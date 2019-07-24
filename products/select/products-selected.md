---
layout: page
title: "Selected Products"
permalink: "/products/selected/"
---
{% for product_hash in site.data.products-selected %}
{% assign selected-product = product_hash[1] %}
{% assign product = site.data.products[selected-product.id] %}

[↑](kmtrigger://macro=FD4E7F5F-35EF-4FFB-B0E0-D23B98EDD509&value={{ product.id }})
[↓](kmtrigger://macro=484F7855-6DB7-4CAB-9B27-8B64783B1159&value={{ product.id }})
[✖︎](kmtrigger://macro=E63B0BE5-650D-487D-A27D-FAB669FB4C72&value={{ product.id }})
{{ product.title }}: [{{ product.link }}](product.link){:target=_blank}

{% endfor %}