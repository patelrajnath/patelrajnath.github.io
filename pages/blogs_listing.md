---
layout: default
title: Blogs 
permalink: /blogs/
---

# Recent Blogs
{% for post in site.posts %}
## [{{ post.title }}]({{ site.baseurl }}{{ post.url }})
 {{ post.excerpt }}
[Read More]({{ site.baseurl }}{{ post.url }})
{% endfor %}
