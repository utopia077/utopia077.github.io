---
layout: default
title: 首页
permalink: /
---

<style>
/* 简洁美观的基础样式 */
:root {
  --main-color: #2c3e50;
  --accent-color: #3498db;
  --light-color: #f8f9fa;
  --text-color: #333;
}

/* 简约标题区 */
.header {
  text-align: center;
  padding: 3rem 1rem 2rem;
  border-bottom: 2px solid #eee;
  margin-bottom: 2rem;
}

.site-title {
  font-size: 2rem;
  color: var(--main-color);
  margin-bottom: 0.5rem;
  position: relative;
}

.site-title:after {
  content: '';
  position: absolute;
  width: 60px;
  height: 3px;
  background: var(--accent-color);
  bottom: -10px;
  left: 50%;
  transform: translateX(-50%);
}

.site-description {
  color: #666;
  font-size: 1.1rem;
  margin-top: 1.5rem;
}

/* 简洁导航 */
.main-nav {
  text-align: center;
  margin: 2rem 0 3rem;
}

.nav-link {
  display: inline-block;
  margin: 0 1rem;
  padding: 0.5rem 1.5rem;
  color: var(--main-color);
  text-decoration: none;
  border: 2px solid var(--main-color);
  border-radius: 4px;
  transition: all 0.3s ease;
}

.nav-link:hover {
  background: var(--main-color);
  color: white;
}

/* 文章列表 */
.articles-container {
  max-width: 800px;
  margin: 0 auto;
  padding: 0 1rem;
}

.section-title {
  font-size: 1.3rem;
  color: var(--main-color);
  margin-bottom: 1.5rem;
  padding-bottom: 0.5rem;
  border-bottom: 1px solid #eee;
}

.article-list {
  list-style: none;
  padding: 0;
}

.article-item {
  margin-bottom: 1.5rem;
  padding-bottom: 1.5rem;
  border-bottom: 1px dashed #eee;
}

.article-item:last-child {
  border-bottom: none;
}

.article-title {
  font-size: 1.1rem;
  margin-bottom: 0.5rem;
}

.article-title a {
  color: var(--main-color);
  text-decoration: none;
}

.article-title a:hover {
  color: var(--accent-color);
  text-decoration: underline;
}

.article-meta {
  color: #666;
  font-size: 0.9rem;
  margin-bottom: 0.5rem;
}

.article-excerpt {
  color: #555;
  line-height: 1.5;
  font-size: 0.95rem;
}

.view-all {
  text-align: center;
  margin-top: 2rem;
}

.view-all a {
  color: var(--accent-color);
  text-decoration: none;
  font-weight: 500;
}

.view-all a:hover {
  text-decoration: underline;
}

/* 底部简洁 */
.footer {
  text-align: center;
  margin-top: 3rem;
  padding-top: 2rem;
  border-top: 1px solid #eee;
  color: #666;
  font-size: 0.9rem;
}

/* 响应式 */
@media (max-width: 768px) {
  .header {
    padding: 2rem 1rem;
  }
  
  .site-title {
    font-size: 1.6rem;
  }
  
  .nav-link {
    display: block;
    margin: 0.5rem auto;
    width: 200px;
  }
}
</style>

<!-- 简洁标题区 -->
<div class="header">
  <h1 class="site-title">{{ site.title }}</h1>
  <p class="site-description">{{ site.description }}</p>
</div>

<!-- 简约导航 -->
<div class="main-nav">
  <a href="/posts" class="nav-link">📚 所有文章</a>
  <a href="/about" class="nav-link">👤 关于作者</a>
</div>

<!-- 文章列表 -->
<div class="articles-container">
  <h2 class="section-title">📝 最新文章</h2>
  
  <ul class="article-list">
    {% for post in site.posts limit: 5 %}
    <li class="article-item">
      <h3 class="article-title">
        <a href="{{ post.url }}">{{ post.title }}</a>
      </h3>
      
      <div class="article-meta">
        <span>{{ post.date | date: "%Y年%m月%d日" }}</span>
        {% if post.categories %}
        <span style="margin-left: 1rem;">📂 {{ post.categories | first }}</span>
        {% endif %}
      </div>
      
      <p class="article-excerpt">
        {{ post.excerpt | default: post.content | strip_html | truncate: 80 }}
      </p>
    </li>
    {% endfor %}
  </ul>
  
  {% if site.posts.size > 5 %}
  <div class="view-all">
    <a href="/posts">查看更多文章 ({{ site.posts.size }}篇) →</a>
  </div>
  {% endif %}
</div>

<!-- 简洁底部 -->
<div class="footer">
  <p>© {{ site.time | date: "%Y" }} {{ site.title }}</p>
</div>
