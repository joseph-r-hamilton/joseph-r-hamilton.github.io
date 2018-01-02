---
layout: post
title: "Happy New Year"
date: 2018-01-01
categories: blog
tags: [Backup]
---

Happy New Year!!

A LOT is changing for me this year.

I am in the midst of a career transition.

I am agressively pursuing training in a variety of forms.

I may end up sliding into working contracts as a Consultant either in place of or in addition to traditional employment.

Who knows.

But I was reminded today that you have to be prepared.  Specifically, you have to be prepared for when your machines and data fail... which means you have to have a backup plan.  It probably also would be wise for me to reboot more often... at least to be sure things will reboot.

The new Linux Virtual Machine I'm using for my MOOC studies and Data Science work went belly up.  It was the weirdest thing.  But it was a wonderful object lesson to be careful about how you interpret data.  What one could **SEE** seemed to be odd errors mostly related to networking when it seemed to fail booting.  Playing with the NIC didn't do anything.  Only when I booted from a (virtual) DVD-ROM and chrooted into drive to check the logs did I find out what the problem really was... and that the system had indeed booted, complete with networking.  What had failed was SDDM.  Somehow SDDM had gotten updated without a dependency.  A full system upgrade and all was fine...

but...

It was a good reminder I need a robust recovery plan for my work.

So that's my task for the moment.  I'm setting up rsnapshot which will facilitate recovering from my own mistakes.  And I'll be implementing a cloud backup as well.


