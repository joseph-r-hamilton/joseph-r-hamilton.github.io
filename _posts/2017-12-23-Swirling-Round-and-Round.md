---
layout: post
title: "Swirling Round and Round"
date: 2017-12-23
categories: [Project, SwirlyPy]
tags: [Swirl, SwirlyPy, R, Python]
---

I just stumbled atop a couple things that may prove helpful or may just be an entertaining distraction.

I'm working through a MOOC that uses R.  SInce the upcoming Bootcamp is exclusively Python, I'm mirroring the work in Python.  But to follow along I need to learn R.  I'd been bouncing in and out of Swirl to get what I needed for the moment (kinda in a "I know what need, these concepts aren't new to me... I just need to know your syntax, silly tutorial program!").  Swirl asks at the beginning if you want the tutorial or the "[Swirl repository](https://github.com/swirldev/swirl_courses)".  I'd glanced at it before.  But this morning I actually looked at it.  And dear heavens if it isn't a slew of stuff parallel to a lot of these Stats and Data Science courses.

Woah.

So... given my current focus on mirroring R and Python work, I just had to scratch a curiosity and sure enough I found [Swirlypy](https://github.com/alexander-bauer/swirlypy).  I'll have to play with this.  Many people who've been pining for something like this seem to want a basic Python tutorial.  The structure and program is here but the library seems empty.

How hard would it be to port the R swirl courses?

Alright.  I've got a slightly better sense of the scope of the task.  First, this is how to run things.

Step one - get the package.
```bash
$ cd $SOMEDIR
$ git clone https://github.com/alexander-bauer/swirlypy
```

Now, in python...
```python
import sys
sys.path.append(SOMEDIR/swirlypy)  # Full path to location
from swirlypy import course
course.Course.load(COURSEDIR).execute()
```
The repostiory comes with a sample courses.  So I just did "SOMEDIR/swirlypy/courses/intro".

It works, after a fashion.

There's a ton of similarity between this and swirl.  The courses are YAML files for both.  The general structure is similar.  The challenge is the types of questions supported.

It seems swirl itself is not that old.  The effort to create swirlypy started almost immediately after the start of swirl.  But development of swirlypy stopped and swirl went another year or so of active development.

This may be insane... but I want to take  a crack at this.  It would be good practice with git, matplotlib and stats stuff in general.

Although I've set up rpy2, it probably wouldn't be wise to depend on R directly like this.  When using the data sets, these can be found online such has [here](https://vincentarelbundock.github.io/Rdatasets/datasets.html).

I grabbed [the Swirl Courses](https://github.com/swirldev/swirl_courses) respository.  Let's try to port what's listed there as "Overview of Statistics".  And... because it'll be a huge focus of the next few months, let's try to incorporate pandas in even this simple data analysis...

```python
from subprocess import check_output
import pandas as pd

from os import chdir, getcwd


chdir("swirl_courses/Open_Intro/Overview_of_Statistics")

output = check_output('grep "^- Class" *yaml',
                      shell=True, universal_newlines=True).strip().split('\n')

d = pd.DataFrame(output)
d[0].replace(to_replace='- Class: ',value='', regex=True, inplace=True)
d[0].value_counts()

text                   58
figure                 24
cmd_question           15
mult_question          14
exact_question          5
video                   5
range_question          3
text_order_question     2
text_many_question      1
meta                    1
text_question           1
```

I believe many of those will be straightforward extensions of classes already built in swirlypy.  The real challenge and the high runner is *figure*.

I may start with some of the easier ones to get going.  Text out to be a straight drop in.

More later...
