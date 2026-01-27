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

<div id="pdf-list">Loading notes...</div>

<script>
// 直接从GitHub获取PDF文件列表
async function loadNotes() {
  try {
    // GitHub API获取note仓库文件
    const response = await fetch('https://api.github.com/repos/Roilkl/note/contents/');
    const files = await response.json();
    
    // 筛选PDF文件
    const pdfFiles = files.filter(file => file.name.endsWith('.pdf'));
    
    const container = document.getElementById('pdf-list');
    
    if (pdfFiles.length === 0) {
      container.innerHTML = '<p>No notes found. Upload PDF files to <a href="https://github.com/Roilkl/note">Roilkl/note</a> repository.</p>';
      return;
    }
    
    // 按文件名排序
    pdfFiles.sort((a, b) => a.name.localeCompare(b.name));
    
    // 生成简单列表
    let html = '<ul>';
    pdfFiles.forEach(file => {
      const title = file.name.replace('.pdf', '').replace(/_/g, ' ');
      const pdfUrl = `https://raw.githubusercontent.com/Roilkl/note/main/${file.name}`;
      const githubUrl = `https://github.com/Roilkl/note/blob/main/${file.name}`;
      
      html += `
        <li style="margin-bottom: 15px; padding: 10px; border-left: 3px solid #dc3545; background: #f8f9fa;">
          <strong>${title}</strong><br>
          <a href="${pdfUrl}" target="_blank" style="margin-right: 10px;">📄 Open PDF</a>
          <a href="${githubUrl}" target="_blank">🔗 View on GitHub</a>
        </li>
      `;
    });
    html += '</ul>';
    
    container.innerHTML = html;
    
  } catch (error) {
    document.getElementById('pdf-list').innerHTML = 
      `<p style="color: red;">Error loading notes: ${error.message}</p>
       <p>Check if <a href="https://github.com/Roilkl/note">Roilkl/note</a> repository exists and is public.</p>`;
  }
}

// 页面加载时执行
document.addEventListener('DOMContentLoaded', loadNotes);
</script>
