---
title: Anomaly Detection with Reddit Users
description: Web presentation on Anomaly Detection
date: 2018-04-01T00:00:00.000Z
layout: slide
theme: simple
transition: fade
width: 90%
height: 90%
center: false
---
<link rel="stylesheet" href="/assets/css/custom1.css" />

{% comment %} SLIDE 01 {% endcomment %}
<section>
  <div class="bbox">
    <h2>Anomaly Detection<br/>Analysis of Reddit Users</h2>
    <hr class="shadow">
    <p class="largefnt" style="text-align: center;">Joseph Hamilton</p>
    {% comment %}
    <p class="mediumfnt" style="text-align: center;background-color: lightgrey;margin:10%;">Follow this presentation on your device: <a href="https://goo.gl/SLr7Gx">https://goo.gl/SLr7Gx</a></p>
    {% endcomment %}
  </div>
</section>


{% comment %} SLIDE 02 {% endcomment %}
<section>
  <div class="slideheader">
    <h3>Anomaly Detection - Definition</h3>
  </div>
  <div class="sliderow">
  <img src="/assets/img/slides/Kojak/flowers.jpg"  width="100%" alt="Flowers">  
  </div>
  <div class="slidefooter">
  </div>
</section>

{% comment %} SLIDE 03 {% endcomment %}
<section>
  <style>
    .flexrow {
      display: flex;
      flex-direction: row;
      align-items: center;
    }

    .flexcol {
      display: flex;
      flex-direction: column;
      align-items: center;
    }

    .flexitem {
      flex: 1;
    }
  </style>
  <div class="slideheader">
    <h3>Anomaly Detection - Common Applications</h3>
  </div>
  <div class="sliderow">
  <div class="flexrow">
  <div class="flexcol" style="flex:2">
  <div class="flexrow">
  <img class="fragment" src="/assets/img/slides/Kojak/fraud.jpg"  alt="Fraud">  
  </div>
  <div class="flexrow">
  <img class="fragment" src="/assets/img/slides/Kojak/intrusion.png"  alt="Hack">  
  </div>
  </div>
  <div class="flexcol" style="flex:2">
  <div class="flexrow">
  <img class="fragment" src="/assets/img/slides/Kojak/fault.jpg"  alt="Fault">  
  </div>
  <div class="flexrow">
  <img class="fragment" src="/assets/img/slides/Kojak/disease.jpg"  alt="Disease">  
  </div>
  </div>
  </div>
  </div>
  <div class="slidefooter">
  </div>
</section>

{% comment %} SLIDE 04 {% endcomment %}
<section>
  <div class="slideheader">
    <h3>The Problem of Trolls on Reddit</h3>
  </div>
  <div class="sliderow">
  <img src="/assets/img/slides/Kojak/internet-troll.jpg"  width="75%" alt="Troll">  
  </div>
  <div class="slidefooter">
  </div>
</section>


{% comment %} SLIDE 05 {% endcomment %}
<section>
  <div class="slideheader">
    <h3>Platforms, Tools and Methods</h3>
  </div>
  <div class="sliderow">
  <div class="bbox">
  <img class="fragment fade-down" src="/assets/img/slides/Kojak/Kojak_Tools_01.png" width="18%" alt="Lotsa Logos">  
  </div>
  </div>
  <div class="slidefooter">
  </div>
</section>
<section>
  <div class="slideheader">
    <h3>Platforms, Tools and Methods</h3>
  </div>
  <div class="sliderow">
  <div class="bbox">
  <img style="opacity: 0.125" src="/assets/img/slides/Kojak/Kojak_Tools_01.png" width="18%" alt="Lotsa Logos">  
  <img class="fragment fade-down" src="/assets/img/slides/Kojak/Kojak_Tools_02.png" width="18%" alt="Lotsa Logos">  
  </div>
  </div>
  <div class="slidefooter">
  </div>
</section>
<section>
  <div class="slideheader">
    <h3>Platforms, Tools and Methods</h3>
  </div>
  <div class="sliderow">
  <div class="bbox">
  <img style="opacity: 0.125" src="/assets/img/slides/Kojak/Kojak_Tools_01.png" width="18%" alt="Lotsa Logos">  
  <img style="opacity: 0.125" src="/assets/img/slides/Kojak/Kojak_Tools_02.png" width="18%" alt="Lotsa Logos">  
  <img class="fragment fade-down" src="/assets/img/slides/Kojak/Kojak_Tools_03.png" width="18%" alt="Lotsa Logos">  
  </div>
  </div>
  <div class="slidefooter">
  </div>
</section>
<section>
  <div class="slideheader">
    <h3>Platforms, Tools and Methods</h3>
  </div>
  <div class="sliderow">
  <div class="bbox">
  <img style="opacity: 0.125" src="/assets/img/slides/Kojak/Kojak_Tools_01.png" width="18%" alt="Lotsa Logos">  
  <img style="opacity: 0.125" src="/assets/img/slides/Kojak/Kojak_Tools_02.png" width="18%" alt="Lotsa Logos">  
  <img style="opacity: 0.125" src="/assets/img/slides/Kojak/Kojak_Tools_03.png" width="18%" alt="Lotsa Logos">  
  <img class="fragment fade-down" src="/assets/img/slides/Kojak/Kojak_Tools_04.png" width="18%" alt="Lotsa Logos">  
  </div>
  </div>
  <div class="slidefooter">
  </div>
</section>
<section>
  <div class="slideheader">
    <h3>Platforms, Tools and Methods</h3>
  </div>
  <div class="sliderow">
  <div class="bbox">
  <img style="opacity: 0.125" src="/assets/img/slides/Kojak/Kojak_Tools_01.png" width="18%" alt="Lotsa Logos">  
  <img style="opacity: 0.125" src="/assets/img/slides/Kojak/Kojak_Tools_02.png" width="18%" alt="Lotsa Logos">  
  <img style="opacity: 0.125" src="/assets/img/slides/Kojak/Kojak_Tools_03.png" width="18%" alt="Lotsa Logos">  
  <img style="opacity: 0.125" src="/assets/img/slides/Kojak/Kojak_Tools_04.png" width="18%" alt="Lotsa Logos">  
  <img class="fragment fade-down" src="/assets/img/slides/Kojak/Kojak_Tools_05.png" width="18%" alt="Lotsa Logos">  
  </div>
  </div>
  <div class="slidefooter">
  </div>
</section>

{% comment %} SLIDE 06 {% endcomment %}
<section data-transition="none-out">
  <div class="slideheader">
    <h3>Troll Hunt - General Approach</h3>
  </div>
  <div class="sliderow">
  <img src="/assets/img/slides/Kojak/Flowchart2_0.png" width="100%" alt="Flow Chart">  
  </div>
  <div class="slidefooter">
  </div>
</section>
<section data-transition="none">
  <div class="slideheader">
    <h3>Troll Hunt - General Approach</h3>
  </div>
  <div class="sliderow">
  <img src="/assets/img/slides/Kojak/Flowchart2_1.png" width="100%" alt="Flow Chart">  
  </div>
  <div class="slidefooter">
  </div>
</section>
<section data-transition="none">
  <div class="slideheader">
    <h3>Troll Hunt - General Approach</h3>
  </div>
  <div class="sliderow">
  <img src="/assets/img/slides/Kojak/Flowchart2_2.png" width="100%" alt="Flow Chart">  
  </div>
  <div class="slidefooter">
  </div>
</section>
<section data-transition="none">
  <div class="slideheader">
    <h3>Troll Hunt - General Approach</h3>
  </div>
  <div class="sliderow">
  <img src="/assets/img/slides/Kojak/Flowchart2_3.png" width="100%" alt="Flow Chart">  
  </div>
  <div class="slidefooter">
  </div>
</section>
<section data-transition="none">
  <div class="slideheader">
    <h3>Troll Hunt - General Approach</h3>
  </div>
  <div class="sliderow">
  <img src="/assets/img/slides/Kojak/Flowchart2_4.png" width="100%" alt="Flow Chart">  
  </div>
  <div class="slidefooter">
  </div>
</section>
<section data-transition="none">
  <div class="slideheader">
    <h3>Troll Hunt - General Approach</h3>
  </div>
  <div class="sliderow">
  <img src="/assets/img/slides/Kojak/Flowchart2_5.png" width="100%" alt="Flow Chart">  
  </div>
  <div class="slidefooter">
  </div>
</section>


{% comment %} SLIDE 07 {% endcomment %}
<section>
<div class="bbox">
  <div class="slideheader">
    <h3>Troll Hunt - Algorithms</h3>
  </div>
  <div class="sliderow">
  <p/>
  <p class="fragment">Agglomerative Clustering</p>
  <p class="fragment">DBSCAN</p>
  <p class="fragment">Isolation Forest</p>
  <p class="fragment">One-Class SVM</p>
  </div>
  <div class="slidefooter">
  </div>
  </div>
</section>


{% comment %} SLIDE 08 {% endcomment %}
<section>
  <style>
    .container {
      display: flex;
    }

    .col {
      flex: 3;
    }
  </style>

  <div class="bbox">
    <div class="slideheader">
      <h3>Troll Hunt - Sample Anomaly</h3>
    </div>
    <div class="sliderow">
      <div class="container">
        <div class="col">
        </div>
        <div class="col">
          <img src="/assets/img/slides/Kojak/Rob_T_Firefly.png" alt="anomaly">
        </div>
        <div class="col">
        </div>
      </div>
      <div class="slidefooter">
      </div>
    </div>
  </div>
</section>
<section>
  <style>
    .container {
      display: flex;
    }

    .col {
      flex: 3;
    }

table { text-align: center; }

table {border-collapse: collapse;  width: 70%; margin: 0 auto 5rem;}

th, td { padding: 1.5rem; font-size: 1.3rem; }

tr {background: hsl(50, 50%, 80%); }

tr, td { transition: .4s ease-in; } 

tr:first-child {background: hsla(12, 100%, 40%, 0.5); }

tr:nth-child(even) { background: hsla(50, 50%, 80%, 0.7); }

td:empty {background: hsla(50, 25%, 60%, 0.7); }

tr:hover:not(#firstrow), tr:hover td:empty {background: #ff0; pointer-events: visible;}
tr:hover:not(#firstrow) { transform: scale(1.2); font-weight: 700; box-shadow: 0px 3px 7px rgba(0, 0, 0, 0.5);}

  </style>

  <div class="bbox">
    <div class="slideheader">
      <h3>Troll Hunt - Sample Anomaly</h3>
    </div>
    <div class="sliderow">
      <div class="container">
        <div class="col">
          <p class="largefnt fragment" data-fragment-index="2" style="text-align: center;">This is <b>not</b> a troll.</p>
          <img class="fragment" data-fragment-index="2" src="/assets/img/slides/Kojak/troll_01.png" width="400px" alt="troll">
        </div>
        <div class="col">
          <img src="/assets/img/slides/Kojak/Rob_T_Firefly_small.png" alt="anomaly">
<table class="fragment" data-fragment-index="1" id="anomaly">
<tr id="firstrow"><td><b>Author</b></td><td>Rob_T_Firefly</td></tr>
<tr><td><b>Total Comments</b></td><td>231</td></tr>
<tr><td><b>Total Subreddits</b></td><td>76</td></tr>
<tr><td><b>Average Score</b></td><td>33.82</td></tr>
<tr><td><b>Total Gilded</b></td><td>2</td></tr>
</table>
        </div>
        <div class="col">
          <p class="largefnt fragment" data-fragment-index="3" style="text-align: center;">This is a treasure.</p>
          <img class="fragment" data-fragment-index="3" src="/assets/img/slides/Kojak/troll_02.jpg" width="400px" alt="treasure">
        </div>
      </div>
      <div class="slidefooter">
      </div>
    </div>
  </div>
</section>

{% comment %} SLIDE 09 {% endcomment %}
<section>
  <style>
    .flexrow {
      display: flex;
      flex-direction: row;
      align-items: center;
    }

    .flexcol {
      display: flex;
      flex-direction: column;
      align-items: center;
    }

    .flexitem {
      flex: 1;
    }
  </style>
  <div class="slideheader">
    <h3>Anomalies - Not Always Bad!</h3>
  </div>
  <div class="sliderow">
  <div class="flexrow">
  <div class="flexcol" style="flex:2">
  <div class="flexrow">
<right>
  <img class="fragment" src="/assets/img/slides/Kojak/high_performer.jpg" width="80%" alt="Performer">  
</right>
  </div>
  <div class="flexrow">
  </div>
  </div>
  <div class="flexcol" style="flex:2">
  <div class="flexrow">
  <img class="fragment" src="/assets/img/slides/Kojak/emerging_trends.jpg"  alt="Trends">  
  </div>
  <div class="flexrow">
  </div>
  </div>
  </div>
  <p class="fragment">Sometimes surprises are good!</p>
  </div>
  <div class="slidefooter">
  </div>
</section>




{% comment %} SLIDE 10 {% endcomment %}
<section>
  <style>
    .container {
      display: flex;
    }

    .col {
      flex: 2;
    }
  </style>

  <div class="bbox">
    <div class="slideheader">
      <h3>Joseph Hamilton</h3>
    </div>
    <div class="sliderow">
      <div class="container">
        <div class="col">
        <img src="/assets/img/slides/Kojak/contact.png" width="400px" alt="stitch in time saves nine">
        </div>
        <div class="col">
          <img src="/assets/img/slides/Kojak/Joe2.jpg" width="400px" alt="stitch in time saves nine">
        </div>
      </div>
      <div class="slidefooter">
      </div>
    </div>
  </div>
</section>
