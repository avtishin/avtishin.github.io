---
layout: page
title: Thoughts
---

<ul>
  {% for post in site.posts %}
  <div class="post">
    <h4 class="post-title">
      <a href="{{ post.url }}">
        {{ post.title }}
      </a>
    </h4>

     <h6>  <em> <span class="post-date">{{ post.date | date_to_string }}</span> </em>  </h6>
    
     {% if post.content contains "<!-- more -->" %}
      {{ post.content | split:"<!-- more -->" | first % }}
      <div style="text-align:right;">
        <a href="{{ post.url }}" style="color:#000;"> Read More </a>
      </div>
    {% else %}
      {{ post.content }}
    {% endif %}
  </div>
  {% endfor %}
</ul>

