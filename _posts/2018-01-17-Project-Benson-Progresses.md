---
layout: post
title: "Project Benson Progresses"
date: 2018-01-17
categories: [Project, Benson]
tags: []
---

Project Benson is underway.

OK.  The last 24 hours have been somewhat of a rollercoaster with regards to Project Benson.

I spent a fair amount of time pursuing the data from a Exploratory Data Analysis point of view.
And I simply loved it.  It was good practice with Pandas.  I learned several new aspects of how
to use Pandas for time series sorts of data.  It was also frustrating when I got stuck trying
to do things that appeared to work but didn't.

But in the morning Alice reminded us that good Data Scientists do **NOT** jump right into the data
searching for things that can be done with the data.  A Data Science project begins with Design.
This was a repeat.  I'm pretty sure she said the same thing yesterday.  But... it was bewildering
then and it was chastening today.  Because... the data is so much FUN.

There's a number of traps and pitfalls here.  First of all, we may end up either limited by focusing
too much on the data at hand or simply incredibly biased because of this focus.  Next, we can spend
a lot of time pleasing ourselves or attempting to build monuments which may be overkill or mismatched
compared to what anyone ever really wanted.

So... how do you do Design before jumping into the Data?  We discussed this...

* First, **listen** to your Customers.  Learn what problems they want solved.  Discern what may be
a threshold of satisfaction or a point of diminishing returns.
* Second, **brainstorm**.  Think about the problem.  Ponder how you'll approach the challenge.  Draft your goals.
* Determine a **MVP - Minimum Viable Product**.

This approach should help to guide the overall effort.  It also sets you up for an iterative method
where you can have *something* to show for your work ASAP but then build upon it.

So... what did we do?  Jump back into the data.

Well.. that's not entirely true.  We spent a lot of time debating methodology... about the data.

Nah... we hastily determined our MVP would be simply a ranked list of the MTA stations based on traffic flow.

But the trouble here is determining how to assess this.  The "fun" part of the MTA data is this isn't actually
quite readily availble.  You must massage the data a bit.

Kendall and I discovered each of us had wrestled with trying to determine the structure behind the data.
We still cannot quite figure out what some of it actually means.  Oh we could figure out what to count.
But... there were hints that you might be able to say more if you undertood more of what it represented.

At some point I described what I'd been doing with standardizing and interpolating by resampling the data.
Kendall and I debated that a lot because her Math/Stats background made her leery of interpolation, especially
dumb linear interpolation.  Dean jumped in and we explored this a bit.  But it wasn't clear any other thing
we were discussing would be any easier or better.  Derrick stayed quiet and simply plugged away at another
approach altogether.  When he shared his idea, we pointed out the errors inherent in that approach and guided
him how to continue with it by aggregating up to the STATION level.

All of our approaches have errors.  Linear interpolation makes assumptions about the rate between the
interpolation.  But so do alternative approaches based on other distributions.  Derrick's approach bumped
up the granurality to 1 day but with known errors around midnight.

We're continuing to work on anything and everything.  But we selected Derrick's approach because it's
easier to do quicker.  And... boy is this projecting being rushed!  Dean typed up our Design Statement
and submitted it.  Our MVP is due tomorrow, less than 48 hours after the project started!

Furthermore, if I get the interpolation working it would permit us to the same 4-hour granularity, or
lower as long as we remember it's interpolated.  And it would very likley corroborate the per-day
approach.



