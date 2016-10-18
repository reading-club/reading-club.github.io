---
layout: page
title: Members
subtitle: Reading Club Members
permalink: /members
---


## ANN-comp-neurosci

<ul>
{% for member in site.data.members %}
<li>
{{ member.id }}: <a href="{{ member.link }}">{{ member.link }}</a>
   </li>
{% endfor %}
</ul>

The list generated from a data file. If you find your id missing or incorrect, speak up in the wechat group. More info can be displayed here on demand.
