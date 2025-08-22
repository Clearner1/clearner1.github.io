---
title: Anki学习技术文档
layout: home
---

# 欢迎来到Anki学习技术文档

这里收集了关于Anki学习方法和技巧的系列文档，内容涵盖从基础理论到实践应用的各个方面。

## 文档概览

本站包含以下主要内容：

### 基础理论
- 学习的最小闭环理论
- 记忆原理与认知科学
- 学习策略与方法论

### 实践技巧
- Anki使用技巧与优化
- 标签系统与分类方法
- 复习策略与难点处理

### 进阶应用
- 碎片化输入与结构化输出
- 学以致用的方法
- 减负与效率优化

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
