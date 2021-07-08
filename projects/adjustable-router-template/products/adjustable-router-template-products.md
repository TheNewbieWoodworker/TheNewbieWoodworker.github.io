---
title: "Products: Adjustable Router Template Jig"
layout: post
video-id: "rSv1CA7aoeE"
permalink: "/projects/adjustable-router-template/products/"
back_btn_link: "/projects/adjustable-router-template/"
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
