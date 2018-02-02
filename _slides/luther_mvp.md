---
title: Luther MVP
description: MVP of the Luther Project
date: 2018-01-29T00:00:00.000Z
layout: slide
theme: league
transition: slide
parallaxBackground:
  image: /assets/img/slides/panoramic-01.jpg
  size: 1920px 789px
  horizontal: 50
  vertical: 0
---

<section>
  <h1>Project Luther</h1>
  <h2>Predicting Neighborhood Stability via Property Tax Assessment Data</h2>
</section>

<section>
  <h2>Data Source Evaluation</h2>
  <h3>Candidates</h3>
  <ul>
    <li>Cook County</li>
    <li>Lake County</li>
    <li>DuPage County</li>
    <li>Will County</li>
  </ul>
</section>

<section>
  <h2>Data Source Evaluation</h2>
  <h3>Selected</h3>
  <ul>
    <li>Will County</li>
    <li>Target: Time since last sale of house.</li>
    <li>Features: Data avaialble on site.</li>
  </ul>
</section>

<section>
  <h1>Will County Website</h1>
  <img alt="chart" src="/assets/img/slides/Luther/WillCo_Web.png">
</section>

<section>
  <h1>Initial Data Scrape</h1>
  <ul>
    <li>5000+ rows scraped</li>
    <li>4000+ rows with target</li>
    <li>1500+ rows selected after cleaning/transforming features</li>
  </ul>
</section>

<section>
  <h1>Initial Regression</h1>
  <ul>
    <li>Weak correlation between target and selected features</li>
    <li>Low adjust R^2 value</li>
  </ul>
</section>

<section>
  <h1>Next Steps</h1>
  <ul>
    <li>Extract more data</li>
    <li>Explore more features</li>
    <li>Explore feature interactions</li>
  </ul>
</section>
