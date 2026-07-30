---
layout: page
permalink: /publications/
title: Research
description: Working papers and publications in game theory, mechanism design, and international economics.
nav: true
nav_order: 1
banner: /assets/img/banners/research.jpg
banner_title: Research
banner_caption: Barcelona, where I completed my PhD
_styles: >
  .post-header { display: none; }
---

<!-- _pages/publications.md -->

{% include page_banner.liquid %}

<div class="publications">

<h2 class="bibliography-section-title">Published &amp; Accepted</h2>
{% bibliography --query @*[status=published] %}

<h2 class="bibliography-section-title">Working Papers</h2>
{% bibliography --query @*[status=working] %}

<h2 class="bibliography-section-title">Research in Progress</h2>
{% bibliography --query @*[status=inprogress] %}

</div>
