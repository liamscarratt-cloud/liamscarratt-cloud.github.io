---
layout: archive
title: "Sitemap"
permalink: /sitemap/
author_profile: true
---

{% include base_path %}

A list of all the posts and pages found on the site. For you robots out there, there is an [XML version]({{ base_path }}/sitemap.xml) available for digesting as well.

<h2>Pages</h2>
<ul>
{% for post in site.pages %}
{% if post.title %}
<li><a href="{{ base_path }}{{ post.url }}">{{ post.title }}</a></li>
{% endif %}
{% endfor %}
</ul>

{% if site.posts.size > 0 %}
<h2>Posts</h2>
<ul>
{% for post in site.posts %}
<li><a href="{{ base_path }}{{ post.url }}">{{ post.title }}</a></li>
{% endfor %}
</ul>
{% endif %}

{% for collection in site.collections %}
{% unless collection.output == false or collection.label == "posts" %}
{% if collection.docs.size > 0 %}
<h2>{{ collection.label | capitalize }}</h2>
<ul>
{% for post in collection.docs %}
<li><a href="{{ base_path }}{{ post.url }}">{{ post.title }}</a></li>
{% endfor %}
</ul>
{% endif %}
{% endunless %}
{% endfor %}
