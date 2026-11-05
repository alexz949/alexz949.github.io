---
layout: about
title: about
permalink: /
subtitle: M.S. student in Computer Science, Duke University

profile:
  align: right
  image: prof_pic.jpg # photo in assets/img/
  image_circular: false # crops the image to make it circular

selected_papers: false # the theme's block is titled "selected publications"; "selected papers" is added at the end of this page instead
social: true # includes social icons at the bottom of the page

announcements:
  enabled: false # set to true once there are items in the `_news` folder
  scrollable: true # adds a vertical scroll bar if there are more than 3 news items
  limit: 5 # leave blank to include all the news in the `_news` folder

latest_posts:
  enabled: true
  scrollable: true # adds a vertical scroll bar if there are more than 3 new posts items
  limit: 3 # leave blank to include all the blog posts
---

I'm a second-year M.S. student in the Department of Computer Science at Duke University, where I am a member of the [CEI Lab](https://cei.pratt.duke.edu/) advised by [Prof. Yiran Chen](https://ece.duke.edu/people/yiran-chen/). My research interests lie in **efficient machine learning**, with a particular focus on large language models. I am motivated by making modern AI systems faster, cheaper, and easier to deploy, while preserving the capabilities that matter. Currently, I am exploring efficient inference for large language models.

I obtained a B.S. in Computer Science and Statistical Science from Wake Forest University, where I was fortunate to conduct undergraduate research advised by [Dr. Grey Ballard](https://users.wfu.edu/ballard/). Much of my work there focused on numerical linear algebra: developing efficient algorithms for CP tensor decomposition based on alternating least squares with QR, which led to a first-author paper in _SIAM Journal on Matrix Analysis and Applications_.

<style>
  /* Smaller profile photo than the theme's 30% (100% on phones). */
  @media (min-width: 576px) {
    .profile { width: 22%; }
  }
  @media (max-width: 575.98px) {
    .profile.float-right { float: none !important; max-width: 220px; margin: 0 auto 1rem; }
  }
  .paper-box {
    border: 1px solid var(--global-divider-color);
    border-radius: 0.5rem;
    padding: 1rem 1.25rem 0.25rem;
    margin-bottom: 1.25rem;
  }
  .paper-box h3 { margin-top: 0; font-size: 1.15rem; }
</style>

<h2 style="clear: both"><a href="{{ '/papers/' | relative_url }}" style="color: inherit">selected papers</a></h2>

<div class="paper-box">
  <h3>publications</h3>
  <div class="publications">
    {% bibliography --group_by none --query @*[selected=true && status!=preprint]* %}
  </div>
</div>

<div class="paper-box">
  <h3>preprints</h3>
  <div class="publications">
    {% bibliography --group_by none --query @*[selected=true && status=preprint]* %}
  </div>
</div>
