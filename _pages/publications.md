---
layout: page
permalink: /publications/
title: publications
description: "* denotes equal contribution"
nav: true
nav_order: 2
---

<!-- _pages/publications.md -->

<!-- Bibsearch Feature -->

Full list on [Google Scholar](https://scholar.google.com/citations?user=lcFgmFEAAAAJ).

{% include bib_search.liquid %}

<div class="publications">

<h2 class="bibliography-section">preprints &amp; manuscripts</h2>

{% bibliography --query @*[status=preprint] %}

<h2 class="bibliography-section">peer-reviewed</h2>

{% bibliography --query @*[status!=preprint] %}

</div>
