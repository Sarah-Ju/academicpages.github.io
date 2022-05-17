---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

You can also find my articles on <a href="https://www.researchgate.net/profile/Sarah-Juricic">my Researchgate profile</a>.

Also, check out <a href="/posts/2022/01/researchjourney/">here</a> a roadmap to my research journey (/!\under construction).

{% include base_path %}

{% for post in site.publications reversed %}
  {% include archive-single.html %}
{% endfor %}
