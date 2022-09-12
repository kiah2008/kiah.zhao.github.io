---
layout: tags
title: tags
description: 文章标签分类
keywords: 分类
comments: false
menu: 标签
permalink: /tags/
---

<section class="container posts-content">
{% if site.tags %}
    {% assign sorted_tags = site.tags | sort %}
    {% for tag in sorted_tags %}
        <h3 id="{{ tag[0] }}">{{ tag | first }}</h3>
        <ol class="posts-list">
            {% for post in tag.last %}
                <li class="posts-list-item">
                <span class="posts-list-meta">{{ post.date | date:"%Y-%m-%d" }}</span>
                <a class="posts-list-name" href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a>
                </li>
            {% endfor %}
        </ol>
    {% endfor %}
{% endif %}
</section>
<!-- /section.content -->
