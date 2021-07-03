---
title: "일상 Blog"
layout: archive
permalink: categories/blog
author_profile: true
sidebar_main: true
---


{% assign posts = site.categories.blog %}
<!--{% for post in posts %} {% include archive-single.html type=page.entries_layout %} {% endfor %}-->
{% for post in posts %} {% include archive-single.html %} {% endfor %}