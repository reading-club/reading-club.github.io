---
layout: page
title: Members
subtitle: Reading Club Members
permalink: /members
---


## ANN-comp-neurosci


<div>
{% for member in site.data.members %}
        <div class="member">
            <div class="member-body">
                <div class="member-heading">{{ member.id }} [ <span><a href="{{ member.link }}"><i class="fa fa-github-alt" aria-hidden="true"></i></a></span> ] <small>{% if member.topics %}{% for topic in member.topics %}#{{ topic }} {% endfor %}{% endif %}</small></div>
                <div>{{ member.intro }}</div>
            </div>
        </div>
{% endfor %}
</div>



The list generated from a data file. If you find your id missing or incorrect, speak up in the wechat group. More info can be displayed here on demand.
