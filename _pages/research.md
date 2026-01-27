---
title: Research
permalink: /research/
layout: single
author_profile: true
---

## Research Overview

My research focuses on mathematical physics and string theory. Following represent my recent research projects.

I particularly recommend the note **"Quantization of N = 1 Super-Yang–Mills Theory"**, in which we uncover the D-module structure on N=1 superspace and systematically construct the BV complex and the quantization of Super-Yang–Mills theory. It's a coarse note and I'm still polishing it, so welcome to every suggestions!

---

## Publications & Notes

{% for note in site.data.notes %}
<div class="publication">
  <h3>{{ note.title }}</h3>
  <p>Size: {{ note.size_kb }} KB</p>
  <p>
    <a href="{{ note.url }}" target="_blank" class="btn">Open PDF</a>
    <a href="{{ note.github_url }}" target="_blank" class="btn">View on GitHub</a>
  </p>
</div>
<hr>
{% endfor %}
