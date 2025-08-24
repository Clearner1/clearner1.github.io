---
title: 首页
layout: home
---

# 欢迎来到我的学习空间

 这里会放一些个人的学习内容

## 专辑

<div class="albums-grid">
  {% assign albums = site.pages | where: 'layout', 'album' %}
  {% for album in albums %}
    <div class="album-card">
      <h3><a href="{{ album.url }}">{{ album.title }}</a></h3>
      {% if album.description %}
        <p>{{ album.description }}</p>
      {% endif %}
      {% assign album_posts = site.posts | where: 'album', album.album_name %}
      <div class="album-meta">{{ album_posts.size }} 篇文章</div>
    </div>
  {% endfor %}
</div>

## 最新文章

<div class="posts-list">
  {% for post in site.posts limit:5 %}
    <div class="post-item">
      <h3><a href="{{ post.url }}">{{ post.title }}</a></h3>
      <div class="post-meta">
        <time>{{ post.date | date: "%Y年%m月%d日" }}</time>
        {% if post.album %}<span class="album-tag">{{ post.album }}</span>{% endif %}
      </div>
    </div>
  {% endfor %}
</div>

{% if site.posts.size > 5 %}
<div class="view-all">
  <a href="/albums/">查看所有文章 →</a>
</div>
{% endif %}

<style>
/* 苹果风格的简洁设计 */
.albums-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 1.5rem;
  margin: 2rem 0;
}

.album-card {
  background: #ffffff;
  border: 1px solid #e8e8e8;
  border-radius: 12px;
  padding: 1.5rem;
  transition: all 0.3s cubic-bezier(0.25, 0.46, 0.45, 0.94);
  box-shadow: 0 1px 3px rgba(0,0,0,0.05);
}

.album-card:hover {
  transform: translateY(-2px);
  box-shadow: 0 8px 25px rgba(0,0,0,0.15);
  border-color: #d1d1d1;
}

.album-card h3 {
  margin: 0 0 0.75rem 0;
  font-size: 1.1rem;
  font-weight: 600;
}

.album-card h3 a {
  text-decoration: none;
  color: #1d1d1f;
  transition: color 0.2s ease;
}

.album-card h3 a:hover {
  color: #007aff;
}

.album-card p {
  color: #6e6e73;
  font-size: 0.9rem;
  line-height: 1.5;
  margin: 0 0 1rem 0;
}

.album-meta {
  color: #8e8e93;
  font-size: 0.8rem;
  font-weight: 500;
}

.posts-list {
  margin: 1.5rem 0;
}

.post-item {
  padding: 1rem 0;
  border-bottom: 1px solid #f2f2f2;
  transition: background-color 0.2s ease;
}

.post-item:last-child {
  border-bottom: none;
}

.post-item:hover {
  background-color: #fafafa;
  border-radius: 8px;
  padding: 1rem;
  margin: 0 -1rem;
}

.post-item h3 {
  margin: 0 0 0.5rem 0;
  font-size: 1rem;
  font-weight: 600;
}

.post-item h3 a {
  text-decoration: none;
  color: #1d1d1f;
  transition: color 0.2s ease;
}

.post-item h3 a:hover {
  color: #007aff;
}

.post-meta {
  display: flex;
  align-items: center;
  gap: 0.75rem;
  font-size: 0.85rem;
  color: #8e8e93;
}

.album-tag {
  background: #f2f2f7;
  padding: 0.2rem 0.5rem;
  border-radius: 6px;
  font-size: 0.75rem;
  color: #007aff;
  font-weight: 500;
}

.view-all {
  text-align: center;
  margin: 2rem 0;
}

.view-all a {
  display: inline-block;
  padding: 0.75rem 1.5rem;
  background: #007aff;
  color: white;
  text-decoration: none;
  border-radius: 8px;
  font-weight: 500;
  transition: all 0.2s ease;
}

.view-all a:hover {
  background: #0051d5;
  transform: translateY(-1px);
}

/* 全局样式调整 */
h1 {
  font-size: 2rem;
  font-weight: 700;
  color: #1d1d1f;
  margin-bottom: 0.5rem;
}

h1 + p {
  font-size: 1.1rem;
  color: #6e6e73;
  margin-bottom: 2rem;
}

h2 {
  font-size: 1.3rem;
  font-weight: 600;
  color: #1d1d1f;
  margin: 2.5rem 0 1rem 0;
}
</style>
