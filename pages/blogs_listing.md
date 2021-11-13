---
layout: default
title: Blogs 
permalink: /blogs/
---

### Recent Blogs

[comment]: <> ([Transformer Model: Self Attentios: Implementation with In-Depth Details]&#40;&#41;)
[Transformer Model: Self Attentios: Implementation with In-Depth Details]({{ site.baseurl }}/blogs/001)

[comment]: <> (![_config.yml]&#40;&#41;)
{% for post in site.posts %}

[{{ post.title }}]({{ site.baseurl }}{{ post.url }})
{{ post.excerpt }}

{% endfor %}
