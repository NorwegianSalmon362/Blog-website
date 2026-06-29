---
layout: page
title: Tags
description: Topics will appear here once you publish tagged notes.
permalink: /tags/
---
{% assign sorted_tags = site.tags | sort %}

{% if sorted_tags.size > 0 %}
  <div class="tag-index">
    <ul class="tag-list tag-list--index">
      {% for tag in sorted_tags %}
        <li>
          <a href="#{{ tag[0] | slugify }}">{{ tag[0] }}</a>
          <span>{{ tag[1].size }}</span>
        </li>
      {% endfor %}
    </ul>
  </div>

  <div class="tag-groups">
    {% for tag in sorted_tags %}
      <section class="tag-group" id="{{ tag[0] | slugify }}">
        <h2>{{ tag[0] }}</h2>
        <div class="post-list">
          {% assign posts = tag[1] | sort: "date" | reverse %}
          {% for post in posts %}
            {% include post-list-item.html post=post %}
          {% endfor %}
        </div>
      </section>
    {% endfor %}
  </div>
{% else %}
  <p>No tags yet.</p>
{% endif %}
