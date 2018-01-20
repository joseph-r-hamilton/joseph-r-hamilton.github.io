---
layout: post
title: "Project Benson MVP"
date: 2018-01-19
categories: [Project, Benson]
tags: []
---

Project Benson is wrapping up.

We are supposed to be ready to present Monday morning.  We were supposed to have finished up our presentations.
We were supposed to have had a practice presentation.

We aren't quite there.  Oh we're gonna have to present no matter what.  And there was a scheduled social event
to cap out Week-One which really did break the stress and focus, so to speak.

But I'm not sure any of our groups are truly at a point where they're not going to be working on this over the
weekend.  And there is a reason they laid out this goal (of having it wrapped up and being free over the weekend)
- they gave us homework... which... ironically would
have been useful **before** attacking this project.  I'm sure it'll help reinforce things.  Indeed, I'm
rather certain that's part of the entire pedagogy here.  We're getting this training before, during and after
while under immense pressure.

If all of the above sounds like doom and gloom, you're reading it wrong.  I'm thrilled with this.  And I sense
a lot of the others are enjoying this too.  It's just so fast paced.  And when you force yourself to cut to
the next aspect (for example, from data wrangling to visualization), you have to start an uphill climb all
over again.  You may have gained some confidence by gaining some fluidity in the previous aspect only to feel
like an infant all over again.

So... enough meta data.  What did we **do**?

Last night I fought with the available geographic data to get a location data for each "Station" in the
MTA data.  The NY data provides geo-data but it is not cleanly aligned with the MTA data.  A bit of patient,
manual sorting and matching got me about 90% there.  Google and Wikipedia got me to about 99%.  For the rest
I just had to make some quasi-intelligent decisions.

I fought through installation of several libraries and played with plots with maps.  I eventually got a
basic heatmap of all the MTA stations.  It didn't dawn on me until I could **SEE** it how odd it is to
be incorporating the non-Manhattan burroughs and simply ignoring Jersey entirely.  The problem statement
didn't specify Manhattan as the location of the gala, although it seems intuitive.  But the problem statement
clearly lays out the scenario as one where the Customer/Client already had the focus on the MTA.  Too late
now to do anything about it.

But... this is probably a good example of the issue of putting Design before Data.  Jump right into the
MTA data and you're locked and biased in that view.  Maybe if you just thought whether it made any sense
to analyze the burroughs the concept of Jersey could have arisen.

We may have ruled it out.   Indeed, we may have chosen to ignore the burroughs if we could.  But what strikes
me is how we utterly ignored New Jersey entirely.

Otherwise, the challenge for our team today was to shift from Data Analysis to Visualization.  We simply
did not have the time to properly synchronize or synthesize our various methodologies.  All of our were
doing slightly different things:

* Me: a Time Series resampling, interpolation, cleaning
* Derrick: a "min-max" per day approach
* Kendall: a weighted average rather than "dumb" interpolation
* Dean: working on code that would take clean data from one of the rest and do further analysis

For the most part, as much as we could test it, all of our approaches were showing the same top sites
in a ranking by traffic.  Derrick had a challenge because it was harder to remove the anomalies with
his method and harder still to limit the impact (those anomalies cost me a 4 hour block and I switched
to interpolating the gap; it cost him a day).  Kendall got her more complicated method mostly working
but before we could really contrast and compare we had to move on.

Since I was ready with clean data a bit earlier, I'd moved from working with the single per-week dumps
from the MTA and using the yearly dumps from NY.  I grepped (yes... literally using grep) the months
of March, April and May from each of 2015, 2016 and 2017, processed these and one-by-one fed the
data to Dean.  Dean and I then struggled with it.  We fought through issues of Pandas so we could 
do analysis and start making charts.  I found almost no variation in the ranking of the first ten
sites when looking at all three months vs. one week in the 2017 data.

I made some charts and spent a lot of time beating my head against the arcane details of matplotlib.
I pushed some charts to our group repository and Kendall provided me some feedback to change a few
things to align more with the morning's lecture on Visualization.

Eventually Dean drafted a Presentation and we sort of discussed who'd say what.  We will be wrapping
up charts, etc. and will present.






