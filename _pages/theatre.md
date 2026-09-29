---
layout: archive
title: "Theatre"
permalink: /theatre/
author_profile: true
---

{% include base_path %}
{% comment %} Credits and photos come from the Theatre section of _data/cv.yml. {% endcomment %}
{% assign theatre = site.data.cv | where: "section", "Theatre" | first %}

<div class="theatre-gallery">
{% for e in theatre.entries %}{% if e.photo %}
  <figure class="theatre-photo">
    <img src="{{ base_path }}/images/theatre/{{ e.photo }}" alt="{{ e.caption | strip_html | remove: '*' }}" loading="lazy">
    <figcaption>{{ e.caption | markdownify | remove: '<p>' | remove: '</p>' | strip }}</figcaption>
  </figure>
{% endif %}{% endfor %}
</div>

<section class="cv-section">
  <h2 class="cv-section__title">Credits</h2>
  {% for e in theatre.entries %}
  <div class="cv-entry">
    <div class="cv-entry__head">
      <span class="cv-entry__title">{{ e.title }}</span>
      {% if e.dates %}<span class="cv-entry__dates">{{ e.dates }}</span>{% endif %}
    </div>
    {% if e.org %}<div class="cv-entry__org">{{ e.org | markdownify | remove: '<p>' | remove: '</p>' | strip }}</div>{% endif %}
  </div>
  {% endfor %}
</section>
