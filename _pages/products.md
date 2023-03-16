---
layout: page
title: Product Library
permalink: /productlibrary/
description: Product library section of RepMat Library
nav: false
nav_order: 2
display_categories: [Group 01, Group 02, Group 03, Group 04]
horizontal: false
---

The Product Library section aims to show variations in the expressive-sensorial qualities of materials influenced by manufacturing processes, linking them to quantitative aspects, technical data, achievable geometries and shapes, and possible applications and exploitations.

Each sample has been identified with a specific name to facilitate identification and comparison. The name is composed by three different codes `Txx_Lyy_Szz`, i.e., T02_L02_S05:
<br>`Txx` Products main spatial structure.
<br>`Lyy` Specific layer of the spatial.
<br>`Szz` Specific material sample in the layer.

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
