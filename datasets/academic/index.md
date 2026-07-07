---
layout: page
title: Academic Datasets
permalink: /datasets/academic/
---
Free datasets, released for research and non-commercial use.

<ul class="dataset-list">
  {% for d in site.data.datasets.academic %}
  <li class="dataset-card">
    <div class="dataset-card__info">
      <div class="dataset-card__title">{{ d.title }}</div>
      <p>{{ d.description }}</p>
      <div class="dataset-card__meta">{{ d.format }} &middot; {{ d.size }}</div>
    </div>
    <div class="dataset-card__action">
      <a class="btn" href="{{ d.download_url }}">Download</a>
    </div>
  </li>
  {% endfor %}
</ul>

To add a dataset, add an entry under `academic:` in `_data/datasets.yml` --
no template edits needed.
