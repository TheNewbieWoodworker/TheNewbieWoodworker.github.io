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

{% include articles-all.html %}

<hr class="hr-thick">

<h2 style="margin-top: 40px">Projects With Plans or Build Articles</h2>

{% include projects-all.html has-plans="true" %}

<hr class="hr-thick">

<h2 style="margin-top: 40px">Other Projects</h2>

{% include projects-all.html has-plans="false" %}
