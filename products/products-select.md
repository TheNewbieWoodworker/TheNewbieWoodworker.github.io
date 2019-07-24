---
layout: page
title: "Select Products"
permalink: "/products/select/"
---
{% for product_hash in site.data.products %}
{% assign product = product_hash[1] %}

<div id="{{ product.id }}" {% if site.data.products-selected[product.id] %}style="display: none"{% endif %}>

<hr class="hr-thick" style="margin-bottom: 30px;">

<a href="kmtrigger://macro=5FF062AE-14FA-4D29-9A41-53F13DA766B5&value={{ product.id }}">Select</a>

{% include product-link-from-data.html data=product %}

{&#37; include product-link-from-data.html data=site.data.products.{{ product.id }} &#37;}

<p style="margin-bottom: 0px"><b>Categories</b></p>

{% for category in product.categories %}
<p style="margin-bottom: 0px">&nbsp;&nbsp;&nbsp;&nbsp;{{ category.name }}</p>
{% endfor %}

<p style="margin-bottom: 0px">&nbsp;</p>

{% include product-link-from-data.html data=product output-youtube-text=true %}

</div>

{% endfor %}

---
