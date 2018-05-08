---
layout: post
title: "Dask and Spark"
date: 2018-03-25
categories: [Project, Kojak]
tags: [Dask, Spark, Kubernetes, AWS, EMR, EC2]
---

Spark and Dask are somewhat overlapping in what they do.  But they are also somewhat complementary.

To be terribly honest, for a lot of production level things it seems the "Big" of Big Data really has to be
pretty signficant or upon analysis just building a large SQL database will serve just fine.

For my current project, there are things I want to take advantage of at both ends of a pipeline.  For the
initial feature engineering I may benefit from using Graphframes on Spark.  There may be algorithms
avaialble in Dask (eg. SpectralClustering) that aren't yet available in Spark.

Dask is relatively new.  And AWS keeps providing alternatives to doing things.  So this post may
get outdated realtively quickly.  But, at the moment, this is what an individual would experience:

* Dask is far easier to install than Spark on a single, local machine.
* Spark is much more straightforward to get working in a cluster on AWS.
* Dask is vastly easier to learn for anyone used to Python and Pandas.
* Spark is great for anyone already adept at SQL.
* Dask is likely more capable of providing someone *immediate* relief if they're running into
memory issues trying to pull all their data into a large Pandas dataframe.

Now, again, this is **at the moment**.  If I had to roll my own Hadoop setup to lay Spark atop of, I
very likely would be singing a different tune.

So what's the issue with Dask?

First, let's try to separate out things that pertain to any effort of taking advantage of a cluster.
Not every problem can be parallelized.  And many things that can require a fair amount of care to
change the general approach.  You cannot always just take your algorithms and functions and throw
them to a parallel virtual machine, cluster or whatnot.  This becomes evident even on a single
machine.  There are several sklearn models that incorpriate an "njobs" parameter to manage
parallel processing across CPUs/cores.  For the most part with Dask, if you can use this on a
single machine, you can immediately use it on a cluster.  You may still end up with issues where
the data isn't where you need it to be.

No, that's not really different.  You have to manage or at least be aware of that issue on Dask,
Spark or whatever.

What's different at the moment is that for a Dask cluster, you have to set up the cluster.  For
Spark with EMR this is qausi-magically managed for you.

And the more important thing.  Dask is bleeding edge.  The various software solutions to manage
this cluster creation have come and gone rapidly in the relatively recent past.

But I have a feeling that things have somewhat settled on the suggested solution.  So, I'll describe
that here.  It may help to lay out one guiding principle to guide your thinking.  If you try to
look at this from the perspective of Dask or your python code using Dask as being "in control" and
setting up the cluster as needed, you need to flip your thinking.  Get comfortable with the idea
that you need a system to manage a cluster to stick Dask (along with anything else) into.

So.. what is that system?

At the moment it's Kubernetes for the cluster and Helm for the "sticking Dask in " function.

This keeps things modular.  It really doesn't matter whether your Kubernetes cluster is on Google,
Amazon, local network or whatever.  Once you have it, you let Helm do the driving.

For AWS, this is how it breaks down:

* Spark is on EMR.
* If you need to boostrap stuff to build in required functionality...
  - You'll be working with EMR's way of managing this
  - The changes you'll be making are on the AWS instances themselves.
  - You will be able to just SSH into the instances and make changes directly (eg. to test)
  - You may only need to change the master node for a variety of things.
* Dask will be on EC2
* Should you need to control things to get desired functionality...
  - These changes will need to be prepared inside Docker containers
  - You shouldn't need to make changes in the instances themselves 
  - It is **possible** to get into the individual Docker containers.  But it's far less easy to do.
  - It's much more likely you will need to change the Docker container all workers use.




