---
layout: post
title: "Trouble with Clusters"
date: 2018-03-22
categories: [Project, Kojak]
tags: [Kubernetes, AWS, EMR, Hadoop]
---

I'm starting to take advantage of clusters on the Cloud for parallel processing power.

The problem isn't that there's not a way to do this.  The problem is that there are
so many ways of doing this.  This is a very dynamic field.

At a very high level, there's Amazon and Google.  I've tabled Google for the moment.  But I'll get
back over there eventually.

But within Amazon, there are many options.

For general Hadoop, there's EMR.  But even there we have many options.  I explored the use of
MRjob for a previous project.  I never made it very far.  This was nice in the way it automatically
set up the cluster and permitted a very structured way to slip in Python code at the various stages
of the overall Map-Combine-Reduce flow.  I used it for some small experiments with TF-IDF.  But
I didn't have to time then to iron out all the issues with setting up instances and containers
appropriately for needs for that project.

But it seems now that Spark is the way to do Python with a Hadoop structure.  MRJob does actually now work
with Spark.  So I may return to explore that.

Then we have Zeppelin notebooks which work rather nicely with Spark, either directly in Scala or
via pyspark.  So now we have several layers of how to do things in notebooks.  There's Jupyter
Notebooks, Jupyter Notebooks in Jupyter Labs and Zeppelin notebooks.

I tripped over myself yesterday firing up an EMR cluster to play with Zeppelin some more.  This
was a reminder than anything manual will involve problems sooner or later.  So, yesterday I backed
off and slammed in a local install of Spark with Zeppelin in a Docker container.  In all honesty,
I should probably be doing initial prototyping and experimentation locally anyway.  So it was
rather important to get it setup.  But... let's now try to wrap things up so I can get an EMR
cluster going with Zeppelin/Spark support with as little manual support needed.

So... my goals:
* Do everything related to setting up the cluster via the AWS CLI.
* End up with the command to set up the tunnel and the URL for Zeppelin.


Using the AWS CLI, let's create a bucket and upload a bootstrap shell script.

```bash
$ aws s3 mb s3://aws-${AWSID}-boots
```
where {AWSID} is the AWS account ID.  S3 bucket names need to be unique.  This ought to be unique.

Now, let's create our bootstrap script.  I'll call it `zep_boots.sh`.

```bash
wget https://repo.continuum.io/miniconda/Miniconda-latest-Linux-x86_64.sh -O ~/anaconda.sh

bash ~/anaconda.sh -b -p $HOME/anaconda

echo -e '\nexport PATH=$HOME/anaconda/bin:$PATH' >> $HOME/.bashrc && source $HOME/.bashrc

conda install -y seaborn pandas requests

```

Upload it to the bucket...

```
$ aws s3 cp zep_boots.sh s3://aws-${AWSID}-boots/

```

I had been cloning an existing cluster.  From the AWS website, I took advantage of the "AWS CLI Export"
function to get a CLI sequence to create the cluster.  I saved it to a file and then added to the end
of this:

```
	--bootstrap-actions Path=s3://elasticmapreduce/bootstrap-actions/run-if,Args=["instance.isMaster=true","s3://aws-${AWSID}-boots/zep_boots.sh"]

```

Because...  that's what [AWS says it should be](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-plan-bootstrap.html).

After **many** attempts and troubleshooting, here's what you really have to do:

```
	--bootstrap-actions Path=s3://aws-${AWSID}-boots/zep_boots.sh

```

And then rather than using the broken run-if script, just incorporate the logic into your code.  I found a good example
to copy on [the forums](https://forums.aws.amazon.com/thread.jspa?threadID=222418).

Here's a new version of `zep_boots.sh` which includes setup for Graphframes.


```bash
#! /bin/bash

# Determine if we are running on the master node.
# 0 - running on master
# 1 - running on a task or core node
check_if_master() {
    python - <<'__SCRIPT__'
import sys
import json
 
instance_file = "/mnt/var/lib/info/instance.json"
is_master = False
try:
    with open(instance_file) as f:
        props = json.load(f)
 
    is_master = props.get('isMaster', False)
except IOError as ex:
    pass # file will not exist when testing on a non-emr machine
 
if is_master:
    sys.exit(0)
else:
    sys.exit(1)
__SCRIPT__
}

check_if_master || exit 0

# Install Conda and desired modules

wget https://repo.continuum.io/miniconda/Miniconda-latest-Linux-x86_64.sh -O ~/anaconda.sh

bash ~/anaconda.sh -b -p $HOME/anaconda

echo -e '\nexport PATH=$HOME/anaconda/bin:$PATH' >> $HOME/.bashrc && source $HOME/.bashrc

conda install -y seaborn pandas requests

# Install Graphframes
# (gonna need sudo calls here...)

# Note... this is sooo kludgey
sudo mkdir -p /var/lib/zeppelin/local-repo/2ANGGHHMQ
cd /var/lib/zeppelin/local-repo/2ANGGHHMQ

# Need some dependencies
sudo wget http://central.maven.org/maven2/com/typesafe/scala-logging/scala-logging-api_2.11/2.1.2/scala-logging-api_2.11-2.1.2.jar
sudo wget http://central.maven.org/maven2/com/typesafe/scala-logging/scala-logging-slf4j_2.11/2.1.2/scala-logging-slf4j_2.11-2.1.2.jar
sudo wget http://central.maven.org/maven2/org/slf4j/slf4j-api/1.7.7/slf4j-api-1.7.7.jar


# Now get graphframes
sudo wget http://dl.bintray.com/spark-packages/maven/graphframes/graphframes/0.5.0-spark2.1-s_2.11/graphframes-0.5.0-spark2.1-s_2.11.jar

# Finally, prepare for pyspark access of graphframes

sudo mkdir -p /usr/lib/zeppelin/interpreter/lib/python
cd /usr/lib/zeppelin/interpreter/lib/python
sudo jar xf /var/lib/zeppelin/local-repo/2ANGGHHMQ/graphframes-0.5.0-spark2.1-s_2.11.jar graphframes



```

This still requires going into the Interpreters in Zeppelin and changing `zeppelin.pyspark.python` to `/home/hadoop/anaconda/bin/python`.  The goofy thing here is the bootstrap script is run **before** the applications are loaded.  We could get away with creating directories and putting files in (as root... which is good because it prevents the "normal" things removing these files).  But the thing to do to switch to anaconda's python would require changing a file (interpreter.json).  Hard to do if it's not there.  And putting it in there may cause the application installation to fail.

The way AWS EMR has set this up for Zeppelin seems to be... problematic and has caused a number of folk some grief when it comes to loading up additional modules and packages.


But what about getting the URL for Zeppelin?  Didn't I want to be able to ignore the AWS website entirely?

```bash
$ bash create_cluster.sh
{
    "ClusterId": "j-38FI39ISFYGTV"
}
$ aws emr describe-cluster --cluster-id j-38FI39ISFYGTV | grep State
# Wait a bit...  keep checking...
$ aws emr describe-cluster --cluster-id j-38FI39ISFYGTV | grep Dns
        "MasterPublicDnsName": "ec2-18-218-45-180.us-east-2.compute.amazonaws.com",
# Now, to set up the tunnel...
$ ssh -ND 8157 hadoop@ec2-18-218-45-180.us-east-2.compute.amazonaws.com
```

And browse to:

`http://ec2-18-218-45-180.us-east-2.compute.amazonaws.com:8890/`






