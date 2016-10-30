---
layout: clubs
title:  "The 5-Week+"
subtitle: ""
info: 10:00 PM, Sunday, GMT+8
status: OPEN
date: 2016-10-18
gitter: reading-club/Lobby
---

<section class="alert--box">
<span class="title-notification--box">Upcoming Event</span>
{% assign noti = site.data.notifications |  where:"event","5-week-plus" %}
<p><a href="{{ noti[0].link }}">{{ noti[0].upcoming }}</a></p>
<p>{{ noti[0].schedule }}, <span><a href="{{ noti[0].timezone }}">tool for different timezones</a></span></p>
</section>>



<ul class="list-posts">
{% for post in site.5weekplus %}
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




