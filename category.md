---
layout: default
title: Categories
---
<h1>Categories</h1>
Below is a list of all the categories on the site as well as a few posts from each category
<hr>
{% for category in site.categories %}
  <div class="blogList">
    {% capture categoryName %}{{ category | first }}{% endcapture %}
    <div id="#{{ categoryName | slugize }}"></div>
    <h2 class="categoryHead">{{ categoryName }}</h2>
    <a name="{{ categoryName | slugize }}"></a>
    {% for post in site.categories[categoryName] %}
        <ul>
            <h3><a href="{{ post.url }}">{{ post.title }}</a></h3>
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
{% endif %} | categoryged with:
{% assign categoryCount = post.categorys | size %}
    {% if categoryCount == 0 %}
        No categorys
    {% elsif categoryCount == 1 %}
    <a href="/category/#{{ post.categorys | first }}">{{ post.categorys | first }}</a>
        {% else %}
            {% for category in post.categorys %}
                {% if forloop.first %}
                    <a href="/category/#{{ category }}">{{ category }}</a>
                {% elsif forloop.last %}
                    and <a href="/category/#{{ category  }}">{{ category }}</a>
                {% else %}
                    , <a href="/category/#{{ category  }}">{{ category }}</a>
        {% endif %}
    {% endfor %}
{% endif %}
                {{ post.excerpt }}
      <hr>
      </ul>
    {% endfor %}
  </div>
{% endfor %}