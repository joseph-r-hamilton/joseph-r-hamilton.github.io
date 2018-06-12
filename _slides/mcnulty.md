---
title: Presentation in Jekyll
description: Web presentation in Jekyll using Reveal.js
date: 2018-02-20
layout: slide
transition: page
theme: black_hex
center: false
width: 90% 
height: 90%
---


<style>
.reveal h1 h2 h3{
text-align: center;
}
.reveal p{
text-align: left;
}
.reveal .leftol{
display: block;
}
.reveal ul{
text-align: left;
}
</style>

{% comment %} Slide   1 {% endcomment %}
<section data-transition="none">
<h1 class="fragment fade-down">Chicago Crime Scene</h1>
<h3 class="fragment fade-down">Arrest Prediction</h3>
<img class="fragment fade-in" alt="picture" src="/assets/img/slides/McNulty/owl.jpg">
</section>
<section>
<h1>Chicago Crime Scene</h1>
<h3>Arrest Prediction</h3>
<img alt="picture" src="/assets/img/slides/McNulty/owl-caged.jpg">
</section>

{% comment %} Slide   2 {% endcomment %}
<section>
<h1><small>Chicago Crime Scene</small></h1>
<h3><small>Project Goals</small></h3>
<ul>
<li class="fragment fade-left">Goal: Provide predictive guidance of likelihood of arrest.</li>
<li class="fragment fade-left">Plan: determine rate of arrest per crime reports.</li>
<li class="fragment fade-left">Method: use the dataset from the Chicago Data Portal.</li>
</ul>
</section>

{% comment %} Slide   2 {% endcomment %}
<section>
<h1><small>Chicago Data Portal</small></h1>
<ul>
<li class="fragment fade-left">Dataset available via the Socrata Open Data API<br/>(and bulk downloads).</li>
<li class="fragment fade-left">Developed a SODA to SQL schema converter for import.</li>
<li class="fragment fade-left">SODA access permits daily updates.</li>
</ul>
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
<img alt="picture" src="/assets/img/slides/McNulty/SODA_mascot.png" width="50%">
</div>
<div class="col">
<img alt="picture" src="/assets/img/slides/McNulty/sqlalchemy.png" width="80%">
</div>
<div class="col">
<img alt="picture" src="/assets/img/slides/McNulty/postgresql.png" width="80%">
</div>
</div>
</section>

{% comment %} Slide   2 {% endcomment %}
<section>
<h1><small>Initial Models</small></h1>
<ul>
<li class="fragment fade-left">Initial modeling seemed to show performance above baseline (of 80% accuracy).</li>
<li class="fragment fade-left">Client wasn't necessarily impressed.</li>
</ul>
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
<img alt="picture" src="/assets/img/slides/McNulty/Chart_MVP_01b.png" width="80%">
</div>
<div class="col">
<img alt="picture" src="/assets/img/slides/McNulty/Chart_MVP_02b.png" width="80%">
</div>
</div>
</section>

{% comment %} Slide   2 {% endcomment %}
<section>
<h1><small>Much about Metrics</small></h1>
<ul>
<li class="fragment fade-left">Accuracy: Client already knows "most of the time" they don't get arrested.</li>
<li class="fragment fade-left">Concern #1: If I say no arrest, and I get that wrong, they lose "staff".  I need to be Sensitive of that.</li>
<li class="fragment fade-left">Concern #2: If I say arrest, and I get that wrong, they lose "business".  So I need to be Precise.</li>
</ul>
</section>

{% comment %} Slide   3 {% endcomment %}
<section>
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
<h2><small>Crime by Communities</small></h2>
<ul>
<li>The dataset calls these "Location Areas".</li>
<li>These are the colloquial parts of town.</li>
<li>This is also the most general breakout.</li>
</ul>
</div>

<div class="col">
<iframe style="float:right" width="360" height="500" src="/assets/html/mcnulty/areas1.html"></iframe>
</div>

</div>
</section>

{% comment %} Slide   4 {% endcomment %}
<section>
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
<h2><small>Crime by Wards</small></h2>
<ul>
<li>The political districts</li>
<li>A bit more granular</li>
<li>Politicians draw much more convoluted shapes.</li>
</ul>
</div>

<div class="col">
<iframe style="float:right" width="360" height="500" src="/assets/html/mcnulty/wards1.html"></iframe>
</div>

</div>
</section>

{% comment %} Slide   5 {% endcomment %}
<section>
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
<h2><small>Crime by the Beat</small></h2>
<ul>
<li>Distrcit and Beat per the CPD.</li>
<li>District and Beat are they only purely heirarchical geo features.</li>
<li>Beat is much more granular.</li>
</ul>
</div>

<div class="col">
<iframe style="float:right" width="360" height="500" src="/assets/html/mcnulty/beats1.html"></iframe>
</div>

</div>
</section>

{% comment %} Slide   5 {% endcomment %}
<section>
<h1><small>Chicago Crime Scene</small></h1>
<ul>
<li class="fragment fade-left">Geo Data was unpersuasive.</li>
<li class="fragment fade-left">Time Data was meager.</li>
<li class="fragment fade-left">Two remaining features proved very useful:</li>
<ul>
<li class="fragment fade-left">Location DESCRIPTION</li>
<li class="fragment fade-left">Crime DESCRIPTION</li>
</ul>
</ul>
</section>

{% comment %} Slide   1 {% endcomment %}
<section data-transition="none">
<h1 class="fragment fade-down">Chicago Crime Scene</h1>
<h3 class="fragment fade-down">Model Results</h3>
<img class="fragment fade-in" alt="picture" src="/assets/img/slides/McNulty/Summary_Metrics.png" width="35%">
</section>

{% comment %} Slide   6 {% endcomment %}
<section>
<h1 class="fragment fade-down"><small>Arrest Predictor</small></h1>
<iframe class="fragment fade-down" style="background: #FFFFFF" width="80%" height="400"  src="http://127.0.0.1:5000/"></iframe>
</section>

{% comment %} Slide   END {% endcomment %}
<section>
<img alt="picture" src="/assets/img/slides/McNulty/jailbreak_800.png" width="60%">
</section>

{% comment %} Slide   Appendix {% endcomment %}
<section>
<h1><small>Appendix</small></h1>
<h3>Chicago Crime Scene</h3>
<img alt="picture" src="/assets/img/slides/McNulty/Chart_01.png" width="90%">
</section>

{% comment %} Slide   Appendix {% endcomment %}
<section>
<h3>Chicago Crime Scene</h3>
<img alt="picture" src="/assets/img/slides/McNulty/Chart_02.png" width="60%">
</section>

{% comment %} Slide   Appendix {% endcomment %}
<section>
<h3>Chicago Crime Scene</h3>
<img alt="picture" src="/assets/img/slides/McNulty/Chart_03.png" width="60%">
</section>

{% comment %} Slide   Appendix {% endcomment %}
<section>
<h3>Chicago Crime Scene</h3>
<img alt="picture" src="/assets/img/slides/McNulty/Chart_04.png" width="60%">
</section>

{% comment %} Slide   Appendix {% endcomment %}
<section>
<h3>Chicago Crime Scene</h3>
<img alt="picture" src="/assets/img/slides/McNulty/Chart_05.png" width="60%">
</section>

{% comment %} Slide   Appendix {% endcomment %}
<section>
<h3>Chicago Crime Scene</h3>
<img alt="picture" src="/assets/img/slides/McNulty/Chart_06.png" width="60%">
</section>
