---
layout: page
title: Publication
permalink: /publication/
---

## Journal Articles

{% assign journal_posts = site.categories.Journal %}
{% assign journal_years = journal_posts | map: 'date' | date: '%Y' | uniq %}

{% for year in journal_years %}
### {{ year }}
  {% for post in journal_posts %}
    {% assign post_year = post.date | date: '%Y' %}
    {% if post_year == year %}
* **[{{ post.title }}]({{ post.url | relative_url }})**<br>
  {{ post.authors }}<br>
  *{{ post.venue }}*{% if post.status %}, {{ post.status }}{% endif %} ({{ post.date | date: "%Y.%m" }}){% if post.doi %} · [[DOI]]({{ post.doi }}){% endif %}
    {% endif %}
  {% endfor %}
{% endfor %}

---

## Conference Papers

{% assign conf_posts = site.categories.Conference %}
{% assign conf_years = conf_posts | map: 'date' | date: '%Y' | uniq %}

{% for year in conf_years %}
### {{ year }}
  {% for post in conf_posts %}
    {% assign post_year = post.date | date: '%Y' %}
    {% if post_year == year %}
* **[{{ post.title }}]({{ post.url | relative_url }})**<br>
  {{ post.authors }}<br>
  *{{ post.venue }}* ({{ post.date | date: "%Y.%m" }}){% if post.doi %} · [[Link]]({{ post.doi }}){% endif %}
    {% endif %}
  {% endfor %}
{% endfor %}
