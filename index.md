---
layout: page
title: Welcome!
tagline: ようこそ
---
{% include JB/setup %}

<div class="panel panel-default">
  <div class="panel-heading">
    List Posts
  </div>
    <div class="list-group">
      {% for post in site.posts %}
        <a class="list-group-item" href="{{ BASE_PATH }}{{ post.url }}">
          <span class="badge">{{ post.date | date_to_string }}</span>
          {{ post.title }}
        </a>
      {% endfor %}
    </div>
</div>