---
layout: archive
title: "CV"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% comment %} The CV content lives in _data/cv.yml. {% endcomment %}
<div class="cv">
{% for block in site.data.cv %}
  <section class="cv-section">
    <h2 class="cv-section__title">{{ block.section }}</h2>
    {% for e in block.entries %}
    <div class="cv-entry">
      <div class="cv-entry__head">
        <span class="cv-entry__title">{{ e.title | markdownify | remove: '<p>' | remove: '</p>' | strip }}</span>
        {% if e.dates %}<span class="cv-entry__dates">{{ e.dates }}</span>{% endif %}
      </div>
      {% if e.org %}<div class="cv-entry__org">{{ e.org | markdownify | remove: '<p>' | remove: '</p>' | strip }}</div>{% endif %}
      {% if e.bullets %}
      <ul class="cv-entry__bullets">
        {% for b in e.bullets %}<li>{{ b | markdownify | remove: '<p>' | remove: '</p>' | strip }}</li>{% endfor %}
      </ul>
      {% endif %}
    </div>
    {% endfor %}
  </section>
{% endfor %}
</div>
