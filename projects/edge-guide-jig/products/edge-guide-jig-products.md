---
title: "Products: Edge Guide Jig"
layout: post
video-id: "-Gh08iho1lw"
permalink: "/projects/edge-guide-jig/products/"
back_btn_link: "/projects/edge-guide-jig/"
back_btn_text: "Back to the Project"
---
{% assign products = site.data.products-by-video[page.video-id]  %}

{% if products %}
{% for product-item in products  %}

{% assign product = site.data.products[product-item.id] %}
{% include product-link-from-data.html data=product text=product-item.text %}
{% endfor %}

{% endif %}

<hr class="hr-thick" style="margin-bottom: 30px; clear: left"/>
