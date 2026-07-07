---
layout: page
title: About
permalink: /about/
---
<div class="about-header">
  <img class="about-header__photo" src="{{ '/assets/images/profile-placeholder.svg' | relative_url }}" alt="Profile photo placeholder">
  <div>
    <p>
      <!-- Replace this paragraph with a couple of sentences about yourself:
           what you work on, what you're curious about, why this site exists. -->
      Placeholder bio. Replace this paragraph with a short blurb about who you
      are, what you research or build, and what to expect from this site.
    </p>
  </div>
</div>

<ul class="about-links">
  <li><a href="https://github.com/{{ site.author.github }}">GitHub</a></li>
  <li>
    <!-- Replace # with your institutional/academic homepage once you have one. -->
    <a href="#">Academic homepage (add link)</a>
  </li>
  <li>
    <!-- Add your CV as assets/cv/cv.pdf and update this link. -->
    <a href="{{ '/assets/cv/cv.pdf' | relative_url }}">CV (add PDF)</a>
  </li>
</ul>

To replace the photo, drop a real image at
`assets/images/profile.jpg` (or similar) and update the `src` above. To add a
CV, drop a PDF at `assets/cv/cv.pdf` -- see `assets/cv/README.md`.
