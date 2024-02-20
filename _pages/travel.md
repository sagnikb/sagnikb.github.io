---
title: Travel
permalink: /categories/travel/
layout: splash
author_profile: true
comments: false
feature_row_1:
  - image_path: https://lh3.googleusercontent.com/AEGMC2r27QelVf2u75FEVgUKQIhuAzi0SNQOTX8Ir3ShdiR80NEMqTAMv_GNSHX0c5JF6YQqLYQnOHBb34Ood1NkMGXwk9i4cC1Zbd2dajUDsYjKeRqt6hO7-JLlJwe1hPdKFPmk3ME=w2400
    alt: "placeholder image 1"
    title: "Rome and (ancient) Romans"
    excerpt: "Finding ancient Rome in modern Rome"
    url: "/blogposts/rome"
    btn_label: "Read More"
    btn_class: "btn--primary"
  - image_path: https://lh3.googleusercontent.com/HzYHffuHa9Xt8_Ye480bg3rQrCeC4mlPlmswoZWbENkjjoBxQZEuim7my7zY1HtvYqfrEFCknk_EmzudbQ5xOY-85_JbpLvtww4gMQjt3Dl-1IRtZntsLXEn3kXrfirMFcd7zbBhUOw=w2400
    alt: "placeholder image 1"
    title: "To the bit of my heart I left in Hong Kong"
    excerpt: "My stay in the city, more than a year on"
    url: "/blogposts/Hong_Kong"
    btn_label: "Read More"
    btn_class: "btn--primary"
  - image_path: https://lh3.googleusercontent.com/sVdrx9HpJ7sdKujkvHpXpFS2-rzPvPF5XJoQtuBBAHLHRQy8xHMmSBgATfcVUxCr7JaO9FmkVCHoOwTOWWm1HpeyetT1ZyFhIAwOiMXIg1u7YvEemX234vc7M1rW__4_POwE0buNV84=w2400
    alt: "placeholder image 2"
    title: "Bangkok Old Town"
    excerpt: "Adventures in the old city of Bangkok"
    url: "/blogposts/bangkok"
    btn_label: "Read More"
    btn_class: "btn--primary"
feature_row_2:
  - image_path: https://lh3.googleusercontent.com/X_PacZ3khsc-S_GG2txmxwESRJ6sTw4ZLa-qbGs7LP3eDX-7uQcfUCmkmaxkG48mOopcbb-EwsoDZR14qP4By6B7PZt6w9cR_CYHcycBBl36MWHCbYuCdZvt9xpTyHWPSh262JABcE0=w2400
    alt: "placeholder image 2"
    title: "Rajasthan on the Feluda Trail"
    excerpt: "How our Rajasthan trip followed a beloved fictional journey"
    url: "/blogposts/rajasthan"
    btn_label: "Read More"
    btn_class: "btn--primary"
---
<br>
<h1> Travel </h1>

{% for post in site.posts %}
	{% if post.categories contains "travel" %}
  		{% include archive-single.html %}
	{% endif %}
{% endfor %}