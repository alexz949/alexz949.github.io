---
layout: page
permalink: /papers/
title: papers
description: "* denotes equal contribution"
nav: true
nav_order: 2
---

<!-- _pages/papers.md -->

Full list on [Google Scholar](https://scholar.google.com/citations?user=lcFgmFEAAAAJ).

<!-- Bibsearch Feature -->

{% include bib_search.liquid %}

<div class="publications">

<h2 class="bibliography-section">publications</h2>

{% bibliography --query @*[status!=preprint] %}

<h2 class="bibliography-section">preprints</h2>

{% bibliography --query @*[status=preprint] %}

</div>
