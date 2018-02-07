---
layout: post
title: "Bootcamp - Investigation One"
date: 2018-02-06
categories: [Metis]
tags: []
---

I gave the presentation for the first of two Investigations today!

[Here it is.](/slides/docker/){:target="_blank"}

The investigations have started.

No... it's not the Spanish Inquisition.

Every student in the cohort has to give two presentations on "Investigations"
at some time during the Bootcamp.  I believe it was the first or second day
when the instructors pointed us to a schedule on Google Docs.  We had to sign
up for two timeslots.

I dutifully ignored this.

I mean how could I even think about researching some random topic in the midst
of all the pressure related to the projects!?!  and the Challenges!!

Somewhere in the past couple of weeks, I caught a whiff or a conversation between
Alice some of the students.  I didn't quite catch what prompted the discussion.
But it seemed to be something along the lines of someone commenting about all
the things to do and the struggle of the pressure relative to scheduling and
prioritizing.

Alice provided this order of prioritization:2018-01-24-Project-Luther-Begins.md
1. Projects
2. Blog
3. Challenges

Now... that doesn't appear to mean just jettison stuff... No, we got a brief
(and supposedly one-time) bit of chastisement from David this morning on
submitting things on time as expected.  And none of that could have pertained
to the Project since we all do that stuff (MVPs, standups, Presentations, etc.).
The only exception so far has been Amy who was out sick on the day for Presentations
on Project Two and she gave her presentation belatedly after I presented my
Investigation.

So... you can run, but you can't hide.  David pestered me last week so I finally signed
up for Investigations.  I chose one early date and one late date since I plan on
one "easy" and one "hard" topic.  OK.  Truth be told, you wait to be almost the
last one to sign up, you no longer have choice of slots.

Docker was on the list of suggested topics, so I jumped on it given my love for
things related to virtualization and my experience playing with containers of
various OSs.

I stayed with reveal.js and like before I tried to explore some new functionality
of reveal.js while doing so.  I used the "cube" transition which, I discovered,
locks you into that for the full presentation - no per-slide overrides.  It seems
to have to with how both sides of the transition have to work with the format.

But the real fun was incorporating "shellinabox" which permitted me to include
a terminal **within** the presentation for the purposes of a live demo.  This
worked well.  It was "cool" to have the terminal be a part of the cube transition.
What did not work as well was what would seem to be simpler - just incorporating
websites in iframes in a slide.  I mean... that's a precursor or dependency of
the functionality for shellinabox!!  But I just could not get it to work.  I 
did manage to use something so I bounced from the presentation to website and
back rather seamlessly... by using some hack for debugging that's been left in
reveal.js as an undocumented feature.  So I did keep in the spirit of not
exiting the presentation.  But still... sheesh!

Another "fun" aspect was that earlier in the day Alice walked the group through installing postgresql
in EC2 instances on AWS.  From there we were supposed to be able to pull the
data into local Jupyter notebooks.  We had all sorts of problems because of
some odd postgresql issues.  It was funny to use as a demo an example of firing
up a local Docker with postgresql and have it all work immediately.  Of course, this
was a bit of apples to oranges since the work to get that to work with Juptyer
would be very similar.

This was the "easy" investigation.  I have high hopes for the next one to be
much more interesting.
