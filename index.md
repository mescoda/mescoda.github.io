---
layout: default
---

<div class="article-wrap">
{% for post in site.posts limit: 1 %}
    <div class="article">
        <div class="article-hd">
            <h2 class="article-hd-title">
                <a href="{{ post.url }}" class="article-hd-title-link">{{ post.title }}</a>
            </h2>
            <div class="artitle-hd-meta">
                <span class="article-hd-meta-time">{{ post.date | date:"%Y-%m-%d" }}</span>
            </div>
        </div>
        <div class="article-bd">
            {{ post.content }}
        </div>
    </div>
{% endfor %}
</div>

<div class="archive">
    <h3 class="archive-title">Happend earlier this year</h3>
    <ul class="archive-list">
        {% capture year %}{{ site.time | date:"%Y"}}{% endcapture %}
        {% for post in site.posts offset:1 %}
            {% capture y %}{{ post.date | date:"%Y"}}{% endcapture %}
            {% if y == year %}
                <li class="archive-list-item">
                    <span class="archive-list-item-time">{{ post.date | date:"%Y-%m-%d" }}</span>
                    <a href="{{ post.url }}" class="archive-list-item-title">{{ post.title }}</a>
                </li>
            {% endif %}
        {% endfor %}
    </ul>
</div>
<div class="more">
    <a href="{{ site.navs[0].url }}" class="more-link">Long long ago</a>
</div>
