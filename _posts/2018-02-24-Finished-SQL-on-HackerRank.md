---
layout: post
title: "Finished SQL on HackerRank"
date: 2018-02-24
categories: HackerRank
tags: [SQL]
---

Yay!!  I finally finished the SQL track on HackerRank!

Project Three of the Metis Bootcamp had three areas of focus:
* SQL
* Classification
* Data Visualization

We spun up EC2 instances on AWS to serve as database servers using Postgres.  I confirmed that past the lectures I didn't
need to stick with that for the requirements of the Project.  That is to say, I could stick with a local server.  This was
my preference and will be for the next project as well which requires the use of MongoDB.  I used MongoDB locally for Project
Two.  So I see no reason to switch to AWS for Project Four.  I DID follow along the lecture and exercise to prove in the
functionality of using the AWS instance.  But I'm not going to bother for any project until I can see a benefit of doing so.

Indeed, I've been thinking about that.  Alice says for the most part Data Scientists aren't simultaneously Data Engineers.
Usually, we'll not be **creating** databases.  We'll be using them.  In that vein, we'll be using (usually) whatever is
already out there, whatever it might be.

But... when does it makes sense for us to actually use these AWS instances over our local machines?  And then, how best
should we use them?  I'm rather curious if it would make better sense for us to run Jupyter or Jupyter Labs on the same
machine running the database server... or alternatively another instance.  To start, we're using meager, small instances
in the free tiers.  Decent laptops surpass that.  But... maybe just maybe... we could come across something we could
parallelize and then use multiple AWS instances.  Or, possibly, we'd benefit from letting something run for a long time.

I dunno.  As far as it pertains to processing power, memory or storage, I've not yet reached a point where for what
we're doing I need to switch.  But, I may take advantage of the instances for my next Investigation.  I've got some
ideas...

In any case, I had hoped or planned to keep my feet wet in HackerRank by maintaining a slow pace of about a challenge
a day.  The track I was working on was the SQL track.  Given the focus on SQL with Project Three, I decided to ramp it
up a bit and try to finish the track.  This worked well enough... until the last challenge in the "Advanced Join"
category.  That was my final challenge for the whole track.  It was marked "Hard" and had a lower completion score
than the others (meaning fewer people who'd ever attempted it eventually succeeded).  I was determined NOT to look
to the Discussions for help.  I lost several hours on it before abandoning it.

I didn't touch HackerRank after that because the work for Project Three and the Challenge Sets had buried me.
HackerRank got lonely and sent me an email suggesting that I work on that very challenge.  Chuckle...

Well... the SQL Challenge Set from Metis gave me lots of relevant practice.  This Challenge Set was broken into
four sections:
* SQL via a tutorial website
* SQL via a Python SQLAlchemy interface to a Postgres database
* SQLite
* SQL with a Postgres database directly.

Hilariously, I completely missed the requirement of SQLAlchemy for that second part till the last challenge.  I was indeed
using the sqlalchemy module, but only to get a connection with which I was simply pumping in raw SQL.  The last challenge
made a remark about what you'd have to do because SQLAlchemy didn't support a particular functionality.  This made no sense
to me until it dawned on me what I was supposed to have been doing all along.  Sigh... So I had to back up and redo the
entire section.  This was a huge blessing though.  It very much helped to already have SQL that worked so I could
"translate" to the way SQLAlchmey works.

Well... Project Three is largely done.  I still have a bit of work to "publish" it.  But as somewhat of a diversion, a bit
of a cooldown, or just to wrap up loose ends, I decided to finish that track on HackerRank.

I built a small database to replicate the sample shown in the project description and fired up a Jupyter notebook to
hammer away at it.  I finally got it working!!  I thought I'd have to use a bit of recursion, but that proved unnecessary.
I just had to carefully construct enough WITH clauses to get the job done.  Ironically, PostgreSQL is not supported by
HackerRank.  So I chose Oracle and then had to "translate".

All done!

