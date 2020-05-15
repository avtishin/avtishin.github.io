---
layout: page
title: Thoughts
---

<ul>
  {% for post in site.posts %}
  <div class="post">
    <h3 class="post-title">
      <a href="{{ post.url }}">
        {{ post.title }}
      </a>
    </h3>

     <span class="post-date"> <h6>  <em>{{ post.date | date_to_string }} </em>  </h6></span> 
    
     {% if post.content contains "<!-- more -->" %}
      {{ post.content | split:"<!-- more -->" | first % }}
      <div style="text-align:right;">
        <a href="{{ post.url }}" style="color:#000;"> <h5 class="related-posts li small"> Read More </h5> </a>
      </div>
    {% else %}
      {{ post.content }}
    {% endif %}
  </div>
  {% endfor %}
</ul>

