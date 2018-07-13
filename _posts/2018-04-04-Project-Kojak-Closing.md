---
layout: post
title: "Project Kojak Closing"
date: 2018-04-04
categories: [Project, Kojak]
tags: []
---

It's the night before Career Day, and all through the house...

Wow.  What a ride!

I have not been blogging much these past couple of weeks.  I may end up back-creating a post or two
here to describe the overall project.

At the moment, I'll just try to describe what happened over the past three weeks.

I chose to extend Project Four in a loose sense.  The purpose and nature wasn't really anything like
the previous project.  The main similarity was the source of the data.

The goal - find trolls on Reddit.

I wanted to focus on a few aspects of "Big Data" for this project.

I wrestled with the instructors a bit over this topic because of a core problem that seems to be
intrinsic for a lot of Data Science or analytic type projects.  One must be careful whether one is
chasing a Supervised or Unsupervised problem.  This may seem rather easy.  Either you have labeled
data or you don't.  But the temptation to believe you can create labels can be rather strong.
No matter how much I looked for some, there wasn't really any way to get a list of known trolls.
I sort of broke through and won blessing for the topic when I was able to cast it as a study of
Anomaly Detection and possibly clustering to learn more about trolls.

So, in a sense the focus shifted a bit away from Trolls and more towards Anomaly Detection.

The first goal was just to prepare the data.  Back in 2015 someone used the Reddit API to create
a historical archive of **all** the past Reddit comments.  This data bounced around to several
forums or locations.  Kaggle hosted one month's worth of data for a challenge.  Someone put this
up in AWS in a S3 bucket.  And, I already knew from Project Four, a file hosting service was
keeping these archives going with about a one-month lag from current.  So, I wanted to create
a second S3 bucket to upload the past couple of years.

This wasn't much more trouble than just firing up EC2 instances and some scripting to download,
uncompress and save.  I had to do this in a way that didn't depend on my connection.  It took a
while.  Of course, I **could** have punched in many instances and done this in parallel.  But
I didn't feel I needed to rush through this part because I needed to do some research in parallel.

I grabbed a number of papers and such to learn what folk have done with similar projects on
Reddit data or anomaly detection algorithms, etc.  And I started to learn Spark and Dask.  I had
lots of places to start:
* David's Spark and Zepellin Lecture
* Mike's Isolation Forest Investigation
* Tiffany's Zepellin, GraphX and Graphframes Investigation
* Alex's Dask Investigation 

SOME of these weren't quite ready when I needed them.  I started reading up on Dask before Alex
gave his Investigation presentation.  But I was able to grab his Jupyter notebooks after his
presentation to repeate them personnaly.  Same for GraphX with Tiffany.

David asked me at one point if I'd settled on Dask or Spark.  I hadn't yet.  But I think it was
right about that time that something dawned on me that should have been pretty clear from the
beginning.  The Reddit archives are comment data only.  But I'm interested not in finding
Troll **comments**.  I wanted to find Troll **users**.  Some of the papers I'd reviewed had
maintained a focus on the per-comment data.  This wasn't my goal at all.  I think I'd imagined
that I would be using Feature Engineering in order to add a few extra features to the existing
features in the data set.  There was a small eureka moment when it became very clear to me that
I wasn't adding features - I was creating them... all of them.  That is, I had per-comment data but for my
modeling I needed per-user data.

It then seemed important not to choose between Spark and Dask but to use both of them for their
respective advantages.  One paper I'd reviewed described using graph-based features.  It seemed I
could do this with GraphX/Graphframes.  So, that'd push me towards Spark.  But Dask's rather native
tie-in with Python would facilitate use of SKLearn.  At that point, I chose to use both.
All I needed to do next was choose how to store data in a way that would work well for both.
I settled in on Parquet. 

Time was the ever-present pressing problem.  There was never really enough of it.  In one sense, I
was well ahead of schedule having my data pulled into the S3 bucket before the informal deadline of
"Data Collected".  But... this was somewhat of an illusion since my modeling would only be based on
the result of the feature engineering.  And I had several things I had to learn simultaneously:
* Spark
* Zeppelin
* EMR clusters
* GraphX/Graphframes
* Dask
* Dask clusters (which eventually meant Kubernetes)

The other interesting aspect of this project was that we formed small accountability groups.
Within these we orderd in such a way that everyone was responsible for another.  In my group,
I was responsbile for Tiffany who was responsible for Chris who was responsible for me.

So, I had to pay attention to Tiffany's status as she progressed through her project.  When I heard
she was having issues due to getting kicked out of her SSH connection to her EC2 instance, I arranged
a quick tutorial session where I showed her how to take advantage of redirects, background jobs and
nohup to ensure her data scraping jobs persisted regardless of the connection.  This was essentially
what I had done with my EC2 instances for extracting and storing data in the S3 bucket.

Then later on when I was working through the Zeppelin notebook she created for her GraphX investigation,
I ran into the same roadblock she'd found with regards to getting Graphframes.  There's something a tad
messed up at the moment with regards to installing it for use with Zeppelin.  I found a way to get it
workign and quickly shared it with her.  She promised to help me with Tableau later on... but alas...
there's really not that much to visualize with Anomaly Detection.

There came a point where we had to end the modeling and start working on a presentation.  Tiffany, Chris
and I met to discuss strategies.  And then later David and Alice met with our team.  As they'd told us
they would, they didn't ask each of us to describe our approach for our project.  Instead we had to describe
the project and presentation strategy for the person we were responsible for.


