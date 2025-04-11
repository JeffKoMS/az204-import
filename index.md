---
title: Microsoft Azure developer exercises
permalink: index.html
layout: home
---

# Develop solutions for Microsoft Azure

The following exercises are designed to provide you with a hands-on learning experience in which you’ll explore common tasks that developers do when developing and deploying solutions to Microsoft Azure.

## Table of Contents
{% assign exercises = site.pages | where_exp:"page", "page.url contains '/Instructions/Exercises'" %}
{% assign grouped_exercises = exercises | group_by: "lab.topic" %}

<ul>
{% for group in grouped_exercises %}
<li><a href="#{{ group.name | slugify }}">{{ group.name }}</a></li>
{% endfor %}
</ul>

{% for group in grouped_exercises %}

## <a id="{{ group.name | slugify }}"></a>{{ group.name }} 
{% for activity in group.items %}
| [{{ activity.lab.title }}]({{ site.github.url }}{{ activity.url }}) <br/> {{ activity.lab.description }} |

{% endfor %}
| <span style="font-size: smaller;"><a href="#table-of-contents">Table of contents</a></span> |
{% endfor %}

