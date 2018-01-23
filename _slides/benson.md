---
title: Project Benson Presentation
description: Presentation of Analysis and Recommendations related to Project Benson
date: 2018-01-23
layout: slide
theme: league
transition: fade
---

<section data-markdown data-background="/assets/img/slides/Benson/Background_01.png">
# Project Benson:
## Strategies for Optimizing Street Team Placements

Dean / Dereck / Joseph / Kendall

01/22/2018
</section>

<section data-background="/assets/img/slides/Benson/Background_02.png">
<h2>Methodology</h2>
<ul>
<li class="fragment">Assumptions</li>
<li class="fragment">Data Cleaning/Aggregation</li>
<li class="fragment">Recommendations</li>
</ul>
</section>

<section data-background="/assets/img/slides/Benson/Background_03.png">
<h1>Data Cleaning & Aggregation</h1>
</section>

<section data-background="/assets/img/slides/Benson/Background_02.png">
<h2>Data Issues</h2>
<ul>
<li class="fragment">Reset Counts</li>
<li class="fragment">Turnstiles rolling backwards</li>
<li class="fragment">Different time intervals</li>
<li class="fragment">How to standardize the counts</li>
</ul>
</section>

<section data-background="/assets/img/slides/Benson/Background_02.png">
<h2>Data Cleaning</h2>
<ul>
<li class="fragment">Three methods explored</li>
<li class="fragment">Resampling and Interpolation</li>
<li class="fragment">Weighted Averages</li>
<li class="fragment">Min/Max per day</li>
</ul>
</section>

<section data-background="/assets/img/slides/Benson/Background_02.png">
<h2>Data Aggregation</h2>
<ul>
<li class="fragment">Pivot table (groupby)</li>
<li class="fragment">Total traffic by station and date</li>
</ul>
</section>

<section data-background="/assets/img/slides/Benson/Background_02.png">
<h2>Top Stations with Most Traffic</h2>
<img data-src="/assets/img/slides/Benson/Chart_01.png"/>
</section>

<section data-background="/assets/img/slides/Benson/Background_02.png">
<h2>Top Stations with Most Traffic</h2>
<img data-src="/assets/img/slides/Benson/Chart_02a.png"/>
<img data-src="/assets/img/slides/Benson/Chart_02b.png"/>
<img data-src="/assets/img/slides/Benson/Chart_02c.png"/>
</section>

<section data-background="/assets/img/slides/Benson/Background_02.png">
<h3>Observations #1</h3>
More high traffic stations on weekdays
<img data-src="/assets/img/slides/Benson/Chart_03.png"/>
</section>

<section data-background="/assets/img/slides/Benson/Background_02.png">
<h3>Observations #2</h3>
More high traffic between 4 to 8pm
<img data-src="/assets/img/slides/Benson/Chart_04.png"/>
</section>

<section data-background="/assets/img/slides/Benson/Background_03.png">
<h1>Recommendations</h1>
</section>

<section data-background="/assets/img/slides/Benson/Background_02.png">
<h3>Recommendation #1</h3>
The Common Sense Approach
<table><tr><td>
<ul>
<li class="fragment">Spring Weekdays 4-8pm</li>
<li class="fragment">Penn Station</li>
<li class="fragment">Grand Central</li>
<li class="fragment">Time Square</li>
<li class="fragment">etc.</li>
</ul>
</td><td>
<img data-src="/assets/img/slides/Benson/Chart_05.png"/>
</td></tr></table>
</section>


<section data-background="/assets/img/slides/Benson/Background_02.png">
<h3>Recommendation #2</h3>
Quality over Quantity Approach<br/>
(next steps)
<table><tr><td>
<ul>
<li class="fragment">Location targeting<br/>(Tech companies, Universities, Pro-women Groups)</li>
<li class="fragment">Find highest traffic stations in nearby zip codes</li>
</ul>
</td><td>
<img data-src="/assets/img/slides/Benson/Chart_06.png"/>
</td></tr></table>
</section>

<section data-background="/assets/img/slides/Benson/Background_02.png">
<h3>Recommendation #3</h3>
The Opportunistic Approach<br/>
(next steps)
<table><tr><td>
<ul>
<li class="fragment">Events targeting (Tech/Women’s Conferences, Concerts)</li>
<li class="fragment">Identify events date/time/location and stations nearby</li>
</ul>
</td><td>
<img data-src="/assets/img/slides/Benson/Chart_07a.png"/>
<img data-src="/assets/img/slides/Benson/Chart_07b.png"/>
</td></tr></table>
</section>
<section data-background="/assets/img/slides/Benson/Background_03.png">
<h1>Thank You</h1>
</section>
