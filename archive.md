---
layout: page
title: Archive
description: Every post, grouped by year.
permalink: /archive/
---
{% assign current_year = "" %}

<div class="archive-list">
  {% for post in site.posts %}
    {% assign post_year = post.date | date: "%Y" %}
    {% if post_year != current_year %}
      {% assign current_year = post_year %}
      <h2 class="archive-year">{{ current_year }}</h2>
    {% endif %}

    <article class="archive-entry">
      <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%-d %b" }}</time>
      <div>
        <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
        <p>
          {% if post.description %}
            {{ post.description }}
          {% else %}
            {{ post.excerpt | strip_html | strip_newlines | truncate: 180 }}
          {% endif %}
        </p>
      </div>
    </article>
  {% endfor %}
</div>
