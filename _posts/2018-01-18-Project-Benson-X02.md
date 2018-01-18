---
layout: post
title: "Project Benson - Data Exploration 02"
date: 2018-01-18
categories: [Project, Benson]
tags: []
---

Project Benson - More Data Exploration

More notebooks I developed as I played around with the data...

### Frustration

[Project Benson - Exploration 02](https://nbviewer.jupyter.org/github/joseph-r-hamilton/Project_Benson/blob/master/Exploration/Project%20Benson%20-%20Exploration%2002.ipynb)

I started to work on an approach using Resampling and Interpolation.  I wanted this done with a MultiIndex.
It seemed tricky but I got it working easily enough...  Except that it returned negative numbers.
For the next day, I backed off and worked in an entirely different manner.  When I finally got that working
and **still** had negative results, I finally went back and explored the source data only to discover that
some of the turnstile are counting backwards.  The negative results were fine.

I've abandoned this alternative approach.  But it was a good exercise nonetheless.


### Cleanup Analysis

[Project Benson - Exploration 03b](https://nbviewer.jupyter.org/github/joseph-r-hamilton/Project_Benson/blob/master/Exploration/Project%20Benson%20-%20Exploration%2003b.ipynb)

After returning to the straightforward method, the next step was to try to determine how to clean things up.
Part of this analysis highlighted a need to tweak my methodology.

Next, however, I had to determine how to handle truly anomalous information.

### A Clean Notebook

[Project Benson - Exploration 05](https://nbviewer.jupyter.org/github/joseph-r-hamilton/Project_Benson/blob/master/Exploration/Project%20Benson%20-%20Exploration%2005.ipynb)

After working out methods for Data Cleanup and Aggregation, I created this notebook to serve as a clean way
to show the process, to share with the team and to present to the larger audience.

This can then serve as a springboard for further analysis and processing.

