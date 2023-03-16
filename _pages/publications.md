---
layout: page
permalink: /press/
title: Press
description: List of publications and events showcasing RepMat.
years: [2023, 2022, 2021]
nav: true
nav_order: 3
---
<!-- _pages/publications.md -->

<br>


<h4><b>Publications</b></h4>
<h5>Journal articles, Book chapters, Conference papers</h5>
<br>

<div class="publications">

{%- for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f papers -q @*[year={{y}}]* %}
{% endfor %}

</div>
<br>
<br>


<h4><b>Events</b></h4>
<h5>International conferences, talks, presentations</h5>
<br>

<div class="publications">

{%- for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f events -q @*[year={{y}}]* %}
{% endfor %}

</div>
