---
title: "Products: How to Make Knobs for Shop Jigs"
layout: post
video-id: "Di_xHYgCE88"
permalink: "/projects/knobs/products/"
back_btn_link: "/projects/knobs/"
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