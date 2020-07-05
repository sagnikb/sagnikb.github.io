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
  - image_path: "https://lh3.googleusercontent.com/bZQ4Ko5nw4pdURLvx3YSFA83XdlGoipkk7-oB5ENcewybwAxkEihFIjq9NQL_kLIML0WVL_7T-ljdeUdHy1zttBPOtlK9FZSEH7TpEcsJWc5bP0pOb-oY_b84a_HCttX9syz_s9SLrI=w2400"
    alt: "placeholder image 1"
    title: "The Four Year Transform"
    excerpt: "An essay with random fundae on college life packaged in a giant pun"
    url: "/blogposts/Fourier"
    btn_label: "Read More"
    btn_class: "btn--primary"
  - image_path: https://lh3.googleusercontent.com/kk18j989Eiks_OrirayG6o2MY6XMKLJ6VjqW3p1od0tJnn9_Vut3BHepPhbNKFxyi90Tty1Ji3tgMitM8_3PNlElGt38BGcI49B2aQa9_7auSEuh9qWfFNc9o8N5CmEeDYoo_teOcLA=w2400
    alt: "placeholder image 2"
    title: "Volumes of spheres in discrete metrics"
    excerpt: "On our paper 'A method to find the volume of a sphere in the Lee metric, and its applications'"
    url: "/blogposts/leemetric"
    btn_label: "Read More"
    btn_class: "btn--primary"
  - image_path: https://lh3.googleusercontent.com/XdgzglMnGLjJ4RMBlCX1S4gmCBt3nlqcJ9s3Wvq4zxMacm8kd_3fXMlVBuPCicm-Dr8EO_dbYlZwK4XHk2sEv1bflyCBOjThj0t10oeaXplAk12y_Ns4J8jAZu9gK9evIdS0KRLos6U=w2400
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