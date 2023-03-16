---
layout: page
title: Materials Library
permalink: /materialslibrary/
description: Materials library section of RepMat Library
nav: false
nav_order: 2
display_categories: [Material samples]
horizontal: false
---
The Material Library section aims to show variations in the expressive-sensorial qualities of materials, linking them to quantitative aspects such as waste percentage.

Each sample has been identified with a specific name to facilitate identification and comparison. The name is composed by three different codes `Gxxx_Myy_Szz`, i.e., G002_M03_S11:
<br>`Gxxx` Materials and Products main group.
<br>`Myy` Specific material of the main group.
<br>`Szz` Specific material sample

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
