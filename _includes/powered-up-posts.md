### Here's my blog posts for Steve Ramsey’s [“Powered Up”](https://theweekendwoodworker.com/powered-up){:target="_blank"} online course:

{% if include.sortOrder == "desc" %}
#### Oldest First | [Show Newest First](/poweredup/)

---

	{% for post in site.categories.PoweredUp reversed %}
	  {% include entry.html %}
	{% endfor %}
{% else %}
#### Newest First | [Show Oldest First](/poweredup/descending/)

---

	{% for post in site.categories.PoweredUp %}
	  {% include entry.html %}
	{% endfor %}
{%endif %}