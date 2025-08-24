---
layout: default
title: 专辑导航
permalink: /albums/
---

# 专辑导航

这里是所有专辑的汇总页面，每个专辑包含相关主题的文章系列。

<div class="albums-grid">
  {% assign albums = site.pages | where: 'layout', 'album' %}
  {% for album in albums %}
    <div class="album-card">
      <h2><a href="{{ album.url }}">{{ album.title }}</a></h2>
      {% if album.description %}
        <p class="album-description">{{ album.description }}</p>
      {% endif %}
      {% assign album_posts = site.posts | where: 'album', album.album_name %}
      <div class="album-meta">
        <span class="post-count">{{ album_posts.size }} 篇文章</span>
        {% if album_posts.size > 0 %}
          <span class="last-updated">最后更新: {{ album_posts.first.date | date: "%Y年%m月%d日" }}</span>
        {% endif %}
      </div>
    </div>
  {% endfor %}
</div>

## 按专辑浏览文章

{% assign albums = site.pages | where: 'layout', 'album' %}
{% for album in albums %}
  {% assign album_posts = site.posts | where: 'album', album.album_name %}
  {% if album_posts.size > 0 %}
    <div class="album-section">
      <h3><a href="{{ album.url }}">{{ album.title }}</a></h3>
      <ul class="album-posts-list">
        {% for post in album_posts limit: 5 %}
          <li><a href="{{ post.url }}">{{ post.title }}</a> <small>({{ post.date | date: "%Y-%m-%d" }})</small></li>
        {% endfor %}
        {% if album_posts.size > 5 %}
          <li><a href="{{ album.url }}">查看全部 {{ album_posts.size }} 篇文章 →</a></li>
        {% endif %}
      </ul>
    </div>
  {% endif %}
{% endfor %}

<style>
.albums-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
  margin: 2rem 0;
}

.album-card {
  border: 1px solid #e1e1e1;
  border-radius: 8px;
  padding: 1.5rem;
  background: #fafafa;
  transition: box-shadow 0.3s ease;
}

.album-card:hover {
  box-shadow: 0 4px 12px rgba(0,0,0,0.1);
}

.album-card h2 {
  margin-top: 0;
  margin-bottom: 1rem;
}

.album-card h2 a {
  text-decoration: none;
  color: #333;
}

.album-card h2 a:hover {
  color: #007acc;
}

.album-description {
  color: #666;
  line-height: 1.5;
  margin-bottom: 1rem;
}

.album-meta {
  font-size: 0.9em;
  color: #888;
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 0.5rem;
}

.album-section {
  margin: 2rem 0;
  padding: 1.5rem;
  border-left: 4px solid #007acc;
  background: #f9f9f9;
}

.album-section h3 {
  margin-top: 0;
  margin-bottom: 1rem;
}

.album-section h3 a {
  text-decoration: none;
  color: #333;
}

.album-section h3 a:hover {
  color: #007acc;
}

.album-posts-list {
  list-style: none;
  padding: 0;
}

.album-posts-list li {
  margin-bottom: 0.5rem;
  padding-left: 1rem;
  position: relative;
}

.album-posts-list li:before {
  content: "•";
  color: #007acc;
  position: absolute;
  left: 0;
}

.album-posts-list a {
  text-decoration: none;
  color: #333;
}

.album-posts-list a:hover {
  color: #007acc;
  text-decoration: underline;
}

.album-posts-list small {
  color: #888;
  margin-left: 0.5rem;
}
</style>
