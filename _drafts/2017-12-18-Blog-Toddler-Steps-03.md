---
layout: post
title: "Blog Toddler Steps - Step 03"
date: 2017-12-18
categories: blog
tags: [Jekyll]
---

Exploring how to work Jekyll to accomplish what I want with this site...

A number of things aren't really necessary at the moment.  Nonetheless, I need to start getting my feet wet putting some of these things together.

There seem to be many ways of doing any one thing.  Furthermore, some of these plugins seem small or trivial enough that it would be just as easy just to toss in the couple files.

Let's start with *jekyll-category-pages*.  In order to use these plugins or make these changes, it's rather important to understand how Jekyll functions at all.  Problem with lots of these plugins or plugin like things is there's no fully functional demo.  This one does show a listing of categories.  But it's not a format I'd want.  If what I want is paginated category pages...

It would seem I could... just... build upon or extend the current functionality I have with HydeJack.  Jekyll isn't clearly modular.  You have to take care when adding or changing things.

So... it **really** looks like it would be simple to change a couple of lines in a layout file to get pagination for categories.  But it doesn't work... which is why someone went and made that plugin.  The "correct" thing these days is to upgrade to *jekyll-paginate-v2*.

OK.  Upgraded.  But the next problem is figuring out **how** to use this.

  



