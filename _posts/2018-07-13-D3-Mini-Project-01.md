---
layout: post
title: "D3 Mini-Project: Convex Hull"
date: 2018-07-13
categories: Training
tags: [Javascript]
---

Take a look at a recent mini-project I have been playing with.

A number of things recently converged to prompt me to create a mini project to sharpen some skills.

I used D3 during the Data Science bootcamp.  I was the first to take advantage of it.  But during a
recent technical interview, someone asked me how to do a particular thing in Javascript.  My answer
was truthful, yet likely unsatisfactory.  I simply stated I wouldn't have done that part in Javascript,
but in Python and then feed that into Javascript.  That could be as straightforward as creating an
appropriate Flask-based REST API.  Later upon researching this idea, I'm actually more confident on
this point.  It's not just that I only know to do it that way.  It may be important to do it that way
for security purposes.

But that got me thinking that I really do need to become a polyglot and know how to do a variety of
things in different ways using different languages.  Around the same time, I came aross an SQL challenge
on the CodeSignal (formerly CodeFight) site.  The challenge expected you to use a hard-coded specific
function to calculate the area of a [convex hull](https://www.geeksforgeeks.org/convex-hull-set-2-graham-scan/).
During the bootcamp David suggested to us that one way to learn something is to code it by yourself
from scratch.  For some reason I had just recently reviewed the idea or concept that SQL was elevated
to become an imperative language despite starting out strictly as a declarative language.  Furthermore,
not only did SQL have standard functions for this, so too does the Python stack (in scipy).  I wanted
to see how best to do this using numpy and pandas without scipy.

After getting Convex Hull working in procedural SQL and python, I decided to create a visualization to
demonstrate or show the methodology of the Graham algortihm to determine the Convex Hull given a series
of points.

This is somewhat of a work-in-progress.  I want to circle back here and polish things up a bit and then
show the way area is calculated after the convex hull has been determined.  But here it is...

NOTE: I've not yet included buttons or a mechanism to restart or pause the demo.  If you didn't catch
it just refresh the page while you have the chart on screen.

<iframe class="fragment fade-in" style="float:center" width="800" height="800" src="/assets/html/mini_001/c_002.html"></iframe>

TODO: include Python and SQL code

