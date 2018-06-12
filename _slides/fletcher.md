---
title: Presentation in Jekyll
description: Web presentation in Jekyll using Reveal.js
date: 2018-03-09
layout: slide
theme: league
center: false
transition: convex
width: 90% 
height: 95%
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
</style>

<section>

{% comment %} Slide   01a {% endcomment %}
<section data-transition="none-out">
<style>
.container{
    display: flex;
}
.col{
    flex: 1;
}
</style>

<div class="container">
<div class="col" style="flex:2">
</div>

<div class="col">
<h2 style="text-align:left" ><strong> </strong><small> </small></h2>
<h2 style="text-align:left" class="fragment fade-in"><strong>S</strong><small>ocial</small></h2>
<h2 style="text-align:left" class="fragment fade-in"><strong>M</strong><small>edia</small></h2>
<h2 style="text-align:left" class="fragment fade-in"><strong>A</strong><small>ggregative</small></h2>
<h2 style="text-align:left" class="fragment fade-in"><strong>S</strong><small>implifying</small></h2>
<h2 style="text-align:left" class="fragment fade-in"><strong>H</strong><small>elper</small></h2>
</div>

<div class="col" style="flex:2">
</div>

</div>
</section>

{% comment %} Slide   01b {% endcomment %}
<section data-transition="none-in convex-out">
<h1><big>S.M.A.S.H.</big></h1>
<img alt="picture" src="/assets/img/slides/Fletcher/Smash.gif" width="80%">
</section>

{% comment %} Slide   02 {% endcomment %}
<section data-transition="none-in convex-out">
<h2 class="fragment fade-in" data-fragment-index="1">Social Media: Reddit</h2>
<center>
<img class="fragment fade-in" data-fragment-index="1" alt="picture" src="/assets/img/slides/Fletcher/SnooCivilWar.png" width="50%">
</center>
<ul>
<li class="fragment fade-in">Total Users: over a quarter billion</li>
<li class="fragment fade-in">Over 850,000 subreddits</li>
<li class="fragment fade-in">Average Daily Comments: over 5 million</li>
</ul>
</section>

{% comment %} Slide   03a {% endcomment %}
<section data-transition="none-out">
<h2 class="fragment fade-in" data-fragment-index="1">Aggregation</h2>
<ul>
<li class="fragment fade-in" data-fragment-index="2">Reddit API available for streaming</li>
<li class="fragment fade-in" data-fragment-index="3">Daily and Monthly archives available in JSON format.</li>
<p> </p>
<p> </p>
</ul>
<center>
<img class="fragment fade-in" data-fragment-index="3" alt="picture" src="/assets/img/slides/Fletcher/MisterKnife.png" width="15%">
</center>
</section>

{% comment %} Slide   03b {% endcomment %}
<section data-transition="none">
<h2>Aggregation</h2>
<ul>
<li>Reddit API available for streaming</li>
<li>Daily and Monthly archives available in JSON format.</li>
<li class="fragment fade-in" data-fragment-index="4">A single day loaded into a MongoDB collection.</li>
<p> </p>
<p> </p>
</ul>
<center>
<img alt="picture" src="/assets/img/slides/Fletcher/json-logo.png" width="25%">
<img class="fragment fade-in" data-fragment-index="4" alt="picture" src="/assets/img/slides/Fletcher/Magneto.jpg" width="25%">
</center>
</section>

{% comment %} Slide   03c {% endcomment %}
<section data-transition="none-in convex-out">
<h2>Aggregation</h2>
<ul>
<li>Reddit API available for streaming</li>
<li>Daily and Monthly archives available in JSON format.</li>
<li>A single day loaded into a MongoDB collection.</li>
<li class="fragment fade-in" data-fragment-index="5">Over 3.5 million comments.</li>
</ul>
<center>
<img alt="picture" src="/assets/img/slides/Fletcher/json-logo.png" width="25%">
<img alt="picture" src="/assets/img/slides/Fletcher/mongodb.png" width="25%">
</center>
</section>

{% comment %} Slide   04 {% endcomment %}
<section data-transition="none-in convex-out">
<h2 class="fragment fade-in" data-fragment-index="1">Simplification</h2>
<center>
<img class="fragment fade-in" data-fragment-index="3" alt="picture" src="/assets/img/slides/Fletcher/DrStrange.jpg" width="50%">
</center>
<ul>
<li class="fragment fade-in" data-fragment-index="2">How do we simplify a large collection of documents?</li>
<li class="fragment fade-in" data-fragment-index="3">Dimensionality Reduction</li>
<li class="fragment fade-in" data-fragment-index="4">Using NLP techniques/algorithms: LDA, LSA, NMF, etc.</li>
<li class="fragment fade-in" data-fragment-index="5">S.M.A.S.H. works best with TF-IDF and NMF.</li>
</ul>
</section>

{% comment %} Slide   05 {% endcomment %}
<section>
<h2 class="fragment fade-in" data-fragment-index="1">Simplification - a Demonstration</h2>
<ul>
<li class="fragment fade-in" data-fragment-index="2">A small sample chosen for demonstration - three subreddits:</li>
<ul>
<li class="fragment fade-in" data-fragment-index="2">marvelstudios</li>
<li class="fragment fade-in" data-fragment-index="2">dataisbeautiful</li>
<li class="fragment fade-in" data-fragment-index="2">Competitiveoverwatch</li>
</ul>
</ul>
</section>

{% comment %} Slide   06 {% endcomment %}
<section>
<h2 class="fragment fade-in">t-SNE Plot</h2>
<iframe class="fragment fade-in" style="float:center" width="1300" height="700" src="/assets/html/fletcher/Reddit_X03a_viz.html"></iframe>
</section>

{% comment %} Slide   07 {% endcomment %}
<section>
<h2 class="fragment fade-in">Intertopic Distance Map</h2>
<iframe class="fragment fade-in" style="float:center" width="1300" height="700" src="/assets/html/fletcher/Reddit_X03b_viz.html"></iframe>
</section>

{% comment %} Slide   08 {% endcomment %}
<section>
<h2 class="fragment fade-in">Helper - Topic Identification</h2>
<ul>
<li class="fragment fade-in">man ant iron spider strange doctor space hawkeye wasp shield</li>
<center class="fragment fade-in">Ant Man, Iron Man, Spider Man, Doctor Strange, Hawkeye</center>
<center class="fragment fade-in">Avengers - Men</center>
<li class="fragment fade-in">trailer war infinity avenger movie marvel cap wanda vision black</li>
<center class="fragment fade-in">Infinity War Trailer</center>
</ul>
</section>

{% comment %} Slide  09 Ribbon-01a {% endcomment %}
<section data-transition="none-out">
<h3 class="fragment fade-in">Helper - Time Channel Plot</h3>
<center>
<iframe class="fragment fade-in" style="float:center" width="1300" height="800" src="/assets/html/fletcher/ribbon_01a.html"></iframe>
</center>
</section>

{% comment %} Slide  09 Ribbon-01b {% endcomment %}
<section data-transition="none-in convex-out">
<h3>Helper - Time Channel Plot</h3>
<center>
<iframe style="float:center" width="1300" height="800" src="/assets/html/fletcher/ribbon_01b.html"></iframe>
</center>
</section>

{% comment %} Slide   10 {% endcomment %}
<section>
<h2 class="fragment fade-in">Helper - Front Page Topics</h2>
<ul>
<li class="fragment fade-in">tide ad pod commercial eat super bowl clean detergent meme america superbowl clothe company actually roll watch buy campaign strange</li>
<center class="fragment fade-in">Super Bowl Commercials or Tide Pod Meme</center>
<li class="fragment fade-in">good pretty really bot look point thing luck bad bitcoin job work idea oh damn play little old hope guess</li>
<center class="fragment fade-in">BitCoin</center>
</ul>
</section>

{% comment %} Slide 11  Ribbon-02a {% endcomment %}
<section data-transition="none-out">
<h3 class="fragment fade-in">Helper - Time Channel Plot</h3>
<center>
<iframe class="fragment fade-in" style="float:center" width="1300" height="800" src="/assets/html/fletcher/ribbon_02a.html"></iframe>
</center>
</section>

{% comment %} Slide 11  Ribbon-02b {% endcomment %}
<section data-transition="none-in convex-out">
<h3>Helper - Time Channel Plot</h3>
<center>
<iframe style="float:center" width="1300" height="800" src="/assets/html/fletcher/ribbon_02b.html"></iframe>
</center>
</section>

<li class="fragment fade-in" data-fragment-index="5">Over 3.5 million comments.</li>

{% comment %} Slide   01 {% endcomment %}
<section>
<h1 class="fragment fade-in" data-fragment-index="1">S.M.A.S.H</h1>
<img class="fragment fade-in" data-fragment-index="1" alt="picture" src="/assets/img/slides/Fletcher/Dancing_Snoo.gif">
</section>

{% comment %} ##### BREAK ##### {% endcomment %}

{% comment %} Appendix   01 {% endcomment %}
<section data-transition="none-in convex-out">
<h2 class="fragment fade-in" data-fragment-index="1">Appendix</h2>
<center>
<img class="fragment fade-in" data-fragment-index="3" alt="picture" src="/assets/img/slides/Fletcher/theDonald.png" width="25%">
</center>
<ul>
<li class="fragment fade-in" data-fragment-index="2">Let's try another group:</li>
<ul>
<li class="fragment fade-in" data-fragment-index="2">news</li>
<li class="fragment fade-in" data-fragment-index="2">worldnews</li>
<li class="fragment fade-in" data-fragment-index="2">politics</li>
<li class="fragment fade-in" data-fragment-index="3">theDonald</li>
</ul>
<li class="fragment fade-in" data-fragment-index="4">Look at that similarity matrix.</li>
<li class="fragment fade-in" data-fragment-index="5">Those guys really are in their own world.</li>
</ul>
</section>

{% comment %} Slide   10 {% endcomment %}
<section>
<h2 class="fragment fade-in">Topics - News and Politics</h2>
<ul>
<li class="fragment fade-in">trump obama market president donald supporter stock economy credit lie </li>
<center class="fragment fade-in">Presidents and the Economy</center>
<li class="fragment fade-in">good bitcoin point thing bad luck pretty job market stock</li>
<center class="fragment fade-in">BitCoin</center>
</ul>
</section>

{% comment %} Slide 11  Ribbon-03a {% endcomment %}
<section data-transition="none-out">
<h3 class="fragment fade-in">Helper - Time Channel Plot</h3>
<center>
<iframe class="fragment fade-in" style="float:center" width="1300" height="800" src="/assets/html/fletcher/ribbon_03a.html"></iframe>
</center>
</section>

{% comment %} Slide 11  Ribbon-03b {% endcomment %}
<section data-transition="none-in convex-out">
<h3>Helper - Time Channel Plot</h3>
<center>
<iframe style="float:center" width="1300" height="800" src="/assets/html/fletcher/ribbon_03b.html"></iframe>
</center>
</section>

</section>
