---
layout: default
title: Blog
permalink: /Blog/
---

To be made :D

<div class="Blog">
    <ul>
        {% for post in site.posts %}
            {% if drafts.categories contains "blog" %}
                <li>
                    <a href="{{ drafts.url }}">{{ drafts.title }}</a>
                    <em><small>{{ drafts.date | date: "%B %d, %Y" }}</small></em>
                </li>
            {% endif %}
        {% endfor %}
    </ul>
</div>