---
layout: page
title: "Products"
permalink: "/products/"
---
I'm just starting to organize this, so right now everything's on one page. But that will change soon, I promise.

You can use your browser's search function to search through this list. For most desktop browsers, just tap Control+F or Command+F.

{% for product_hash in site.data.products %}
{% assign product = product_hash[1] %}

{% if jekyll.environment == "development" %}
<hr class="hr-thick" style="margin-bottom: 30px;">
{% endif %}

{% include product-link-from-data.html data=product %}
{% if jekyll.environment == "development" %}
{&#37; include product-link-from-data.html data=site.data.products.{{ product.id }} &#37;}

<p style="margin-bottom: 0px"><b>Categories</b></p>

{% for category in product.categories %}
<p style="margin-bottom: 0px">&nbsp;&nbsp;&nbsp;&nbsp;{{ category.name }}</p>
{% endfor %}

<p style="margin-bottom: 0px">&nbsp;</p>

{% include product-link-from-data.html data=product output-youtube-text=true %}

{% endif %}
{% endfor %}

---
