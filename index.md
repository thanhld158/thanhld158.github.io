---
layout: page
title: Welcome to My Blog!
---
{% include JB/setup %}
<ul class="posts">
  {% for post in site.posts %}
  {% if (post.category != 'translation' && post.category != 'writing') %}
      <span><h5><b>{{ post.date | date_to_string }}</b></h5></span>
      <span><a href="{{ BASE_PATH }}{{ post.url }}"><h3> <b> {{ post.title }} </b></h3></a></span>
      <div class="post-content-truncate">
        {% if post.description != empty %}
          {{ post.description }}
        {% else %}
          {{ post.content | strip_html | truncatewords:100 }}
        {% endif %}
    </div>
    <br /> <br />
    {% endif %}
  {% endfor %}
</ul>