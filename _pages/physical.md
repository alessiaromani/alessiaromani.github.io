---
layout: page
title: Physical Library
permalink: /physicallibrary/
description: Physical part of RepMat Library
nav: false
nav_order: 2
display_categories: [Physical Materials Library, Physical Product Library]
horizontal: false
---

The vhysical part of the library focuses on a direct approach with materials by interacting with them through the senses.
Physical material samples, part cut-offs, possible products and applications can be directly touched and experienced by the users, supporting experiential learning approaches. Furthermore, the hands-on activities in replicating or improving this part is also meant to let the users directly experience and learn how to exploit these materials and technologies by using them in first person.

The physical structures contain the samples showcased in the virtual part of the library ([Materials Library](materialslibrary/), [Product Library](productlibrary/)).
Each of them has been identified with a specific name to facilitate identification and comparison. The name is composed by three different codes `Gxx_Tyy`, i.e., G01_T03:
<br>`Gxx` Materials and Products main group.
<br>`Tyy` Products main spatial structure.

Do you want to know more about the organization and taxonomy of the physical and virtual parts of the library? Visit the section [How it works](howitworks/)!

<!-- pages/projects.md -->
<div class="projects">
{%- if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {%- for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {%- assign categorized_projects = site.projects | where: "category", category -%}
  {%- assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_projects -%}
      {% include projects_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_projects -%}
      {% include projects.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
  {% endfor %}

{%- else -%}
<!-- Display projects without categories -->
  {%- assign sorted_projects = site.projects | sort: "importance" -%}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_projects -%}
      {% include projects_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_projects -%}
      {% include projects.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
{%- endif -%}
</div>
