---
layout: post
title: "Blog Toddler Steps - Step 03"
date: 2017-12-22
categories: blog
tags: [Jekyll, Ruby, Liquid]
---

Exploring how to work Jekyll to accomplish what I want with this site...

A number of things aren't really necessary at the moment.  Nonetheless, I need to start getting my feet wet putting some of these things together.

There seem to be many ways of doing any one thing.  Furthermore, some of these plugins seem small or trivial enough that it would be just as easy just to toss in the couple files.

Let's start with *jekyll-category-pages*.  In order to use these plugins or make these changes, it's rather important to understand how Jekyll functions at all.  Problem with lots of these plugins or plugin like things is there's no fully functional demo.  This one does show a listing of categories.  But it's not a format I'd want.  If what I want is paginated category pages...

It would seem I could... just... build upon or extend the current functionality I have with HydeJack.  Jekyll isn't clearly modular.  You have to take care when adding or changing things.

So... it **really** looks like it would be simple to change a couple of lines in a layout file to get pagination for categories.  But it doesn't work... which is why someone went and made that plugin.  The "correct" thing these days is to upgrade to *jekyll-paginate-v2*.

OK.  Upgraded.  But the next problem is figuring out **how** to use this.

EDIT -  Thu Dec 21 16:36:07 CST 2017

I brushed up on Ruby.  But ironically, learning the **syntax** of Ruby doesn't help so much when your problem is in packaging and file management.  I picked up where I left off.  At least I was better equipped to do web searches for solutions.

The trouble was I just dumped the Gem into the *_includes* directory which is where Jekyll docs says plugins go.  The files were getting pulled in.  But not in the appropriate order which was leading to dependency gaps.

A working solution needs follow [this sort of approach](https://newcome.wordpress.com/2013/02/07/hacking-on-local-ruby-gems/).  Sure enough, changing the site's Gemfile from

```ruby
gem "jekyll-paginate-v2" ,
```
to
```ruby
gem "jekyll-paginate-v2" , :path => "_local/jekyll-paginate-v2"
```
was all  I needed to switch to a local copy of the gem so I could play and explore.

Picking up [pry](http://pryrepl.org/) along the way...

OK.  That very much helped.  I could see what was happening.  Or more specifically what wasn't happening.  Jekyll has some oddities baked in given its evolution.  Things that look similar in the templating are treated differently under the hood.  To add to the difficulty, the HydeJack theme does something interesting with categories.  It creates a collection for the categories you bother to document.  This is "featured" categories.  The *jekyll-paginate-v2* has "autopages" which tries to autogenerate these sorts of pages.  I did **not** like that.  I settled on changing HydeJack as follows:

* "Upgrade" to paginate-v2.
* Switch the "featured_categories" collection to "no output".
* Symlink a category directory to "featured_categories".

Believe it or not this works just fine.  With Hydejack and these "featured" collections, I only get the link this indexing for the tages and categories I deem important enough.  With paginate-v2 I get some extra functionality, including a "trail".

For the trail, I have to play around with CSS to get it to look good...  Tweaked the templating a bit too.  Looks good.  Now to prep things and deploy it...

Hmm... running into issues...

Everybody's fascinated with  [slugs](https://yoast.com/slug/) these days...  There's some inconsistency between urls here.  Jekyll doesn't seem to be honoring defined slugs.  No that's not the problem.  The trouble is parts of Jekyll are honoring things case-senstive and other parts of Jekyll force things to lower case.  Some people have just modifed Jekyll's source to change that behavior.  That doesn't seem good.

Well... I don't like it.  But any "fix" I implement here would be kludgey.  It's probably safer long term to submit to case insenstive... sigh...

But... back to slugs...  HydeJack is using the slug parameter to connect the category to the *featured_category* collection.  So, ironically, it does need to remain case sensitive.

Well... I've gotten my feet wet with Jekyll plugins and modifying things through the Liquid templating.








