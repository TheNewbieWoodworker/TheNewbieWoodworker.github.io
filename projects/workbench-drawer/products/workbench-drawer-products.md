---
title: "Products: Under-Workbench Drawer"
layout: post
video-id: "WGTKtKyAtL8"
permalink: "/projects/workbench-drawer/products/"
back_btn_link: "/projects/workbench-drawer/"
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
