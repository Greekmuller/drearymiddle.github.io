---
layout: default
title: Blog
---
<h1>Latest Posts</h1>

<ul>
  {% for post in site.posts %}
    
      <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
      {{ post.date | date_to_string }} | Written by: 
  {% assign authorCount = post.authors | size %}
    {% if authorCount == 0 %}
        No author
    {% elsif authorCount == 1 %}
    <a href="/authors/{{ post.authors | first }}">{{ post.authors | first }}</a>
        {% else %}
            {% for author in post.authors %}
                {% if forloop.first %}
                    <a href="/authors/{{ author }}">{{ author }}</a>
                {% elsif forloop.last %}
                    and <a href="/authors/{{ author }}">{{ author }}</a>
                {% else %}
                    , <a href="/authors/{{ author }}">{{ author }}</a>
        {% endif %}
    {% endfor %}
{% endif %} | Categorised as: 
{% assign categoryCount = post.categories | size %}
    {% if categoryCount == 0 %}
        Nothing
    {% elsif categoryCount == 1 %}
    <a href="/category/{{ post.categories | first  | downcase }}">{{ post.categories | first }}</a>
        {% else %}
            {% for category in post.categories %}
                {% if forloop.first %}
                    <a href="/category/{{ category | downcase }}">{{ category }}</a>
                {% elsif forloop.last %}
                    and <a href="/category/{{ category | downcase }}">{{ category }}</a>
                {% else %}
                    , <a href="/category/{{ category | downcase }}">{{ category }}</a>
        {% endif %}
    {% endfor %}
{% endif %} | Tagged with:
{% assign tagCount = post.tags | size %}
    {% if tagCount == 0 %}
        No tags
    {% elsif tagCount == 1 %}
    <a href="/tag/#{{ post.tags | first }}">{{ post.tags | first }}</a>
        {% else %}
            {% for tag in post.tags %}
                {% if forloop.first %}
                    <a href="/tag/#{{ tag }}">{{ tag }}</a>
                {% elsif forloop.last %}
                    and <a href="/tag/#{{ tag  }}">{{ tag }}</a>
                {% else %}
                    , <a href="/tag/#{{ tag  }}">{{ tag }}</a>
        {% endif %}
    {% endfor %}
{% endif %}
      {{ post.excerpt }}
    <hr>
  {% endfor %}
</ul>