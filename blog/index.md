---
layout: splash
author_profile: true
comments: false
feature_row1:
  - image_path: /assets/images/teaser.png
    alt: "placeholder image 2"
    title: "Ishaan Kon - The Sushant Singh Rajput story"
    excerpt: 'How he lived in the intersection of two worlds, and what he meant to me as I was growing up'
    url: "/blogposts/ishaan-kon"
    btn_label: "Read More"
    btn_class: "btn--primary"
feature_row:
  - image_path: "/assets/images/four-year-teaser.svg"
    alt: "placeholder image 1"
    title: "The Four Year Transform"
    excerpt: "An essay with random fundae on college life packaged in a giant pun"
    url: "/blogposts/Fourier"
    btn_label: "Read More"
    btn_class: "btn--primary"
  - image_path: /assets/images/lee-teaser.svg
    alt: "placeholder image 2"
    title: "Volumes of spheres in discrete metrics"
    excerpt: "On our paper 'A method to find the volume of a sphere in the Lee metric, and its applications'"
    url: "/blogposts/leemetric"
    btn_label: "Read More"
    btn_class: "btn--primary"
  - image_path: /assets/images/april-2019-teaser.svg
    alt: "placeholder image 3"
    title: "One More April Puzzle"
    excerpt: "One more special puzzle to celebrate April Fools Day"
    url: "/blogposts/One-More-April-Puzzle/"
    btn_label: "Read More"
    btn_class: "btn--primary"
---
<br>
# New Post
{% include feature_row id="feature_row1" type="left" %}

# Recent Posts
{% include feature_row id="feature_row" %}

# Older Posts

{% assign counter = 0 %}

{% for post in site.posts %}
	{% if post.categories contains "travel" %}
	{% elsif post.categories contains "writing" %}
	{% else %}
        {% assign counter = counter | plus: 1 %}
        {% if counter > 4 %}
  		    {% include archive-single.html %}
        {% endif %}
	{% endif %}
{% endfor %}    