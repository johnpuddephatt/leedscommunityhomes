---
# You don't need to edit this file, it's empty on purpose.
# Edit theme's home layout instead if you wanna make some changes
# See: https://jekyllrb.com/docs/themes/#overriding-theme-defaults
layout: page
title: News and updates
description: We’re building 16 permanently affordable homes in Leeds’ Climate Innovation District
---
{% for post in site.posts %}

  <div class="card post--card" href="#" data-tags="{{ post.tags | join: ','}}">
    <h2 class="post-title"><a href="{{ post.url }}">{{ post.title }}</a></h2>
    <div class="post-excerpt">
      {{ post.excerpt }}
    </div>
    <ul class="post-tags">
      {% for tag in post.tags %}
        <li class="tag"><a href="/blog?tag={{ tag }}">{{ tag }}</a></li>
      {% endfor %}
    </ul>
  </div>

{% endfor %}

<script>
  var search = location.search.split('tag=').splice(1).join('').split('&')[0];
  if(search) {
    console.log(search);
    var all = document.querySelectorAll('.post--card');
    var shown = document.querySelectorAll('div[data-tags*=' + search + ']');
    for (var i = 0; i < all.length; i++) {
      all[i].style.display = 'none';
    }
    for (var i = 0; i < shown.length; i++) {
      shown[i].style.display = 'block';
    }

  }

</script>