---
layout: default
title: 首页
---
<div class="home">
  <section class="hero">
    <h1>{{ site.title }}</h1>
    <p class="tagline">{{ site.description }}</p>
  </section>

  <section class="post-list">
    <h2>文章</h2>
    {% if site.posts.size > 0 %}
      <ul>
        {% for post in site.posts %}
          <li class="post-item">
            <a class="post-link" href="{{ post.url | relative_url }}">{{ post.title }}</a>
            <span class="post-meta">{{ post.date | date: "%Y-%m-%d" }}</span>
            {% if post.excerpt %}
              <p class="post-excerpt">{{ post.excerpt | strip_html | truncate: 120 }}</p>
            {% endif %}
          </li>
        {% endfor %}
      </ul>
    {% else %}
      <p>还没有文章，马上就来。</p>
    {% endif %}
  </section>
</div>
