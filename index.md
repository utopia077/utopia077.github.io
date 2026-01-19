---
layout: default
title: 首页
description: "{{ site.description }}"
permalink: /
---

<!-- ==================== 样式部分 ==================== -->
<style>
/* 全局变量 */
:root {
  --primary-color: #3498db;
  --secondary-color: #2c3e50;
  --accent-color: #e74c3c;
  --text-color: #333;
  --light-bg: #f8f9fa;
  --card-shadow: 0 4px 12px rgba(0,0,0,0.08);
  --transition: all 0.3s ease;
}

/* 英雄区域 */
.hero {
  background: linear-gradient(135deg, var(--secondary-color) 0%, #1a1a2e 100%);
  color: white;
  padding: 5rem 1rem;
  text-align: center;
  border-radius: 0 0 20px 20px;
  margin-bottom: 3rem;
}

.hero h1 {
  font-size: 3rem;
  margin-bottom: 1rem;
  background: linear-gradient(45deg, #3498db, #9b59b6);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.hero p {
  font-size: 1.2rem;
  max-width: 600px;
  margin: 0 auto 2rem;
  opacity: 0.9;
}

.cta-buttons {
  display: flex;
  gap: 1rem;
  justify-content: center;
  flex-wrap: wrap;
}

.btn {
  padding: 0.8rem 2rem;
  border-radius: 50px;
  text-decoration: none;
  font-weight: 600;
  transition: var(--transition);
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
}

.btn-primary {
  background: var(--primary-color);
  color: white;
}

.btn-secondary {
  background: transparent;
  color: white;
  border: 2px solid white;
}

.btn:hover {
  transform: translateY(-2px);
  box-shadow: 0 8px 20px rgba(0,0,0,0.2);
}

/* 特色文章区域 */
.featured-posts {
  padding: 2rem 0;
}

.section-title {
  text-align: center;
  margin-bottom: 3rem;
  position: relative;
}

.section-title h2 {
  font-size: 2.2rem;
  color: var(--secondary-color);
  display: inline-block;
  padding-bottom: 0.5rem;
}

.section-title h2:after {
  content: '';
  position: absolute;
  width: 60px;
  height: 4px;
  background: var(--primary-color);
  bottom: 0;
  left: 50%;
  transform: translateX(-50%);
  border-radius: 2px;
}

/* 文章网格 */
.posts-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
  margin-bottom: 4rem;
}

.post-card {
  background: white;
  border-radius: 12px;
  overflow: hidden;
  box-shadow: var(--card-shadow);
  transition: var(--transition);
  height: 100%;
  display: flex;
  flex-direction: column;
}

.post-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 12px 24px rgba(0,0,0,0.15);
}

.post-image {
  height: 180px;
  background: linear-gradient(45deg, #3498db, #2c3e50);
  position: relative;
  overflow: hidden;
}

.post-category {
  position: absolute;
  top: 1rem;
  left: 1rem;
  background: var(--accent-color);
  color: white;
  padding: 0.3rem 1rem;
  border-radius: 20px;
  font-size: 0.8rem;
  font-weight: 600;
}

.post-content {
  padding: 1.5rem;
  flex-grow: 1;
  display: flex;
  flex-direction: column;
}

.post-content h3 {
  margin: 0 0 1rem 0;
  font-size: 1.3rem;
  line-height: 1.4;
}

.post-content h3 a {
  color: var(--secondary-color);
  text-decoration: none;
}

.post-content h3 a:hover {
  color: var(--primary-color);
}

.post-meta {
  display: flex;
  gap: 1rem;
  color: #666;
  font-size: 0.9rem;
  margin-bottom: 1rem;
  flex-wrap: wrap;
}

.post-meta span {
  display: flex;
  align-items: center;
  gap: 0.3rem;
}

.post-excerpt {
  color: #555;
  line-height: 1.6;
  margin-bottom: 1.5rem;
  flex-grow: 1;
}

/* 关于我区域 */
.about-section {
  background: var(--light-bg);
  padding: 4rem 1rem;
  border-radius: 20px;
  margin: 4rem 0;
}

.about-content {
  max-width: 800px;
  margin: 0 auto;
  display: flex;
  align-items: center;
  gap: 3rem;
  flex-wrap: wrap;
}

.about-avatar {
  flex: 0 0 150px;
}

.avatar {
  width: 150px;
  height: 150px;
  border-radius: 50%;
  background: linear-gradient(45deg, var(--primary-color), #9b59b6);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 3rem;
  color: white;
  font-weight: bold;
}

.about-text {
  flex: 1;
  min-width: 300px;
}

.about-text h3 {
  font-size: 1.8rem;
  margin-bottom: 1rem;
  color: var(--secondary-color);
}

.social-links {
  display: flex;
  gap: 1rem;
  margin-top: 1.5rem;
}

.social-links a {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 40px;
  height: 40px;
  background: var(--secondary-color);
  color: white;
  border-radius: 50%;
  text-decoration: none;
  transition: var(--transition);
}

.social-links a:hover {
  background: var(--primary-color);
  transform: scale(1.1);
}

/* 技能标签云 */
.skills-section {
  padding: 3rem 0;
}

.tags-cloud {
  display: flex;
  flex-wrap: wrap;
  gap: 0.8rem;
  justify-content: center;
  max-width: 800px;
  margin: 0 auto;
}

.tag {
  background: white;
  padding: 0.5rem 1.2rem;
  border-radius: 50px;
  box-shadow: 0 2px 8px rgba(0,0,0,0.1);
  transition: var(--transition);
  font-weight: 500;
}

.tag:hover {
  background: var(--primary-color);
  color: white;
  transform: scale(1.05);
}

/* 响应式调整 */
@media (max-width: 768px) {
  .hero h1 {
    font-size: 2.2rem;
  }
  
  .hero p {
    font-size: 1rem;
  }
  
  .posts-grid {
    grid-template-columns: 1fr;
  }
  
  .about-content {
    flex-direction: column;
    text-align: center;
  }
}
</style>

<!-- ==================== 内容部分 ==================== -->

<!-- 英雄区域 -->
<section class="hero">
  <h1>欢迎来到我的技术博客</h1>
  <p>{{ site.description }}</p>
  <div class="cta-buttons">
    <a href="#featured-posts" class="btn btn-primary">
      <span>📚 阅读文章</span>
    </a>
    <a href="/about" class="btn btn-secondary">
      <span>👤 关于作者</span>
    </a>
  </div>
</section>

<!-- 特色文章区域 -->
<section class="featured-posts" id="featured-posts">
  <div class="section-title">
    <h2>📝 最新文章</h2>
    <p>分享我的学习心得和技术实践</p>
  </div>
  
  <div class="posts-grid">
    {% assign latest_posts = site.posts | limit: 3 %}
    {% for post in latest_posts %}
    <article class="post-card">
      <div class="post-image">
        {% if post.categories.first %}
        <span class="post-category">{{ post.categories.first }}</span>
        {% endif %}
      </div>
      <div class="post-content">
        <h3>
          <a href="{{ post.url }}">{{ post.title }}</a>
        </h3>
        <div class="post-meta">
          <span title="发布日期">📅 {{ post.date | date: "%Y年%m月%d日" }}</span>
          {% if post.tags %}
          <span title="文章标签">🏷️ {{ post.tags | first }}</span>
          {% endif %}
          <span title="阅读时间">⏱️ {{ post.content | number_of_words | divided_by: 300 | plus: 1 }} 分钟</span>
        </div>
        <p class="post-excerpt">
          {{ post.excerpt | default: post.content | strip_html | truncate: 120 }}
        </p>
        <a href="{{ post.url }}" class="btn btn-primary" style="align-self: flex-start;">
          阅读全文 →
        </a>
      </div>
    </article>
    {% endfor %}
  </div>
  
  <div style="text-align: center; margin-top: 2rem;">
    <a href="/posts" class="btn btn-secondary" style="padding: 0.8rem 3rem;">
      查看所有文章 ({{ site.posts.size }}篇)
    </a>
  </div>
</section>

<!-- 关于我区域 -->
<section class="about-section">
  <div class="about-content">
    <div class="about-avatar">
      <div class="avatar">
        {{ site.author.name | slice: 0 }}
      </div>
    </div>
    <div class="about-text">
      <h3>👋 你好，我是 {{ site.author.name }}</h3>
      <p>一名热爱技术的开发者，在这里记录我的编程学习之路和技术实践心得。</p>
      <p>专注于 Web 开发、后端技术和系统架构，喜欢探索新技术并解决实际问题。</p>
      
      <div class="social-links">
        <a href="https://github.com/{{ site.author.github }}" title="GitHub" target="_blank">
          <span>GitHub</span>
        </a>
        <a href="mailto:{{ site.author.email }}" title="Email">
          <span>Email</span>
        </a>
        <!-- 添加更多社交链接 -->
      </div>
    </div>
  </div>
</section>

<!-- 技能标签云 -->
<section class="skills-section">
  <div class="section-title">
    <h2>🚀 技术栈 & 技能</h2>
  </div>
  <div class="tags-cloud">
    <!-- 修改这些标签为你实际的技术栈 -->
    <span class="tag">JavaScript</span>
    <span class="tag">Python</span>
    <span class="tag">Java</span>
    <span class="tag">HTML/CSS</span>
    <span class="tag">React</span>
    <span class="tag">Vue.js</span>
    <span class="tag">Node.js</span>
    <span class="tag">Git</span>
    <span class="tag">Docker</span>
    <span class="tag">Linux</span>
    <span class="tag">MySQL</span>
    <span class="tag">MongoDB</span>
  </div>
</section>

<!-- 统计信息 -->
<div style="text-align: center; padding: 2rem; color: #666; margin-top: 3rem;">
  <p>
    🎯 已分享 {{ site.posts.size }} 篇文章 • 
    📅 博客运行 {{ site.time | date: '%Y' | minus: 2024 | abs }} 年 •
    💖 持续更新中
  </p>
</div>
