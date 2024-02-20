---
layout: single
classes: wide
title: <span style='background-color:#000;'>Thoughts, Quantized</span>
author_profile: true
comments: false
header:
  overlay_color: "#000"
  overlay_filter: "0.8"
  overlay_image: /assets/images/wordcloud.jpg
excerpt: <span style='background-color:#000;'>Sagnik (sometimes) blogs here</span>
feature_row1:
  - image_path: https://lh3.googleusercontent.com/kCOkqtqRGhf_etkDFoPT5UWUxrSqvPRmeW3HGfvkithBZtGuAUj03qTHr6ioBymhR8Mb7s-FtGe85qPwr4LMb9mcHMlgjDIF3AsUPTFrHxl6JjixljGAlZanHbJjqhIpiFinArqY0yo=w2400
    alt: "Friends / Distance = Drift?"
    title: "Friends / Distance = Drift?"
    excerpt: 'How to maintain long distance friendships?'
    url: "/blogposts/friends"
    btn_label: "Read More"
    btn_class: "btn--primary"
feature_row:
  - image_path: https://lh3.googleusercontent.com/cdMxkGJq0Zxq7087QNZHCu41ro3f5boLVrEIWQbGItSScHNbyKmDOsTpw11n_QRosTgZ4GHFaV1YDU--WAoHJV3anFChOaYH699dTIJzU--I1kzhDNpTb7GU1X5MQ_AV3yBXr4yS85I=w2400
    alt: "placeholder image 2"
    title: "Ishaan Kon - The Sushant Singh Rajput story"
    excerpt: 'How he lived in the intersection of two worlds, and what he meant to me as I was growing up'
    url: "/blogposts/ishaan-kon"
    btn_label: "Read More"
    btn_class: "btn--primary"
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
    excerpt: "Introducing a new technique based on generating functions"
    url: "/blogposts/leemetric"
    btn_label: "Read More"
    btn_class: "btn--primary"
---
{% assign counter = 0 %}

<!--- # Academics, research etc -->

{% for post in site.posts %}
	{% if post.categories contains "academic" %}
  		{% include archive-single.html %}
	{% endif %}
{% endfor %}
