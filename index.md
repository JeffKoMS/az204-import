---
title: Online Hosted Instructions
permalink: index.html
layout: home
---

## Content Directory

Hyperlinks to each of the labs are listed below.

## Labs

{% assign labs = site.pages | where_exp: "page", "page.url contains '/Instructions/Labs'" %}
| Module | Lab |
| --- | --- |
{% for activity in labs  %}{% if activity.lab.az204Module %}| {{ activity.lab.az204Module }} | [{{ activity.lab.az204Title }}]({{ site.github.url }}{{ activity.url }}) |
{% endif %}{% endfor %}

## Exercises

The following exercises are designed to provide you with a hands-on learning experience in which you’ll explore common tasks that developers do when building AI agents on Microsoft Azure.

{% assign exercises = site.pages | where_exp:"page", "page.url contains '/Instructions/Exercises'" %}
{% assign grouped_exercises = exercises | group_by: "lab.topic" %}

{% for group in grouped_exercises %}

## {{ group.name }}

<hr/>

{% for activity in group.items %}

### [{{ activity.lab.title }}]({{ site.github.url }}{{ activity.url }})

{{ activity.lab.description }}

{% endfor %}
{% endfor %}

