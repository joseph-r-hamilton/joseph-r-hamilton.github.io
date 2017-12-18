---
layout: post
title: "Blog Toddler Steps - Step 02"
date: 2017-12-17
categories: blog
tags: [Jekyll, CircleCI, GitHub]
---

Having lots of fun with CircleCI.

It seems GitHub Pages supports external themes directly at the moment.  So just to use an external theme, I need not have gone to such trouble.  However, in the spirit of Continuous Integration, I implemented a "Test" step incorporating [html-proofer](https://github.com/gjtorikian/html-proofer) in a similar fashion as described on [Jekyll's page](https://jekyllrb.com/docs/continuous-integration/circleci/).

But I'm getting ahead of myself.  First, for deployment I used a script based on what I found [here](https://github.com/DevProgress/onboarding/wiki/Using-Circle-CI-with-Github-Pages-for-Continuous-Delivery).  And despite many attempts to handle it different ways, I also was unable to get CircleCI to ignore the push to the other branch.  So I similarly just settled for a "skip".

Next, I ran into a couple of issues when trying html-proofer locally.  Apparently, linked-in has blocked html-proofer outright.  I probably could [change the User Agent](https://github.com/gjtorikian/html-proofer/blob/002c5f1a578f045ff52f53e447aee16889db2b7a/README.md#user-agent) but for the moment it was just easier to use the command line option of htmlproofer to ignore that link.

But the other problem proved to be a good bit of exercise in Git and [Liquid](https://shopify.github.io/liquid/).  Html-proofer was complaining about images which were being served up just fine.  Trouble was an extra space before the closing quote of the url.  I had a hunch were it was but to be able to test it I needed to do the following:

1. Fork hydejack
1. Switch the site's remote-theme to my forked hydejack
1. Clone the fork locally
1. Copy the clone using rsync (yeah... I could have branched)
1. Copy the site on top of the copy via "cp -a" 
1. Test using "jekyll build" and "html-proofer"

Found the issue with the help of [this page on Liquid](https://shopify.github.io/liquid/basics/whitespace/).

Pushed to my fork.  Tested with CircleCI managing the test and deploy.

Lastly, I created a pull request to send the fix upstream.



  



