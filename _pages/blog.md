---
layout: page
title: blog
permalink: blog
description: 
nav: true
nav_order: 4
---
<div class="news">

  <!--
  <header class="post-header">
    <h1 class="post-title"> <i class="fas fa-calendar fa-sm"></i> {{ page.date | date: "%Y" }} </h1>
    <p class="post-description"> an archive of posts from this year </p>
  </header>
  -->

<div class="table-responsive">
  <table class="table table-sm table-borderless">
    {% if page.pagination.enabled %}
      {% assign postlist = paginator.posts %}
    {% else %}
      {% assign postlist = site.posts %}
    {% endif %}

    {% for post in postlist %}
    <tr>
      <th scope="row">{{ post.date | date: "%b %-d, %Y" }}</th>
      <td>
          {% if post.external_link %}
            <a href="{{ post.external_link }}" target="_blank">{{ post.title }}</a>
          {% else %}
            <a class="post-link" href="{{ post.url | relative_url }}">{{ post.title }}</a>
          {% endif %}
      </td>
    </tr>
  {% endfor %}
  </table>
</div>

</div>

