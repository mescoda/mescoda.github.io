---
layout: page
title: Archive
---

<div class="archive">
    <ul class="archive-list">
    {% for post in site.posts %}
        {% capture y %}{{post.date | date:"%Y"}}{% endcapture %}
        {% if year != y %}
            {% assign year = y %}
            <li class="archive-list-item">{{ year }}</li>
        {% endif %}
        <li class="archive-list-item">
            <span class="archive-list-item-time">{{ post.date | date:"%Y-%m-%d" }}</span>
            <a href="{{ post.url }}" class="archive-list-item-title">{{ post.title }}</a>
        </li>
    {% endfor %}
    </ul>
</div>
