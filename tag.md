---
layout: default
title: Tags
---
# List of tags
The world's biggest list of tags, be in awe of the sheer size of this list... beginning now!
<hr>
{% for tag in site.tags %}
  <div class="archive-group">
    {% capture tag_name %}{{ tag | first }}{% endcapture %}
    <div id="#{{ tag_name | slugize }}"></div>
    <h2 class="tag-head">{{ tag_name }}</h2>
    <a name="{{ tag_name | slugize }}"></a>
    {% for post in site.tags[tag_name] %}
        <ul>
            <h3><a href="{{ post.url }}">{{ post.title }}</a></h3>
                {{ post.excerpt }}
      <hr>
      </ul>
    {% endfor %}
  </div>
{% endfor %}
     
