---
title: Zane, who are you?
layout: home
---

# 欢迎来到Zane的 Blog

 这里会放一些个人的学习内容


## 最新文章

{% for post in site.posts limit:5 %}
- [{{ post.title }}]({{ post.url }}) - {{ post.date | date: "%Y年%m月%d日" }}
{% endfor %}

## 所有文章

{% for post in site.posts %}
- [{{ post.title }}]({{ post.url }}) - {{ post.date | date: "%Y年%m月%d日" }}
{% endfor %}

---

*本文档持续更新中，欢迎收藏关注。*

## 关于本站

本站基于Jekyll构建，所有文档均为Markdown格式，方便阅读和维护。如果您对内容有任何建议或发现错误，欢迎反馈。
