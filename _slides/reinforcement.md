---
title: Reinforcement Learning
description: A brief review of reinforcement learning
date: 2018-03-18
layout: slide
theme: serif
transition: cube
center: false
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


{% comment %} Slide   01 {% endcomment %}
<section>
<h1 class="fragment fade-down">Reinforcement<br/>Learning</h1>
</section>

{% comment %} Slide   02 {% endcomment %}
<section>
<h1><small>Agenda</small></h1>
<ul>
<li class="fragment">Review of Machine Learning</li>
<li class="fragment">Introduction</li>
<li class="fragment">History</li>
<li class="fragment">Demo - Playground</li>
<li class="fragment">Future</li>
</ul>
</section>


{% comment %} Slide   03 {% endcomment %}
<section>
<h2>Review of Machine Learning</h2>
<img class="fragment fade-in" alt="picture" width="50%" src="/assets/img/slides/Reinforcement/LearningTypes-Supervised.png">
<img class="fragment fade-in" alt="picture" width="50%" src="/assets/img/slides/Reinforcement/LearningTypes-Unsupervised.png">
</section>

{% comment %} Slide   04 {% endcomment %}
<section>
<h2>Review of Machine Learning</h2>
<style>
.container{
    display: flex;
}
.col{
    flex: 3;
}
</style>
<div class="container">
<div class="col">
<img class="fragment fade-in" alt="picture" width="80%" src="/assets/img/slides/Reinforcement/rl_1.png">
</div>
<div class="col">
<img class="fragment fade-in" alt="picture" width="80%" src="/assets/img/slides/Reinforcement/rl_2.png">
</div>
<div class="col">
<img class="fragment fade-in" alt="picture" width="80%" src="/assets/img/slides/Reinforcement/rl_3.png">
</div>
</div>
<div class="container">
<div class="col">
<ul>
<li class="fragment">Labled Data</li>
</ul>
</div>
<div class="col">
<ul>
<li class="fragment">Unlabled Data</li>
</ul>
</div>
<div class="col">
<ul>
<li class="fragment">No Data</li>
</ul>
</div>
</div>
</section>

{% comment %} Slide   05 {% endcomment %}
<section>
<h1><small>Introduction</small></h1>
<h2><small>When to use Reinforcement Learning</small></h2>
<ul>
<li class="fragment">Data for learning currently does not exist</li>
<li class="fragment">Or you don’t want to wait to accumulate it<br/>(because delay might be costly)</li>
<li class="fragment">Or the data may change rapidly causing the<br/>outcome to change more rapidly than a typical<br/>model refresh cycle can accommodate.</li>
</ul>
</section>

{% comment %} Slide   06 {% endcomment %}
<section>
<h1><small>Introduction</small></h1>
<h2><small>Typical RL Problems</small></h2>
<ul>
<li class="fragment">Robotic Control</li>
<li class="fragment">AI Game Play</li>
</ul>
</section>


{% comment %} Slide   07 {% endcomment %}
<section>
<h2>RL - How it Works</h2>
<img class="fragment fade-in" alt="picture" width="50%" src="/assets/img/slides/Reinforcement/RL_Process.png">
<ul>
<li class="fragment">Environment - all possible values and steps</li>
<li class="fragment">State - current values</li>
<li class="fragment">Reward - benefit from action</li>
<li class="fragment">Agent - RL Algorithm</li>
<li class="fragment">Policy - Solution or Steps to Maximize Reward</li>
</ul>
</section>

{% comment %} Slide   08 {% endcomment %}
<section>
<h1><small>The RL Bible</small></h1>
<h2><small>Reinforcement Learning:<br/>An Introduction</small></h2>
<h3><small>Richard S. Sutton and Andrew G. Barto</small></h3>
</section>


{% comment %} Slide   09 {% endcomment %}
<section>
<h1><small>RL - History</small></h1>
<ul>
<li class="fragment">1963 - Tic Tac Toe</li>
<li class="fragment">1992 - Backgammon</li>
<li class="fragment">1997 - Deep Blue - Chess</li>
<li class="fragment">2013 - Deep Mind - Atari</li>
<li class="fragment">2016 - AlphaGo - Go</li>
<li class="fragment">2017 - OpenAI Bot - DOTA</li>
</ul>
</section>


{% comment %} Slide   10 {% endcomment %}
<section>
<h1><small>Playground - OpenAI</small></h1>
<ul>
<li class="fragment">Install it from Github:<br/><a href="https://github.com/openai/gym">https://github.com/openai/gym</a></li>
<li class="fragment">Install either PyTorch or Keras</li>
<li class="fragment">PLAY</li>
</ul>
</section>


{% comment %} Slide   XX {% endcomment %}
<section>
<h2><small>CartPole with ACER</small></h2>
<iframe class="fragment fade-in" style="float:center" width="1300" height="700" data-src="/assets/html/reinforcement/CartPole_rewards.html"></iframe>
</section>


{% comment %} Slide   XX {% endcomment %}
<section>
<h2><small>The Future<br/>From MOBA to RTS</small></h2>
<img class="fragment fade-in" alt="picture" width="200%" src="/assets/img/slides/Reinforcement/SC2_logo.gif">
</section>

{% comment %} Slide   XX {% endcomment %}
<section>
<h1><small>Starcraft ][</small></h1>
<ul>
<li class="fragment"><a href="https://deepmind.com/blog/deepmind-and-blizzard-open-starcraft-ii-ai-research-environment/">Deepmind and Blizzard announce open support of Starcraft 2 as an AI research environment.</a></li>
<li class="fragment">PySC2, a Starcraft II machine learning environment by DeepMind in Python.</li>
<li class="fragment">OpenAI interface</li>
</ul>
</section>



{% comment %}
<section>
<h1><small>Title</small></h1>
<ul>
<li class="fragment">Item</li>
</ul>
</section>
{% endcomment %}
