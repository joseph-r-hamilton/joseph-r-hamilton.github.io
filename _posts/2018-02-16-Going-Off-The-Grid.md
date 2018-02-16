---
layout: post
title: "Going Off The Grid"
date: 2018-02-16
categories: [Metis]
tags: []
---

I have a bit of preparation to do...

Just after I might have considered myself caught up after finding myself having to work remotely for a couple
of days, I have a pure absence coming up.

A family issue has arisen that has prompted us to take advantage of the fact the kids are off due to
President's Day.  This is problematic for my experience here at Metis for a couple of reasons.  There will
be a bit of time where I'll be driving.  But when I'm lucky enough to be a passenger, I might be able to
do stuff on the laptop... but sans the Internet.

We talked about this issue early on in the Bootcamp.  David made the comment that the "dirty secret" of the
industry is that, on average, programmers do one websearch for every ten lines of code.  I really believe it.
This isn't even really a bad thing.  You want to avoid reinventing the wheel.  And you want to be able to
incorporate the discussions or learnings of others rather than repeating all the same mistakes or ignoring
opportunities.

I've look ahead to challenge sets to ensure I have datasets downloaded, installed or whatever.

There are some things where I can grab documentation.  I just dp.  But I may also have to shift work around so
I can plan on doing certain things when I'll be off the ownloaded huge PDFs for the documentation 
of scikit learn and matplotlib.  I'm sure these will help.  But I may also have to shift work around so
I can plan on doing certain things when I'll be off the grid.

Just skimming the scikit learn documentation, I confirmed a hunch.  This past week, I subclassed regressors
to create "dummy" or baseline models for comparative purposes.  This was a bit clumsy.  Part of that
was because I only iteratively added functions as I found I needed them.  I knew that surely sklearn had
this already.  But I didn't bother looking it up.

This was a good thing, actually.  This forced me to dig a bit deeper into what **should** be going on
with some of these functions or behaviors between parts of sklearn (estimators, scorers, metrics, etc.).
This is one thing that troubles me a bit with sklearn - it's too powerful.  It gives you so much functionality
in a standard fashion that you can get addicted to tossing things together without really understanding
what's going on underneath.

Another thing that's key is avoiding the seduction of working with lots of data.  Sometimes, it's really
just more important to work with very small datasets.  I don't mean just for speed of optimizing.  It
is really much clearer to **see** what's going on when you only have a few rows and columns.

In any case, I dearly hope I an absence with travel doesn't prove too costly.  The pressure is on for the
current project.
