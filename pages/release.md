---
title: Release Archive
permalink: /release/
redirect_from: 
  - /release_notes/
  - /release_notes.html
---

<div>
<hr>
{% assign header_year = site.categories.release[0].date | date: "%Y" %}
<h3>{{header_year}}</h3>
{% for release in site.categories.release %}
  {% assign current_release_year = release.date | date: "%Y" %}
  {% if current_release_year != header_year %}
    {% assign header_year = current_release_year %}
    <hr>
    <h3>{{ header_year }}</h3>
  {% endif %}
  <div class="row" style="margin-top: 15px">
    <div class="col-md-1">{{ release.date | date: "%b %d" }}</div>
    <div class="col-md-10"><a href="{{ site.baseurl }}{{ release.url }}">{{ release.title }}</a></div>
  </div>
{% endfor %}
</div>
