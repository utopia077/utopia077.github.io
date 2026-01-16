---
layout: home
title: 首页
---

# 欢迎来到我的技术博客！

这里分享：
- 编程学习笔记
- 技术解决方案
- 项目开发经验

## 最新文章

{% for post in site.posts limit:3 %}
### [{{ post.title }}]({{ post.url }})
{{ post.date | date: "%Y年%m月%d日" }}  
{{ post.excerpt | strip_html | truncate: 100 }}
{% endfor %}

[查看所有文章](/posts)
