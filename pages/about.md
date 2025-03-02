---
layout: page
title: About
permalink: /about/
weight: 3
---

# **About Me**

Hi I am **{{ site.author.name }}** :wave:,<br>
I learn about different languages in the world. Currently, I have a hobby and work as an <b>IT Networking, Linux Server Administrator, and Electrical Technician.</b>

<div class="row">
{% include about/skills.html title="Native Languages" source=site.data.native-languages-skills %}
{% include about/skills.html title="Other Skills" source=site.data.other-skills %}
</div>

<div class="row">
{% include about/timeline.html %}
</div>