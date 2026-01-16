---
layout: page
title: 所有文章
permalink: /posts/
---

# 所有文章

{% for post in site.posts %}
<div class="post-item">
  <h2>
    <a href="{{ post.url | relative_url }}">
      {{ post.title }}
    </a>
  </h2>
  
  <p class="post-meta">
    <time datetime="{{ post.date | date_to_xmlschema }}">
      {{ post.date | date: "%Y年%m月%d日" }}
    </time>
    {% if post.categories %}
      • 分类: {{ post.categories | join: ", " }}
    {% endif %}
    {% if post.tags %}
      • 标签: {{ post.tags | join: ", " }}
    {% endif %}
  </p>
  
  <div class="post-excerpt">
    {{ post.excerpt | strip_html | truncate: 200 }}
  </div>
  
  <a href="{{ post.url | relative_url }}" class="read-more">
    阅读全文 →
  </a>
  
  <hr>
</div>
{% else %}
<p>暂无文章。</p>
{% endfor %}
