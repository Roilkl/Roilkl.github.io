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
  <ul class="notes-list">
  {% for note in site.data.notes %}
    <li class="note-item">
      <div class="note-header">
        <h3>{{ note.title }}</h3>
        <span class="note-size">{{ note.size_kb }} KB</span>
      </div>
      <div class="note-links">
        <a href="{{ note.url }}" target="_blank" class="btn btn-pdf">
          <i class="fas fa-file-pdf"></i> Open PDF
        </a>
        <a href="{{ note.github_url }}" target="_blank" class="btn btn-github">
          <i class="fab fa-github"></i> View on GitHub
        </a>
      </div>
    </li>
  {% endfor %}
  </ul>
{% else %}
  <p>No notes available yet. Notes will appear here once the GitHub Actions workflow runs.</p>
  <p>You can manually trigger the update: 
    <a href="https://github.com/Roilkl/Roilkl.github.io/actions/workflows/update-notes.yml" target="_blank">
      Run workflow
    </a>
  </p>
{% endif %}
{% endraw %}

<style>
.notes-list {
  list-style: none;
  padding: 0;
}

.note-item {
  background: #fff;
  border: 1px solid #e1e4e8;
  border-radius: 6px;
  padding: 15px;
  margin-bottom: 15px;
}

.note-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 10px;
}

.note-header h3 {
  margin: 0;
  font-size: 1.1em;
  color: #24292e;
}

.note-size {
  color: #6a737d;
  font-size: 0.9em;
}

.note-links {
  display: flex;
  gap: 10px;
}

.btn {
  display: inline-block;
  padding: 6px 12px;
  border-radius: 4px;
  text-decoration: none;
  font-size: 0.9em;
  font-weight: 500;
}

.btn-pdf {
  background-color: #dc3545;
  color: white;
}

.btn-pdf:hover {
  background-color: #c82333;
  color: white;
}

.btn-github {
  background-color: #24292e;
  color: white;
}

.btn-github:hover {
  background-color: #1b1f23;
  color: white;
}

.btn i {
  margin-right: 5px;
}
</style>
