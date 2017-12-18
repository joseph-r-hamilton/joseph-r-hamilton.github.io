---
layout: post
title: "Blog Toddler Steps - Step 01"
date: 2017-12-16
categories: blog
tags: [Jekyll, CircleCI, GitHub]
---

Well... using Jekyll... I mean actually actively using it is going to be a bit more involved than I may have originally thought.

I have chosen do pursue a path of using Jekyll in a manner that frees me to be able to toss in themes and plugins at will.  But this requires that I fall back to my earlier view that I would end up maintaining two repositories: one for the input to Jekyll and another for the output.

Let me first toss in some notes on what I've been doing locally to choose a theme and build a site.

* I chose to start with [HydeJack](https://qwtel.com/hydejack/) which builds upon [Hyde](http://jekyllthemes.org/themes/hyde/).  I was also interested in [Lanyon](http://jekyllthemes.org/themes/lanyon/) which builds upon [Poole](http://getpoole.com/).  Lanyon provides a toggle for the sidebar.  Still waffling on that... If I want it I can probably build it.
* While playing around with Hydejack, I added an icon for HackerRank.  HydeJack's documentation details how to go about doing that using [IcoMoon](https://icomoon.io/app/).  I grabbed the icon for HackerRank from a collection available at [socicon](https://icomoon.io/app/).
* I am likely to use [TravisCI](https://travis-ci.org/) to manage things. [Jekyll suggests a handful of Continuous Integration options](https://jekyllrb.com/docs/continuous-integration/).  [CircleCI](https://circleci.com/) ranks higher on [Slant](https://www.slant.co/versus/625/627/~circleci_vs_travis) at the moment.  But I believe if you narrow the scope to Jekyll on GitHub Pages, TravisCI probably pulls ahead.
* But.... you know what?  I **will be** doing more than just blogging, more than just Jekyll.  Let's back up and ponder.  Part of the reason for chosing Jekyll for blogging at all was it's focus on Markdown and tight integration with GitHub.  More and deeper experience with Git is more significant than playing with Jekyll.  Similarly, for just Jekyll TravisCI looks best.  But the more I look at the differences between what TravisCI and CircleCI support, the more CircleCI wins out if I consider Data Science projects.

So... let's get going with CircleCI.

There are are several guides out there.  But one thing to keep in mind is how GitHub Pages works differs.  GitHub Pages gives each user a single site plus a site for every repository.  For "every repository" the *master* branch contains the stuff and the website is in the *gh-pages* branch.  For that special single site, the *master* branch is the website.  Most of these guides for CircleCI, Jekyll and GitHub are for grabbing from *master*, processing and sending output to *gh-pages*.  For this single user site, I'll use the *development* branch and push to the *master* branch.

I'd cloned the HydeJack theme and have been working there.  Let's replace the development branch with that:

```bash
$ mv development development.old
$ mv hydejack-starter-kit development
$ cd development
$ rsync -aq --del ../development.old/.git/ .git
$ git add .
$ git commit
$ git push
```
There may have been more proper ways to do that with git.  But that'll do, pig... that'll do...

There are quite a number of examples and guides out there.  I haven't found one quite suitable here.  The Jekyll guide is using the CircleCI version 1.  One benefit of using version 2 is that CircleCI finds and uses its config in the development branch directly.

I found [these instructions from GitHub](https://github.com/DevProgress/onboarding/wiki/Using-Circle-CI-with-Github-Pages-for-Continuous-Delivery), to be rather interesting because of the use of another specific GitHub account for write access - rather than giving CircleCI write access to all your repositories.  CircleCI has [a page describing this](https://circleci.com/docs/1.0/github-security-ssh-keys/#machine-user-keys)

The idea is strange to me.  But it seems once you hook everything and everyone together, CircleCI knows what to use.  Let's see how this works...








