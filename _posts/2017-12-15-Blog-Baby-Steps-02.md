---
layout: post
title: "Blog Baby Steps - Step 02"
date: 2017-12-15
categories: blog
---

Progressing through some baby steps...

Spawned a development branch.  Pulled it down.

Found and fixed a bug with layout for posts.

Corrected something for the RSS feed (layout to "null").

Alright... I've been using Jekyll locally on the laptop.  Took a bit to get used to how this should work and flow.  But the warnings one can see by doing this guided me to the fixes above.

Now... let's try to push this and pull it from the home network...

Piece of cake.  Hadn't set up authentication for git yet in the home network.  Good to get
that out of the way.

So, the next thing to do here is to experiment with themes.  Color, flair, special effects and
all sorts of bells and whistles may prove distracting.  But there are a few "needs" here.
To me these are critical:

- Use of categories
	+ Search on categories
	+ Sidebar (or something) listing categories
	+ Heirarchical category management
- Search by Date
- Pagination

But let's just start with the distracting fun stuff.

Hmm... experimentation with themes seems to show I need the github-pages gem and it's not
installed.  Woah.  It pulls quite a lot with it.  And for some reason, it's taking forever
on the home network.

And that was pointless.  Well... no.  It was unsuccessful.  Well... no.  It just introduced
some *issues*.  Punching in github-pages added quite a lot to Gemfile.lock.  You end up
with multiple gem versions.  The "correct" thing to do is to force ruby to use the versions
specificed in the lock file by calling "bundle exec jekyll serve" rather than "jekyll serve".

Next, however, there is going to be a limitation of what will be supported via hosting on
GitHub Pages.  Not at all sure this matters.  I haven't even tried any themes yet.  But
something to consider.  The solution is straightforward if I find I need something more:
just use jekyll locally to produce the content and then push that.

Let's try at least one them before pushing and switching back to the laptop...

Ouch.  OK.  This is NOT what I expected.  I was spoiled before, I guess.  I was expecting
something like changing skins on any number of things... where it would be a relatively
minor one-line change thing.  It is not at all this easy.  I found I liked one of the
themes supported directly by GitHub Pages.  And I can serve it locally... but copying
over the data and configuration from another existing Jekyll site is manual and tedious.

Worse yet, a bit of research into plugins and such strongly suggests to me I'll need
to use plugins not supported innately on GitHub Pages.

Beginning to explore next steps...
