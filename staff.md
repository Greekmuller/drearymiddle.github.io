---
layout: default
title: Staff
---
# {{ page.title }}
Below is a list of all the people who make this site possible. Toiling endlessly into the night to bring you articles, podcasts and just all round great entertainment! Click on someone below to find out more and see some of their latest posts!
<div class="blogList">
  {% for author in site.authors %}
  <hr>
    <br>
    <div class="avatar"><img src="{{ author.avatar }}" width="100px" style="float: left; margin-right:30px; margin-bottom:20px;"></div>
    <div class="avatarBG"><img src="{{ author.avatar }}" width="105px" style="float: left;"></div>
    <h2><a href="{{ author.url }}" style="text-decoration: none; color: #959494;">{{ author.name }}</a></h2>  
    <h3>{{ author.position }}</h3>
    <a class="twitter-follow-button" data-dnt="true" data-show-count="false" data-size="large" href="https://twitter.com/{{ author.name }}?ref_src=twsrc%5Etfw">Follow @{{ author.name }}</a><script async="" charset="utf-8" src="https://platform.twitter.com/widgets.js"></script>
    <p>{{ author.bio | markdownify }}</p>
    <br>
  {% endfor %}
</div>