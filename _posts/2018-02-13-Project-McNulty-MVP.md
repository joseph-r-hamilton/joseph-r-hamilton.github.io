---
layout: post
title: "Project McNulty - Choices"
date: 2018-02-13
categories: [Project, McNulty]
tags: []
---

Project McNulty has passed MVP.

Working on Project McNulty has been interesting.  I've suffered a bit due to days not being in person for
lectures.  In general, the project has been more straightforward.  Nonetheless, all of our work seems
to require a lot of time - many very late nights.  There is almost always some aspect of what you're working
on that is new.  So any time saved because you already know one thing is counter-balanced with something
that you haven't yet mastered.

SQL and database stuff isn't new to me.  But PostgreSQL is.  I've known OF Postgres.  But I've mainly used
MySQL in the past.  And Postgres isn't even an option for databases in the SQL track on HackerRank... which
I've almost completely finished.  So getting used to weird Postgres quirks is one thing.  Yet another is
learning SQLAlchemy and more important for this particular project Socrata and SODA.  Because of the structure
already inherent in the dataset I was using, I wanted to create and use a function that would use SQLAlchemy
to create the table strcture for Postgres automatically from the Socrata metadata.  What I ended up with
certainly isn't *complete*.  But it would be very straightforward to pick it up and tailor it for any
future project using another Socrata-based dataset.

Punching the data in was easy once I had the table set up.  After a few tests with very small batches, I
pushed in the entire thing.  It took about 100 seconds for 6.5 million rows.  I still want to go back and
create a function to "top off" my data.  The Chicago Data Portal updates almost daily.  I should be able to
use a SODA query to pull in recent records and upsert to punch it into my local store.

Next... once I started to **use** the data, I encountered some common database sorts of problems.  Queries
were slow.  So I punched in a few indices.  That helped.

After that I have a number of issues related to size.  First, I can exhaust memory.  Any number of things
are holding onto or leaking memory.  Rebooting the VM helps.  But overall, I've set the VM at 10G.  I
*could* update the laptop to 32G and give the VM 25G.  But that's expensive.  Alternatively, I can set
up swap files.  The best for speed is the SSD.  But I don't want to eat into that space and upgrading the
SSD wouldn't just be costly - it'd be painful and risky.  The HD has plenty of space but it's slow.  So
as an alternative I ordered a slim USB3 stick.  Using it for swap will likely kill it.  Oh well.  I'll be
free from "out-of-memory" issues.

Memory issues are just one part of the size problem.  Time is another.  But today we covered spare matrices
in lecture.  I have several large categoricals.  When I blow those out to dummy variables I get huge things
that take a lot of time.  I **NEED** to employ sparse matrices here for this project.

But beyond what efforts I will undertake to setup swap for a large amount of virtual memory and tricks
to speed things up, now that I've gotten a couple pretty pictures based on prototypes for the MVP, I
also just need to play more with much smaller datasets.  For the MVP, I just queried for all of the data
for 2017.  Even that was a quarter million records.  For model evaluation, I do need something that captures
a fair representation of the categoricals.  But nothing so big.

I didn't bother with interpretability or descriptions of the modeling... at all for the MVP.  I just described
the dataset, tossed in a geo picture I created via Tableau and showed a couple of learning curves.

It was good enough for MVP.

But... what was **VERY INTERESTING** for the Project McNulty MVP was that we did not present our MVPs.  Project
Three is actually a solo project.  But we were grouped into teams.  Our teams are like "project buddies" where
we each go to our team for assistance and help before others or the instructors.  The real fun here, however,
was that someone else on our team presented our MVP on our behalf.  This meant we had to communicate with
each other well enough that we could give the teammate's presentation.  The way this was explained early on
was that we'd have to understand each other's code.  But that wasn't truly necessary.  It **WAS** if that
team presented via the work in a Juptyer notebook which several did.  A slide presentation of any kind
negated that need.  And for the final presentation we're back to giving our own talk.

So... now we *could* have simply acted as if we were presenting the talk on our teammate's behalf... you know...
which we were doing.  But no... the first person that went up started by acting as if they were the other
person.  And it just got more hilarious from there.  Everyone followed that trend of pretending to be the
other person.  Then people started trying to do a good job **imitating** the other person.

It got utterly comical at that point.  Now, for some things the instructor's questions were fielded by the
actual author.  Alex got into it with David because David questioned whether he was really using "Accuracy"
as the metric to compare models.  Alex retorted that he was only using Accuracy because the things he had
ready to go to create charts used Accuracy.  I exclaimed "ditto" because I knew I had the very same issue.
But... when it was my turn, Amy (who was presented on my behalf) and I started speaking together.  So,
I deferred to let "Joseph" respond.  And Amy was hilarious since she just bluffed her way through saying,
in essence, that for the most part all of these metrics trend together and any one of them would do.

This was silly, but incredibly funny.  On a more serious note, this highlighted something I'd missed not
being here for a couple days.  I scoured the material again to confirm "logloss" wasn't covered.  It seems
it was something David covered from material on his own blog.  I need to go read that... especially since
it is probably important for my project.  Not only was it not in the material.  It wasn't in the challenge sets and we haven't
yet covered it in a Pair Problem.  But after the David-Amy exchange, David all but insinuated it
may well be in an upcoming Pair Problem.

So... while the others were going, Amy was clearly getting into the spirit of all this and she asked me
to imitate myself so she could work from that.  I told here that was silly.  Imitate myself?  Preposterous.
In any case, she did a fair job imitating me... I guess.  One obvious thing it did was it made her present
loudly.  She's normally as quiet as a mouse and gets even quieter as she continues to speak.  I imagine I'm
at the other end... just a loud presenter.  Well... it get her more where she needs to be.  I don't think I
did anywhere near as good a job channeling Michael.  And although Michael may have somewhat started with
an Amy imitation, I don't think he kept it up long.

Even more hilarity followed as Adam imitated Derrick.  But the really memorable thing was a comment Adam
made when Derrick got done presenting for Tiffany and Tiffany went up to present for Adam.  Adam whined
that now Tiffany finally knew what it felt like to follow Tiffany.  We all lost it.  Several students
have, in the past, overtly requested from the instructors that they be able to present before Tiffany.

Why?  Tiffany's past work experience has drilled into her the use of Keynote and Tableau in a way that
is very fine.  She's mentioned a previous boss was very finicky on the use of Keynote.  Things had to
look "good".  It's not that we cannot do so... given time... lots of time...  It's that no matter what
we do, it is upstaged by Tiffany who seems not to even be trying.


