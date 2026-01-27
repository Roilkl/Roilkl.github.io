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

{% raw %}
{% if site.data.notes %}
  <ul style="list-style: none; padding: 0;">
  {% for note in site.data.notes %}
    <li style="margin-bottom: 25px; padding: 15px; border: 1px solid #ddd; border-radius: 5px;">
      <h3 style="margin-top: 0;">{{ note.title }}</h3>
      <p>Size: {{ note.size_kb }} KB</p>
      <div>
        <a href="{{ note.url }}" target="_blank" style="background: #dc3545; color: white; padding: 8px 15px; border-radius: 4px; text-decoration: none; margin-right: 10px;">
          📄 Open PDF
        </a>
        <a href="{{ note.github_url }}" target="_blank" style="background: #24292e; color: white; padding: 8px 15px; border-radius: 4px; text-decoration: none;">
          🔗 View on GitHub
        </a>
      </div>
    </li>
  {% endfor %}
  </ul>
{% else %}
  <p>No notes available yet.</p>
{% endif %}
{% endraw %}
