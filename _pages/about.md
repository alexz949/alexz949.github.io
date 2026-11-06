---
layout: about
title: about
permalink: /
subtitle: M.S. student in Computer Science, Duke University

profile:
  align: right
  image: prof_pic.jpg # photo in assets/img/
  image_circular: false # crops the image to make it circular
  # Contact icons under the photo (styled in the <style> block below). Keep in sync with _data/socials.yml.
  more_info: >
    <div class="profile-links">
    <a href="mailto:zhanglixun67@gmail.com" title="Email"><i class="fa-solid fa-envelope"></i></a>
    <a href="https://github.com/alexz949" title="GitHub" rel="external nofollow noopener" target="_blank"><i class="fa-brands fa-github"></i></a>
    <a href="https://scholar.google.com/citations?user=lcFgmFEAAAAJ" title="Google Scholar" rel="external nofollow noopener" target="_blank"><i class="ai ai-google-scholar"></i></a>
    </div>

selected_papers: false # the theme's block is titled "selected publications"; "selected papers" is added at the end of this page instead
social: false # contact icons are shown under the photo instead (profile.more_info)

announcements:
  enabled: false # set to true once there are items in the `_news` folder
  scrollable: true # adds a vertical scroll bar if there are more than 3 news items
  limit: 5 # leave blank to include all the news in the `_news` folder

latest_posts:
  enabled: true
  scrollable: true # adds a vertical scroll bar if there are more than 3 new posts items
  limit: 3 # leave blank to include all the blog posts
---

I'm a second-year M.S. student in the Department of Computer Science at Duke University, where I am a member of the [CEI Lab](https://cei.pratt.duke.edu/) advised by [Prof. Yiran Chen](https://ece.duke.edu/people/yiran-chen/).

My research interests lie in numerical linear algebra and efficient algorithms for foundation models, with an emphasis on structured computation and parallel algorithms. I enjoy finding cool structures and playing matrix tricks on them :)

I obtained a B.S. in Computer Science and Statistical Science from Wake Forest University, where I was fortunate to conduct undergraduate research advised by [Dr. Grey Ballard](https://users.wfu.edu/ballard/). Much of my work there focused on numerical linear algebra and tensor decompositions.

<style>
  /* Smaller profile photo than the theme's 30% (100% on phones). */
  @media (min-width: 576px) {
    .profile { width: 22%; }
  }
  .profile .more-info .profile-links {
    display: flex;
    justify-content: center;
    gap: 1.1rem;
    margin-top: 0.6rem;
    font-size: 1.6rem;
  }
  .profile-links a { color: var(--global-text-color); }
  .profile-links a:hover { color: var(--global-theme-color); }
  @media (max-width: 575.98px) {
    .profile.float-right { float: none !important; max-width: 220px; margin: 0 auto 1rem; }
  }
</style>

{% include paper_box_style.liquid %}

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
