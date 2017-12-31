---
layout: post
title: "Rodeo - First Impressions"
date: 2017-12-28
categories: Rodeo
tags: [Rodeo, Python, RStudio]
---

OK... I'm starting to **use** Rodeo, not just toy with it.

I realized there was no "Project" functionality yet.  But it seemed really odd that there was no way to
set the current working directory so it was connected to the location of the file.  This isn't a bug,
though some have argued the case on GitHub.  It just takes getting used to.  You just use the directory
chooser of the console pane to get where you want to be.

That felt like a negative.  But if so, it's easily outweighed by a huge benefit - the editor has *vim*
and *emacs* bindings!!

Ironically, the IDE that's been giving me the most grief has been RStudio.  That sucker core dumps if
just breathe funny.  And it's weird.  For some projects, it just works fine.  For others, SOMETHING
repeatably crashes it.  The trouble is that it's repeatable for a period.  Something in the environment
is such that R crashes.  But when that environment thing isn't there, RStudio is fine.  That sort of
problem is devilishly difficult to chase or report.  It seems there's something related to the Clipboard
that's at play.

Hmmm... or... it actually seems dependent on what is being pasted.  It seems to be most common when
pasting a command that involves reading/accessing a file and the filepath is invalid.  But...  it is
oddly not 100% repeatable.  It will eventually do it it without crashing.  It is weird.

But...back to Rodeo.  It sort of grows on you.  I **like** the vim binding but I keep forgetting it's
there because I'm bouncing between so many things.  In a lot of ways, though, it seems a work in progress.
I've seen some folk comment they don't want to see it become bloated like Spyder.  I had to chuckle.
I didn't consider Spyder bloated at all.  Have these guys used Komodo or Eclipse?


