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

{% include paper_box_style.liquid %}

<div class="paper-box">
  <h2 class="bibliography-section">publications</h2>
  <div class="publications">
    {% bibliography --query @*[status!=preprint] %}
  </div>
</div>

<div class="paper-box">
  <h2 class="bibliography-section">preprints</h2>
  <div class="publications">
    {% bibliography --query @*[status=preprint] %}
  </div>
</div>
