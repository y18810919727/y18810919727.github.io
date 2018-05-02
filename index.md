---
layout: default
title: my blogggggggggg
---

# ACM
{% for post in site.posts %}
{% if post.tag == 'acm' %}
 [{{post.date | date_to_string}} {{post.title}}]({{post.url}})
{% endif %}
{%endfor%}

# Machine Learning 
{% for post in site.posts %}
{% if post.tag == 'ml' %}
 [{{post.date | date_to_string}} {{post.title}}]({{post.url}})
{% endif %}
{%endfor%}

# NLP 
{% for post in site.posts  %}
{% if post.tag == 'nlp' %}
 [{{post.date | date_to_string}} {{post.title}}]({{post.url}})
{% endif %}
{%endfor%}

# Statistics 
{% for post in site.posts  %}
{% if post.tag == 'statistics' %}
 [{{post.date | date_to_string}} {{post.title}}]({{post.url}})
{% endif %}
{%endfor%}

# OTHERS 
{% for post in site.posts  %}
{% if post.tag == 'others' %}
 [{{post.date | date_to_string}} {{post.title}}]({{post.url}})
{% endif %}
{%endfor%}
