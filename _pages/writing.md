---
layout: page
permalink: /writing/
title: writing
description: research papers and philosophy essays. none of these are formally published — they are course projects and things I wrote for fun.
nav: true
nav_order: 2
---

<!-- _pages/writing.md -->

<!-- Bibsearch Feature -->

{% include bib_search.liquid %}

<h2 class="mt-4">research</h2>

<div class="publications">

{% bibliography --query @*[category=research] %}

</div>

<h2 class="mt-5">philosophy</h2>

<div class="publications">

{% bibliography --query @*[category=philosophy] %}

</div>
