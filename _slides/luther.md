---
title: Linear Regression - Neighborhood Longevity
description: Web Presentation of the Luther Project
date: 2018-02-02T00:00:00.000Z
layout: slide
theme: beige
transition: slide
parallaxBackground:
  image: /assets/img/slides/panoramic-02.jpg
  size: 2400px 800px
  horizontal: 50
  vertical: 0
---

<section>
  <h1>Project Luther</h1>
  <h1 class="fragment zoom-in"><small>Predicting Neighborhood Stability via Property Tax Assessment Data</small></h1>
</section>

<section>
  <h1><small>Project Goals</small></h1>
  <ul>
    <li class="fragment fade-left">Can we predict neighborhood stability?</li>
    <li class="fragment fade-left">Let's use time since the last sale of a house as a proxy.</li>
    <li class="fragment fade-left">Can we predict this from available property tax data?</li>
    <li class="fragment fade-left">First, can we accumulate enough property tax data?</li>
  </ul>
</section>

<section>
<h1><small>Web Scraping</small></h1>

<style>
.container{
    display: flex;
}
.col{
    flex: 1;
}
</style>

<div class="container">

<div class="col">
<ul>
  <li class="fragment fade-left" data-fragment-index="1">The Will County website has the data we need.</li>
  <li class="fragment fade-left" data-fragment-index="3">Extracting data is straightforward if you have the address or PIN.</li>
  <li class="fragment fade-left" data-fragment-index="4">But guessing these can be slow.</li>
</ul>
</div>

<div class="col">
<img class="fragment fade-left" data-fragment-index="2" alt="chart" src="/assets/img/slides/Luther/WillCo_Web.png">
</div>

</div>
</section>

<section>
<h1><small>Web Scraping</small></h1>

<style>
.container{
    display: flex;
}
.col{
    flex: 1;
}
</style>

<div class="container">

<div class="col">
<h3 class="fragment">Methods and Tools</h3>
<ul>
<li class="fragment fade-left">A bit of AJAX Hijacking</li>
  <li class="fragment fade-left">Scrapy Spiders - parallel</li>
  <li class="fragment fade-left">MongoDB for storage</li>
</ul>
</div>

<div class="col">
<h3 class="fragment">Results</h3>
<ul>
  <li class="fragment fade-left">~60,000 records</li>
  <li class="fragment fade-left">~25% of all households</li>
  <li class="fragment fade-left">Is this enough?</li>
  <li class="fragment fade-left">Yes, as we'll see...</li>
</ul>
</div>

</div>
</section>


<section>
  <h1><small>Linear Regression</small></h1>
  <ul>
    <li class="fragment fade-left">Can we predict "Longevity" (time since last sale)?</li>
    <li class="fragment fade-left">Not very well.</li>
    <li class="fragment fade-left">The mean "Longevity" is about 13 years.</li>
    <li class="fragment fade-left">The typical error of the better models was 5 years.</li>
  </ul>
</section>


<section>
<style>
.container{
    display: flex;
}
.col{
    flex: 1;
}
</style>
  <h1><small>Learning Curves</small></h1>
<div class="container">
<div class="col">  
  <img class="fragment fade-up" alt="chart" width="100%" src="/assets/img/slides/Luther/Chart_01.png">
</div>
<div class="col">  
  <ul>
    <li class="fragment fade-left">The model converges quickly.</li>
    <li class="fragment fade-left">More data is likely not going to help.</li>
  </ul>
</div>
</div>
</section>

<section>
  <h1><small>Learning Curves</small></h1>
  <ul>
    <li class="fragment fade-up">With more data, we continue to see huge variance.</li>
  </ul>
  <img class="fragment fade-up" alt="chart" width="60%" src="/assets/img/slides/Luther/Chart_02.png">
</section>

<section>
<style>
.container{
    display: flex;
}
.col{
    flex: 1;
}
</style>
  <h1><small>Poorly correlated features?</small></h1>
<div class="container">
<div class="col">  
<small>Correlation Matrix Snippet</small>
  <img  alt="chart" height="70%" src="/assets/img/slides/Luther/Chart_03.png">
</div>
<div class="col">  
  <ul>
    <li class="fragment fade-left">Most of our features have poor correlation with our target.</li>
    <li class="fragment fade-left">Feature evaluation confirms Sale Amount is the strongest signal.</li>
  </ul>
</div>
</div>
</section>


<section>
  <h1><small>Linear Regression - Assumptions</small></h1>
  <p class="fragment fade-left">Have we met the key assumptions for Linear Regression?</p>
  <ul>
    <li class="fragment highlight-blue">Linear relationship</li>
    <li class="fragment highlight-red">Multivariate normality</li>
    <li class="fragment highlight-red">No or little multicollinearity</li>
    <li class="fragment highlight-blue">No auto-correlation</li>
    <li class="fragment highlight-red">Homoscedasticity</li>
  </ul>
</section>

<section>
  <h1><small>Homoscedasticity</small></h1>
  <img class="fragment fade-up" alt="chart" width="60%" src="/assets/img/slides/Luther/Chart_04.png">
</section>

<section>
  <h1><small>Collinearity</small></h1>
  <ul>
    <li class="fragment fade-left">There were several groupings or clusters of similar things among the features.</li>
    <li class="fragment fade-left">For each of these all but one of the features were removed.</li>
  </ul>
</section>

<section>
<section>
  <h1><small>Normally distributed features?</small></h1>
  <ul>
    <li class="fragment fade-left">Several features were transformed via a log function.</li>
    <li class="fragment fade-left">Outlier removal followed.</li>
  </ul>
  </section>
  <section>
    <h1><small>Normally distributed features?</small></h1>
    <img class="fragment fade-up" alt="chart" width="90%" src="/assets/img/slides/Luther/Chart_05.png">
  </section>

</section>


<section>
<section>
  <h1><small>Normally distributed target?</small></h1>
  <ul>
    <li class="fragment fade-left">The target also wasn't very guassian.</li>
    <li class="fragment fade-left">Transforming didn't improve the modeling.</li>
  </ul>
</section>
<section>
  <h1><small>Normally distributed target?</small></h1>
  <img class="fragment fade-up" alt="chart" width="60%" src="/assets/img/slides/Luther/Chart_06.png">
</section>
<section>
  <h1><small>Normally distributed target?</small></h1>
  <img class="fragment fade-up" alt="chart" width="60%" src="/assets/img/slides/Luther/Chart_07.png">
</section>
</section>
