---
title: Zane, who are you?
layout: home
---

# 欢迎来到Zane的 Blog

 这里会放一些个人的学习内容

## 专辑导航

<div class="albums-preview">
  {% assign albums = site.pages | where: 'layout', 'album' %}
  {% for album in albums %}
    <div class="album-preview">
      <h3><a href="{{ album.url }}">{{ album.title }}</a></h3>
      {% if album.description %}
        <p>{{ album.description }}</p>
      {% endif %}
      {% assign album_posts = site.posts | where: 'album', album.album_name %}
      <small>{{ album_posts.size }} 篇文章</small>
    </div>
  {% endfor %}
</div>

<p><a href="/albums/">查看所有专辑 →</a></p>

## 最新文章

{% for post in site.posts limit:5 %}
- [{{ post.title }}]({{ post.url }}) - {{ post.date | date: "%Y年%m月%d日" }}
  {% if post.album %}<small>专辑: {{ post.album }}</small>{% endif %}
{% endfor %}

## 所有文章

{% for post in site.posts %}
- [{{ post.title }}]({{ post.url }}) - {{ post.date | date: "%Y年%m月%d日" }}
  {% if post.album %}<small>专辑: {{ post.album }}</small>{% endif %}
{% endfor %}

---

*本文档持续更新中，欢迎收藏关注。*

## 关于本站

本站基于Jekyll构建，所有文档均为Markdown格式，方便阅读和维护。如果您对内容有任何建议或发现错误，欢迎反馈。

<style>
.albums-preview {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 1.5rem;
  margin: 1.5rem 0;
}

.album-preview {
  border: 1px solid #e1e1e1;
  border-radius: 6px;
  padding: 1.25rem;
  background: #f8f9fa;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.album-preview:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 12px rgba(0,0,0,0.1);
}

.album-preview h3 {
  margin-top: 0;
  margin-bottom: 0.75rem;
}

.album-preview h3 a {
  text-decoration: none;
  color: #333;
}

.album-preview h3 a:hover {
  color: #007acc;
}

.album-preview p {
  color: #666;
  font-size: 0.9em;
  line-height: 1.4;
  margin-bottom: 0.75rem;
}

.album-preview small {
  color: #888;
  font-style: italic;
}
</style>
