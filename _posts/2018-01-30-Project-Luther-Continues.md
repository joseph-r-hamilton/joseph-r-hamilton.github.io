---
layout: post
title: "Project Luther Continues"
date: 2018-01-30
categories: [Project, Luther]
tags: [MongoDB]
---

Project Luther continues.

We present on Friday.  However, the Instructors have issued the stricture that we must have our analysis complete
by end-of-day Wednesday.  Now... I may take a bit of issue with what "end-of-day" means.  But they've specified
Thursday is to be solely for development of presentations.

For me, this means that Tuesday was/is for **more** data scraping.  And Wednesday is primarily going to be devoted
to analysis.  Or to put it another way, I cannot do a good job on the presentation if I'm still fighting with the
analysis.  And I cannot do justice to the analysis, if I'm still scrambling over scraping.

There's simply not enough time to do all of what we want on these projects.  I had hoped to incorporate some
basic Unit Testing and CI support.  That's out.  But I **did** implement the pipeline to MongoDB as a backend.
My fears may have been unwarranted.  But I was leery of issues of concurrent scrapes dumping to a single
text file.  It was likely not really an issue.  I had though the concurrency setting was set to "1".  But that
was what I had seen as I reviewed the project from last year.  In any case, I'm happy to have incorporated
MongoDB.

I did implement a scraping approach that could end up pulling all the property tax data from Will County...
if it's left to run long enough.  It's still a bit slow for some odd reason.  Maybe, I can tweak it a bit...
who knows.

But I've already shifted to analysis.  The pair-plots seemed to show me that there may yet be some pattern or
signal to capture but it's being swamped by outliers.  So I started doing some box-plots and histograms to get
a sense for things... And oh boy!  I have outliers.

I still have work to do to incorporate a good number of my features.  And I may be able to create some
more features based on aggregated data (assuming I can get reasonably close to a complete scrape).  But even
with the initial set of records, it's clear there are things I could do.  I may end up jettisoning some records
to get rid of outliers.   Or I may switch those features to logarithms.  I'll have to experiment.

