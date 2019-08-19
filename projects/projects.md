---
layout: page
title: "Articles, Projects & Plans"
permalink: "/projects/"
redirect_from:
  - "/plans/"
  - "/articles/"
image: /projects/projects-splash.jpg
back_btn_link: "/"
back_btn_text: "Back to the Main Page"
---
<hr class="hr-thick" style="margin-bottom: 30px;">
## Articles

{% for post in site.categories.article %}

{% capture theUrl %}{{ post.url }}?from=articles{% endcapture %}

### [{{ post.title }}]({{ theUrl }})

[![]({{ post.article-image }}){: width="150px"}]({{ theUrl }}){: .align-left}
{{ post.article-description }}

{:style="clear: left"}

{% endfor %}

<hr class="hr-thick" style="margin-bottom: 30px;">

## Projects (that may have plans)

{% include pic-and-link-line.html
  name="Micro-Adjuster for Table Saw Fences"
  link="/projects/microadjuster/"
  image="/projects/microadjuster/2019-07-08.1.02.jpg" %}

{% include pic-and-link-line.html
  name="Chisel Plane & Sheath"
  link="/projects/chisel_plane/"
  image="/projects/chisel_plane/chisel_plane_and_sheath_150.png" %}

{% include pic-and-link-line.html
  name="Router Lift"
  link="/projects/routerlift/"
  image="/projects/routerlift/router_lift_150.png" %}

{% include pic-and-link-line.html
  name="Corner Clamp"
  link="/projects/cornerclamp/"
  image="/projects/cornerclamp/corner_clamp_150.png" %}

{% include pic-and-link-line.html
  name="Corn Cob Skewers"
  link="/projects/corncobskewers/"
  image="/projects/corncobskewers/corn_cob_skewers_150.jpg" %}

