---
layout: blog
title: Blog
description: Read about what Scarlet Data Studio has been up to.
---

<div class="articles">
  {% assign date_format = "%B %e, %Y" %}
  {% assign articles = site.blog | where: 'display', true | sort: "published" | reverse %}
  {% for page in articles %}
    <div class="article">
      <a href="../blog/{{ page.slug }}" class="no-decorate">
        <h2>{{ page.title }}</h2>
      </a>
      <p>
        {% if page.author and page.published %}
          <span>By {{ page.author }} on {{ page.published | date: date_format }}</span>
        {% elsif page.author %}
          <span>By {{ page.author }}</span>
        {% elsif page.published %}
          <span>By {{ page.published | date: date_format }}</span>
        {% endif %}
      </p>
      {% if page.description %}
        <p>{{ page.description }}</p>
      {% endif %}
    </div>
  {% endfor %}
</div>
