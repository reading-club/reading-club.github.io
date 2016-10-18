---
layout: clubs
title:  "The 5 Weeks"
subtitle: ""
info: 10:00 PM, Sunday, GMT+8
status: OPEN
date: 2016-10-18
gitter: reading-club/Lobby
---


<ul class="list-posts">
{% for post in site.rotations %}
<li class="post-teaser">
    <a href="{{ site.url }}{{ post.url | prepend: site.baseurl }}">
        <span class="post-teaser__title">{{ post.title }}</span>
        </a>
        <div class="post-teaser__infoblock">
        <span class="post-teaser__schedule">
<i class="fa fa-calendar-o" aria-hidden="true"></i> Date: {{ post.schedule }}</span>
        <br>
        <span class="post-teaser__speaker"><i class="fa fa-user" aria-hidden="true"></i> Speaker: {{ post.speaker }}</span>
        <br>
        <span class="post-teaser__references"><i class="fa fa-paperclip" aria-hidden="true"></i> References: </span><br>
        {% for item in post.ref %}
        <span class="post-teaser__reflist"><a href="{{ item }}">{{ item }}</a></span>
        {% endfor %}
        </div>
    
</li>
{% endfor %}
</ul>




