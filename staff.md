---
layout: default
title: Staff
---
<h1>Staff</h1>
<p>Below is a list of all the people who make this site possible. Toiling endlessly into the night to bring you articles, podcasts and just all round great entertainment! Click on someone below to find out more and see some of their latest posts!</p>
<ul>
  {% for author in site.authors %}
    <br>
    <div class="avatar"><img src="{{ author.avatar }}" width="100px" style="float: left; margin-right:30px; margin-bottom:20px;"></div>
    <div class="avatarBG"><img src="{{ author.avatar }}" width="105px" style="float: left;"></div>
    <h2><a href="{{ author.url }}" style="text-decoration: none; color: #959494;">{{ author.name }}</a></h2>  
    <h3>{{ author.position }}</h3>
    <p>{{ author.content | markdownify }}</p>
    <br><hr>
  {% endfor %}
</ul>