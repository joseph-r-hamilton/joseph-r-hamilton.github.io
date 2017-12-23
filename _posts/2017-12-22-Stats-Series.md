---
layout: post
title: "Stats Series"
date: 2017-12-22
categories: [Training, PH_525_series]
tags: [Statistics, Harvard, R, Python, Rodeo, Spyder]
---

It's time to shift gears a bit.  I need to start **using* this blog, not just play with it.

I've about a month left before starting the **Metis Data Science Bootcamp**.  One of the things I'd slotted to do in December was to work through this online course series from Harvard.  The Metis Boocamp is exclusively Python.  A number of these MOOCs and books focus on R.  I have found one book that does both Python and R.

For this course, I'm going to try to replicate work in Python.

The Harvard course is a 6 part series that parallels the book *Data Analysis for the Life Sciences*.  I was drawn to the series when searching for a refresher on Linear Algebra.  That's course 2 of 6.  I chose to use HackerRank for the review and will now push through the entire series, time permitting.

The course starts with the R tutorial.  In order to load packages, I had to back out and load some more stuff in Anaconda:

```bash
$ conda install gcc_linux-64
$ conda install gxx_linux-64
```

Then I was able to proceed with
```R
install.packages("swirl")
install.packages("rafalib")
```

The first exercise in PHP 525.1x is a "First Assessment: Run Swirl Exercises".  It's essentially a quiz on basics of R syntax which you get through *swirl* - the R tutorial.

I used RStudio for swirl.  But then I fired up two parallel Jupyter notebooks - one for R and another for Python.  I installed [rpy2](https://rpy2.bitbucket.io/) and was even able to call the "version" command from Python to confirm the version of R.  But the main benefit of this was the access the standard datasets in R.

They fairly strongly encouraged an approach of projects in RStudio.  I will try to mirror that in Python.  This should be a good chance to test out both Rodeo, which seems most akin to RStudio and Spyder.  The questions for this next exercise seem simple enough that notebooks will still work fine.


