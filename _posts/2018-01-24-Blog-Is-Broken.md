---
layout: post
title: "I broke the blog!"
date: 2018-01-24
categories: blog
tags: [blog, Metis]
---

I recently broke the blog!!

I was indeed able to add in the functionality so I could include slide presentations on the blog!!

YAY!

However... as with so much related to the Metis Bootcamp, I was under pressure because of a time crunch.

There is a lot that I could do with this functionality, but for the purpose of using this within
the project post for Project Benson, I chose to "simply" convert the presentation our tream created
from Powerpoint to Reveal.  I got it!  But... I hadn't yet pushed any example slide presentation
all the way to the public blog.  I didn't want this because I didn't want the public blog with the
Swirply project pointing to a dummy slide.

But...

This led to the scenario where I finished the presentation conversion and got done testing things
locally to my heart's content and then attempted the final push around the time the whole thing
was due.  Actually I was about ten minutes beyond the deadline.  It worked locally, so it should
be fine, right?

Well...

I set up a pipeline for the blog.  The push to the public blog goes through a "test" stage.
This is very helpful because not only does it ensure I don't creating broken links on my own,
it will alert me to cases where external links fail.  This could be because I mistyped it. 
Or, as I've learned, it could be because the external site is down that day.  I imagine eventually
I'll run into cases where the external site has reconfigured or deleted that page.  This testing
lets me catch all that and detemine how to clean it up if I wish or just ignore the problems.

This testing failed due to an non-trivial number of issues related to things related to the
inclusion of reveal.js.  There was no simple way to ignore all of that in the same way I
can ignore a single URL.

So... I just had to disable that test phase.

To get one functionality, I had to break another.

Sigh...


