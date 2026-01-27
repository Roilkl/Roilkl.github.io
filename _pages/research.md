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

<div id="pdf-list" class="pdf-list-container">
  <div class="loading-spinner">
    <div class="spinner"></div>
    <p>Loading publications from GitHub...</p>
  </div>
</div>

<!-- PDF预览模态框 -->
<div id="pdf-modal" class="pdf-modal">
  <div class="pdf-modal-content">
    <span class="pdf-modal-close">&times;</span>
    <iframe id="pdf-viewer" style="width: 100%; height: 85vh;" frameborder="0"></iframe>
  </div>
</div>

<style>
/* 加载动画 */
.loading-spinner {
  text-align: center;
  padding: 40px;
}

.spinner {
  border: 4px solid #f3f3f3;
  border-top: 4px solid #3498db;
  border-radius: 50%;
  width: 40px;
  height: 40px;
  animation: spin 2s linear infinite;
  margin: 0 auto 15px;
}

@keyframes spin {
  0% { transform: rotate(0deg); }
  100% { transform: rotate(360deg); }
}

/* PDF列表样式 */
.pdf-list-container {
  margin-top: 30px;
}

.publication-list {
  list-style: none;
  padding: 0;
}

.publication-item {
  background: #fff;
  border: 1px solid #e1e4e8;
  border-radius: 8px;
  padding: 20px;
  margin-bottom: 20px;
  transition: all 0.3s ease;
  box-shadow: 0 2px 4px rgba(0,0,0,0.05);
}

.publication-item:hover {
  box-shadow: 0 4px 12px rgba(0,0,0,0.1);
  transform: translateY(-2px);
  border-color: #0366d6;
}

.publication-header {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  margin-bottom: 15px;
}

.publication-title {
  margin: 0;
  color: #24292e;
  font-size: 1.2em;
  flex: 1;
}

.publication-date {
  color: #6a737d;
  font-size: 0.9em;
  white-space: nowrap;
  margin-left: 15px;
}

.publication-meta {
  color: #586069;
  font-size: 0.95em;
  margin-bottom: 15px;
}

.publication-links {
  display: flex;
  gap: 10px;
  flex-wrap: wrap;
}

/* 按钮样式 */
.btn {
  display: inline-block;
  padding: 8px 16px;
  border-radius: 6px;
  text-decoration: none;
  font-weight: 500;
  font-size: 0.9em;
  transition: all 0.2s;
  border: none;
  cursor: pointer;
}

.btn--primary {
  background-color: #dc3545;
  color: white;
}

.btn--primary:hover {
  background-color: #c82333;
  color: white;
}

.btn--secondary {
  background-color: #6c757d;
  color: white;
}

.btn--secondary:hover {
  background-color: #5a6268;
  color: white;
}

.btn--github {
  background-color: #24292e;
  color: white;
}

.btn--github:hover {
  background-color: #1b1f23;
  color: white;
}

.btn--view {
  background-color: #28a745;
  color: white;
}

.btn--view:hover {
  background-color: #218838;
  color: white;
}

.btn--info {
  background-color: #17a2b8;
  color: white;
}

.btn--info:hover {
  background-color: #138496;
}

.btn i {
  margin-right: 5px;
}

/* 模态框样式 */
.pdf-modal {
  display: none;
  position: fixed;
  z-index: 1000;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0,0,0,0.8);
}

.pdf-modal-content {
  position: relative;
  background-color: #fefefe;
  margin: 5% auto;
  padding: 20px;
  border: 1px solid #888;
  width: 90%;
  max-width: 1200px;
  border-radius: 8px;
  animation: modalopen 0.3s;
}

@keyframes modalopen {
  from {opacity: 0; transform: translateY(-30px);}
  to {opacity: 1; transform: translateY(0);}
}

.pdf-modal-close {
  position: absolute;
  right: 20px;
  top: 10px;
  color: #aaa;
  font-size: 28px;
  font-weight: bold;
  cursor: pointer;
  z-index: 1001;
}

.pdf-modal-close:hover {
  color: #000;
}

/* 空状态 */
.empty-state {
  text-align: center;
  padding: 40px;
  color: #6c757d;
}

.empty-state i {
  font-size: 48px;
  margin-bottom: 20px;
  color: #e9ecef;
}

/* 响应式设计 */
@media (max-width: 768px) {
  .publication-header {
    flex-direction: column;
  }
  
  .publication-date {
    margin-left: 0;
    margin-top: 5px;
  }
  
  .publication-links {
    flex-direction: column;
  }
  
  .btn {
    width: 100%;
    text-align: center;
    margin-bottom: 5px;
  }
}
</style>

<script>
// 动态获取GitHub仓库中的PDF文件
async function loadPDFs() {
  const repo = 'Roilkl/note';  // 你的笔记仓库
  const apiUrl = `https://api.github.com/repos/${repo}/contents/`;
  
  try {
    const response = await fetch(apiUrl);
    if (!response.ok) {
      throw new Error(`GitHub API error: ${response.status}`);
    }
    
    const files = await response.json();
    
    const pdfList = document.getElementById('pdf-list');
    
    // 筛选PDF文件
    const pdfFiles = files.filter(file => 
      file.name.toLowerCase().endsWith('.pdf') && 
      file.type === 'file'
    );
    
    if (pdfFiles.length === 0) {
      pdfList.innerHTML = `
        <div class="empty-state">
          <i class="fas fa-file-pdf"></i>
          <h3>No publications found</h3>
          <p>Upload PDF files to the <a href="https://github.com/Roilkl/note" target="_blank">Roilkl/note</a> repository to see them here.</p>
        </div>
      `;
      return;
    }
    
    // 按修改时间排序（最新的在前）
    pdfFiles.sort((a, b) => new Date(b.updated_at) - new Date(a.updated_at));
    
    // 生成列表
    let html = '<ul class="publication-list">';
    
    pdfFiles.forEach(file => {
      // 格式化文件名
      const fileName = file.name.replace('.pdf', '');
      const displayName = fileName
        .replace(/_/g, ' ')
        .replace(/-/g, ' ')
        .split(' ')
        .map(word => word.charAt(0).toUpperCase() + word.slice(1))
        .join(' ');
      
      const rawUrl = `https://raw.githubusercontent.com/${repo}/main/${file.name}`;
      const githubUrl = `https://github.com/${repo}/blob/main/${file.name}`;
      const downloadUrl = `https://github.com/${repo}/raw/main/${file.name}`;
      
      // 格式化日期
      const date = new Date(file.updated_at);
      const formattedDate = date.toLocaleDateString('en-US', {
        year: 'numeric',
        month: 'short',
        day: 'numeric'
      });
      
      html += `
        <li class="publication-item">
          <div class="publication-header">
            <h3 class="publication-title">${displayName}</h3>
            <span class="publication-date">${formattedDate}</span>
          </div>
          
          <div class="publication-meta">
            <i class="fas fa-file-pdf"></i> PDF Document • ${(file.size / 1024).toFixed(1)} KB
          </div>
          
          <div class="publication-links">
            <button onclick="viewPDF('${rawUrl}')" class="btn btn--view">
              <i class="fas fa-eye"></i> View Online
            </button>
            
            <a href="${rawUrl}" target="_blank" class="btn btn--primary">
              <i class="fas fa-file-pdf"></i> Open PDF
            </a>
            
            <a href="${downloadUrl}" download class="btn btn--secondary">
              <i class="fas fa-download"></i> Download
            </a>
            
            <a href="${githubUrl}" target="_blank" class="btn btn--github">
              <i class="fab fa-github"></i> View on GitHub
            </a>
          </div>
        </li>
      `;
    });
    
    html += '</ul>';
    pdfList.innerHTML = html;
    
    // 添加字体awesome图标
    if (!document.querySelector('link[href*="font-awesome"]')) {
      const faLink = document.createElement('link');
      faLink.rel = 'stylesheet';
      faLink.href = 'https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css';
      document.head.appendChild(faLink);
    }
    
  } catch (error) {
    document.getElementById('pdf-list').innerHTML = `
      <div class="empty-state">
        <i class="fas fa-exclamation-triangle"></i>
        <h3>Unable to load publications</h3>
        <p>Error: ${error.message}</p>
        <p>Please check your internet connection and try again later.</p>
        <a href="https://github.com/Roilkl/note" target="_blank" class="btn btn--info">
          <i class="fab fa-github"></i> Visit GitHub Repository
        </a>
      </div>
    `;
    console.error('Error loading PDFs:', error);
  }
}

// PDF预览功能
function viewPDF(url) {
  const modal = document.getElementById('pdf-modal');
  const viewer = document.getElementById('pdf-viewer');
  const closeBtn = document.querySelector('.pdf-modal-close');
  
  viewer.src = `https://docs.google.com/viewer?url=${encodeURIComponent(url)}&embedded=true`;
  modal.style.display = 'block';
  
  // 点击关闭按钮
  closeBtn.onclick = function() {
    modal.style.display = 'none';
    viewer.src = '';
  }
  
  // 点击模态框外部关闭
  window.onclick = function(event) {
    if (event.target === modal) {
      modal.style.display = 'none';
      viewer.src = '';
    }
  }
}

// 页面加载完成后执行
document.addEventListener('DOMContentLoaded', function() {
  loadPDFs();
  
  // 添加键盘快捷键支持
  document.addEventListener('keydown', function(event) {
    const modal = document.getElementById('pdf-modal');
    if (event.key === 'Escape' && modal.style.display === 'block') {
      modal.style.display = 'none';
      document.getElementById('pdf-viewer').src = '';
    }
  });
});

// 可选：自动刷新功能（每5分钟检查一次更新）
setInterval(loadPDFs, 5 * 60 * 1000);
</script>

<hr>

<div class="callout">
  <h4><i class="fas fa-info-circle"></i> How to add new publications</h4>
  <p>Simply upload your PDF files to the <a href="https://github.com/Roilkl/note" target="_blank"><i class="fab fa-github"></i> Roilkl/note</a> repository. They will automatically appear here within a few minutes.</p>
  <p>File naming suggestions: Use descriptive names with underscores, e.g., <code>quantization_super_yang_mills.pdf</code></p>
</div>

<style>
.callout {
  background: #f8f9fa;
  border-left: 4px solid #0366d6;
  padding: 15px 20px;
  margin-top: 40px;
  border-radius: 4px;
}

.callout h4 {
  margin-top: 0;
  color: #0366d6;
}

.callout i {
  color: #0366d6;
  margin-right: 8px;
}
</style>
