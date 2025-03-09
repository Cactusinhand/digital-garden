---
{"dg-publish":true,"permalink":"/使用 Claude-3.7 制作 SVG 图/","noteIcon":"default"}
---


## 什么是 API ？

1. 初始版本：

<?xml version="1.0" encoding="UTF-8" standalone="no"?>
<svg width="800" height="500" xmlns="http://www.w3.org/2000/svg">
  <!-- 背景 -->
  <rect width="800" height="500" fill="#f8f9fa" />
  <!-- 标题 -->
  <text x="400" y="50" font-family="Arial" font-size="24" text-anchor="middle" fill="#333">API（应用程序编程接口）</text>
  <!-- 应用程序 A -->
  <rect x="100" y="150" width="200" height="200" rx="10" ry="10" fill="#4285f4" opacity="0.8" />
  <text x="200" y="250" font-family="Arial" font-size="20" text-anchor="middle" fill="white">应用程序 A</text>
  <!-- 应用程序 B -->
  <rect x="500" y="150" width="200" height="200" rx="10" ry="10" fill="#34a853" opacity="0.8" />
  <text x="600" y="250" font-family="Arial" font-size="20" text-anchor="middle" fill="white">应用程序 B</text>
  <!-- API 层 -->
  <rect x="300" y="200" width="200" height="100" rx="10" ry="10" fill="#fbbc05" stroke="#ea4335" stroke-width="2" />
  <text x="400" y="250" font-family="Arial" font-size="20" text-anchor="middle" fill="#333">API</text>
  <!-- 连接线和箭头 -->
  <line x1="300" y1="220" x2="250" y2="220" stroke="#333" stroke-width="2" />
  <polygon points="250,220 260,215 260,225" fill="#333" />
  <line x1="500" y1="220" x2="550" y2="220" stroke="#333" stroke-width="2" />
  <polygon points="550,220 540,215 540,225" fill="#333" />
  <line x1="300" y1="280" x2="250" y2="280" stroke="#333" stroke-width="2" />
  <polygon points="300,280 290,275 290,285" fill="#333" />
  <line x1="500" y1="280" x2="550" y2="280" stroke="#333" stroke-width="2" />
  <polygon points="500,280 510,275 510,285" fill="#333" />
  <!-- 说明文字 -->
  <text x="400" y="350" font-family="Arial" font-size="16" text-anchor="middle" fill="#333">请求和响应通过 API 传递</text>
  <!-- 图例 -->
  <rect x="100" y="400" width="20" height="20" fill="#4285f4" opacity="0.8" />
  <text x="130" y="415" font-family="Arial" font-size="14" fill="#333">客户端应用</text>
  <rect x="250" y="400" width="20" height="20" fill="#34a853" opacity="0.8" />
  <text x="280" y="415" font-family="Arial" font-size="14" fill="#333">服务端应用</text>
  <rect x="400" y="400" width="20" height="20" fill="#fbbc05" stroke="#ea4335" stroke-width="2" />
  <text x="430" y="415" font-family="Arial" font-size="14" fill="#333">API 接口层</text>
  <line x1="550" y1="410" x2="580" y2="410" stroke="#333" stroke-width="2" />
  <polygon points="580,410 570,405 570,415" fill="#333" />
  <text x="600" y="415" font-family="Arial" font-size="14" fill="#333">数据流向</text>
</svg>


2. 第二版

<?xml version="1.0" encoding="UTF-8" standalone="no"?>
<svg width="800" height="700" xmlns="http://www.w3.org/2000/svg">
  <!-- 背景 -->
  <defs>
    <linearGradient id="bg-gradient" x1="0%" y1="0%" x2="100%" y2="100%">
      <stop offset="0%" style="stop-color:#f9f9f9;stop-opacity:1" />
      <stop offset="100%" style="stop-color:#f0f0f0;stop-opacity:1" />
    </linearGradient>
    <filter id="drop-shadow" x="-20%" y="-20%" width="140%" height="140%">
      <feGaussianBlur in="SourceAlpha" stdDeviation="3" />
      <feOffset dx="2" dy="2" result="offsetblur" />
      <feComponentTransfer>
        <feFuncA type="linear" slope="0.2" />
      </feComponentTransfer>
      <feMerge>
        <feMergeNode />
        <feMergeNode in="SourceGraphic" />
      </feMerge>
    </filter>
    <style type="text/css">
      @import url('https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500&amp;display=swap');
      .title { font-family: 'Roboto', sans-serif; font-weight: 500; }
      .subtitle { font-family: 'Roboto', sans-serif; font-weight: 400; }
      .body-text { font-family: 'Roboto', sans-serif; font-weight: 300; }
    </style>
  </defs>
  <rect width="800" height="700" fill="url(#bg-gradient)" />
  <!-- 标题区域 -->
  <rect x="100" y="30" width="600" height="80" rx="15" ry="15" fill="#6366F1" filter="url(#drop-shadow)" />
  <text x="400" y="70" class="title" font-size="28" text-anchor="middle" fill="white">什么是 API？</text>
  <text x="400" y="100" class="subtitle" font-size="16" text-anchor="middle" fill="white">Application Programming Interface（应用程序编程接口）</text>
  <!-- 定义区域 -->
  <rect x="100" y="130" width="600" height="100" rx="10" ry="10" fill="white" stroke="#E2E8F0" stroke-width="1" filter="url(#drop-shadow)" />
  <text x="120" y="160" class="subtitle" font-size="18" fill="#334155">定义</text>
  <text x="120" y="190" class="body-text" font-size="14" fill="#64748B">API（应用程序编程接口）是一种机制，允许不同的软件程序或服务之间进行通信和数据</text>
  <text x="120" y="210" class="body-text" font-size="14" fill="#64748B">交换。它就像是软件之间的"翻译官"或"服务员"，帮助它们相互理解和交流。</text>
  <!-- 图示区域 -->
  <rect x="150" y="250" width="500" height="250" rx="10" ry="10" fill="white" stroke="#E2E8F0" stroke-width="1" filter="url(#drop-shadow)" />
  <!-- 客户端 -->
  <ellipse cx="200" cy="350" rx="80" ry="100" fill="#FEF3C7" stroke="#F59E0B" stroke-width="1" />
  <text x="200" y="320" class="subtitle" font-size="16" text-anchor="middle" fill="#92400E">客户端</text>
  <image x="170" y="330" width="60" height="60" href="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCIgZmlsbD0ibm9uZSIgc3Ryb2tlPSIjOTI0MDBFIiBzdHJva2Utd2lkdGg9IjIiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgc3Ryb2tlLWxpbmVqb2luPSJyb3VuZCIgY2xhc3M9ImZlYXRoZXIgZmVhdGhlci11c2VyIj48cGF0aCBkPSJNMjAgMjF2LTJhNCA0IDAgMCAwLTQtNEg4YTQgNCAwIDAgMC00IDR2MiI+PC9wYXRoPjxjaXJjbGUgY3g9IjEyIiBjeT0iNyIgcj0iNCI+PC9jaXJjbGU+PC9zdmc+" />
  <!-- API -->
  <ellipse cx="400" cy="350" rx="80" ry="100" fill="#DBEAFE" stroke="#3B82F6" stroke-width="1" />
  <text x="400" y="320" class="subtitle" font-size="16" text-anchor="middle" fill="#1E40AF">API</text>
  <image x="370" y="330" width="60" height="60" href="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCIgZmlsbD0ibm9uZSIgc3Ryb2tlPSIjMUU0MEFGIiBzdHJva2Utd2lkdGg9IjIiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgc3Ryb2tlLWxpbmVqb2luPSJyb3VuZCIgY2xhc3M9ImZlYXRoZXIgZmVhdGhlci1jb2RlIj48cG9seWxpbmUgcG9pbnRzPSIxNiAxOCAyMiAxMiAxNiA2Ij48L3BvbHlsaW5lPjxwb2x5bGluZSBwb2ludHM9IjggNiAyIDEyIDggMTgiPjwvcG9seWxpbmU+PC9zdmc+" />
  <!-- 服务器 -->
  <ellipse cx="600" cy="350" rx="80" ry="100" fill="#D1FAE5" stroke="#10B981" stroke-width="1" />
  <text x="600" y="320" class="subtitle" font-size="16" text-anchor="middle" fill="#065F46">服务器</text>
  <image x="570" y="330" width="60" height="60" href="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCIgZmlsbD0ibm9uZSIgc3Ryb2tlPSIjMDY1RjQ2IiBzdHJva2Utd2lkdGg9IjIiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgc3Ryb2tlLWxpbmVqb2luPSJyb3VuZCIgY2xhc3M9ImZlYXRoZXIgZmVhdGhlci1zZXJ2ZXIiPjxyZWN0IHg9IjIiIHk9IjIiIHdpZHRoPSIyMCIgaGVpZ2h0PSI4IiByeD0iMiIgcnk9IjIiPjwvcmVjdD48cmVjdCB4PSIyIiB5PSIxNCIgd2lkdGg9IjIwIiBoZWlnaHQ9IjgiIHJ4PSIyIiByeT0iMiI+PC9yZWN0PjxsaW5lIHgxPSI2IiB5MT0iNiIgeDI9IjYuMDEiIHkyPSI2Ij48L2xpbmU+PGxpbmUgeDE9IjYiIHkxPSIxOCIgeDI9IjYuMDEiIHkyPSIxOCI+PC9saW5lPjwvc3ZnPg==" />
  <!-- 箭头和文字 -->
  <path d="M280 320 L320 320" stroke="#64748B" stroke-width="2" marker-end="url(#arrowhead)" />
  <path d="M480 320 L520 320" stroke="#64748B" stroke-width="2" marker-end="url(#arrowhead)" />
  <path d="M520 380 L480 380" stroke="#64748B" stroke-width="2" marker-end="url(#arrowhead)" />
  <path d="M320 380 L280 380" stroke="#64748B" stroke-width="2" marker-end="url(#arrowhead)" />
  <defs>
    <marker id="arrowhead" markerWidth="10" markerHeight="7" refX="9" refY="3.5" orient="auto">
      <polygon points="0 0, 10 3.5, 0 7" fill="#64748B" />
    </marker>
  </defs>
  <text x="300" y="310" class="body-text" font-size="12" text-anchor="middle" fill="#64748B">请求</text>
  <text x="500" y="310" class="body-text" font-size="12" text-anchor="middle" fill="#64748B">请求</text>
  <text x="500" y="400" class="body-text" font-size="12" text-anchor="middle" fill="#64748B">响应</text>
  <text x="300" y="400" class="body-text" font-size="12" text-anchor="middle" fill="#64748B">响应</text>
  <!-- 比喻说明区域 -->
  <rect x="100" y="520" width="600" height="150" rx="10" ry="10" fill="white" stroke="#E2E8F0" stroke-width="1" filter="url(#drop-shadow)" />
  <text x="120" y="550" class="subtitle" font-size="18" fill="#334155">比喻说明</text>
  <text x="120" y="580" class="body-text" font-size="14" fill="#64748B">想象一下餐厅的场景：顾客（客户端）想要点餐，厨师（服务器）负责准备食物，</text>
  <text x="120" y="600" class="body-text" font-size="14" fill="#64748B">而服务员（API）在中间传递信息。顾客向服务员提出请求，服务员将请求传达给厨师，</text>
  <text x="120" y="620" class="body-text" font-size="14" fill="#64748B">厨师准备食物后，服务员将食物送回给顾客。这样，顾客不需要知道厨师是如何准备</text>
  <text x="120" y="640" class="body-text" font-size="14" fill="#64748B">食物的，只需要知道如何向服务员下单和接收食物即可。</text>

  <!-- 装饰元素 -->
  <circle cx="50" cy="50" r="30" fill="rgba(255, 255, 255, 0.05)" />
  <circle cx="750" cy="650" r="40" fill="rgba(255, 255, 255, 0.05)" />
  <circle cx="700" cy="100" r="20" fill="rgba(255, 255, 255, 0.05)" />
  <circle cx="100" cy="600" r="25" fill="rgba(255, 255, 255, 0.05)" />
  <!-- 底部署名 -->
  <text x="400" y="680" class="body-text" font-size="12" text-anchor="middle" fill="rgba(255, 255, 255, 0.5)">© 2025 API 解释图 </text>
</svg>

3. 第三版

<?xml version="1.0" encoding="UTF-8" standalone="no"?>
<svg width="800" height="700" xmlns="http://www.w3.org/2000/svg">
  <!-- 背景 -->
  <defs>
    <linearGradient id="bg-gradient" x1="0%" y1="0%" x2="100%" y2="100%">
      <stop offset="0%" style="stop-color:#1a202c;stop-opacity:0.9" />
      <stop offset="100%" style="stop-color:#2d3748;stop-opacity:0.9" />
    </linearGradient>
    <filter id="drop-shadow" x="-20%" y="-20%" width="140%" height="140%">
      <feGaussianBlur in="SourceAlpha" stdDeviation="5" />
      <feOffset dx="3" dy="3" result="offsetblur" />
      <feComponentTransfer>
        <feFuncA type="linear" slope="0.4" />
      </feComponentTransfer>
      <feMerge>
        <feMergeNode />
        <feMergeNode in="SourceGraphic" />
      </feMerge>
    </filter>
    <filter id="glass-effect">
      <feGaussianBlur in="SourceGraphic" stdDeviation="5" result="blur" />
      <feColorMatrix in="blur" type="matrix" values="1 0 0 0 0  0 1 0 0 0  0 0 1 0 0  0 0 0 18 -7" result="glow" />
      <feComposite in="SourceGraphic" in2="glow" operator="atop" />
    </filter>
    <style type="text/css">
      @import url('https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500&amp;display=swap');
      .title { font-family: 'Roboto', sans-serif; font-weight: 500; }
      .subtitle { font-family: 'Roboto', sans-serif; font-weight: 400; }
      .body-text { font-family: 'Roboto', sans-serif; font-weight: 300; }
    </style>
  </defs>
  <rect width="800" height="700" fill="url(#bg-gradient)" />
  <!-- 标题区域 -->
  <rect x="100" y="30" width="600" height="80" rx="15" ry="15" fill="#6366F1" filter="url(#glass-effect)" opacity="0.95" />
  <text x="400" y="70" class="title" font-size="28" text-anchor="middle" fill="white">什么是 API？</text>
  <text x="400" y="100" class="subtitle" font-size="16" text-anchor="middle" fill="white">Application Programming Interface（应用程序编程接口）</text>
  <!-- 定义区域 -->
  <rect x="100" y="130" width="600" height="100" rx="10" ry="10" fill="rgba(255, 255, 255, 0.15)" stroke="rgba(255, 255, 255, 0.3)" stroke-width="1" filter="url(#drop-shadow)" />
  <text x="120" y="160" class="subtitle" font-size="18" fill="#e2e8f0">定义</text>
  <text x="120" y="190" class="body-text" font-size="14" fill="#cbd5e0">API（应用程序编程接口）是一种机制，允许不同的软件程序或服务之间进行通信和数据</text>
  <text x="120" y="210" class="body-text" font-size="14" fill="#cbd5e0">交换。它就像是软件之间的"翻译官"或"服务员"，帮助它们相互理解和交流。</text>
  <!-- 图示区域 -->
  <rect x="150" y="250" width="500" height="250" rx="10" ry="10" fill="rgba(255, 255, 255, 0.1)" stroke="rgba(255, 255, 255, 0.2)" stroke-width="1" filter="url(#glass-effect)" />
  <!-- 客户端 -->
  <ellipse cx="200" cy="350" rx="80" ry="100" fill="rgba(254, 243, 199, 0.8)" stroke="#F59E0B" stroke-width="1.5" filter="url(#drop-shadow)" />
  <text x="200" y="320" class="subtitle" font-size="16" text-anchor="middle" fill="#92400E">客户端</text>
  <image x="170" y="330" width="60" height="60" href="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCIgZmlsbD0ibm9uZSIgc3Ryb2tlPSIjRjU5RTBCIiBzdHJva2Utd2lkdGg9IjIiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgc3Ryb2tlLWxpbmVqb2luPSJyb3VuZCIgY2xhc3M9ImZlYXRoZXIgZmVhdGhlci11c2VyIj48cGF0aCBkPSJNMjAgMjF2LTJhNCA0IDAgMCAwLTQtNEg4YTQgNCAwIDAgMC00IDR2MiI+PC9wYXRoPjxjaXJjbGUgY3g9IjEyIiBjeT0iNyIgcj0iNCI+PC9jaXJjbGU+PC9zdmc+" />
  <!-- API -->
  <ellipse cx="400" cy="350" rx="80" ry="100" fill="rgba(219, 234, 254, 0.9)" stroke="#3B82F6" stroke-width="1.5" filter="url(#drop-shadow)" />
  <text x="400" y="320" class="subtitle" font-size="16" text-anchor="middle" fill="#1E40AF">API</text>
  <image x="370" y="330" width="60" height="60" href="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCIgZmlsbD0ibm9uZSIgc3Ryb2tlPSIjM0I4MkY2IiBzdHJva2Utd2lkdGg9IjIiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgc3Ryb2tlLWxpbmVqb2luPSJyb3VuZCIgY2xhc3M9ImZlYXRoZXIgZmVhdGhlci1jb2RlIj48cG9seWxpbmUgcG9pbnRzPSIxNiAxOCAyMiAxMiAxNiA2Ij48L3BvbHlsaW5lPjxwb2x5bGluZSBwb2ludHM9IjggNiAyIDEyIDggMTgiPjwvcG9seWxpbmU+PC9zdmc+" />
  <!-- 服务器 -->
  <ellipse cx="600" cy="350" rx="80" ry="100" fill="rgba(209, 250, 229, 0.9)" stroke="#10B981" stroke-width="1.5" filter="url(#drop-shadow)" />
  <text x="600" y="320" class="subtitle" font-size="16" text-anchor="middle" fill="#065F46">服务器</text>
  <image x="570" y="330" width="60" height="60" href="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCIgZmlsbD0ibm9uZSIgc3Ryb2tlPSIjMTBCOTgxIiBzdHJva2Utd2lkdGg9IjIiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgc3Ryb2tlLWxpbmVqb2luPSJyb3VuZCIgY2xhc3M9ImZlYXRoZXIgZmVhdGhlci1zZXJ2ZXIiPjxyZWN0IHg9IjIiIHk9IjIiIHdpZHRoPSIyMCIgaGVpZ2h0PSI4IiByeD0iMiIgcnk9IjIiPjwvcmVjdD48cmVjdCB4PSIyIiB5PSIxNCIgd2lkdGg9IjIwIiBoZWlnaHQ9IjgiIHJ4PSIyIiByeT0iMiI+PC9yZWN0PjxsaW5lIHgxPSI2IiB5MT0iNiIgeDI9IjYuMDEiIHkyPSI2Ij48L2xpbmU+PGxpbmUgeDE9IjYiIHkxPSIxOCIgeDI9IjYuMDEiIHkyPSIxOCI+PC9saW5lPjwvc3ZnPg==" />
  <!-- 箭头和文字 -->
  <path d="M280 320 L320 320" stroke="#a0aec0" stroke-width="2.5" marker-end="url(#arrowhead)" />
  <path d="M480 320 L520 320" stroke="#a0aec0" stroke-width="2.5" marker-end="url(#arrowhead)" />
  <path d="M520 380 L480 380" stroke="#a0aec0" stroke-width="2.5" marker-end="url(#arrowhead)" />
  <path d="M320 380 L280 380" stroke="#a0aec0" stroke-width="2.5" marker-end="url(#arrowhead)" />
  <defs>
    <marker id="arrowhead" markerWidth="10" markerHeight="7" refX="9" refY="3.5" orient="auto">
      <polygon points="0 0, 10 3.5, 0 7" fill="#a0aec0" />
    </marker>
  </defs>
  <text x="300" y="310" class="body-text" font-size="12" text-anchor="middle" fill="#e2e8f0">请求</text>
  <text x="500" y="310" class="body-text" font-size="12" text-anchor="middle" fill="#e2e8f0">请求</text>
  <text x="500" y="400" class="body-text" font-size="12" text-anchor="middle" fill="#e2e8f0">响应</text>
  <text x="300" y="400" class="body-text" font-size="12" text-anchor="middle" fill="#e2e8f0">响应</text>
  <!-- 比喻说明区域 -->
  <rect x="100" y="520" width="600" height="150" rx="10" ry="10" fill="rgba(255, 255, 255, 0.12)" stroke="rgba(255, 255, 255, 0.25)" stroke-width="1" filter="url(#glass-effect)" />
  <text x="120" y="550" class="subtitle" font-size="18" fill="#e2e8f0">比喻说明</text>
  <text x="120" y="580" class="body-text" font-size="14" fill="#cbd5e0">想象一下餐厅的场景：顾客（客户端）想要点餐，厨师（服务器）负责准备食物，</text>
  <text x="120" y="600" class="body-text" font-size="14" fill="#cbd5e0">而服务员（API）在中间传递信息。顾客向服务员提出请求，服务员将请求传达给厨师，</text>
  <text x="120" y="620" class="body-text" font-size="14" fill="#cbd5e0">厨师准备食物后，服务员将食物送回给顾客。这样，顾客不需要知道厨师是如何准备</text>
  <text x="120" y="640" class="body-text" font-size="14" fill="#cbd5e0">食物的，只需要知道如何向服务员下单和接收食物即可。</text>
  <!-- 装饰元素 -->
  <circle cx="50" cy="50" r="30" fill="rgba(99, 102, 241, 0.15)" />
  <circle cx="750" cy="650" r="40" fill="rgba(16, 185, 129, 0.15)" />
  <circle cx="700" cy="100" r="20" fill="rgba(245, 158, 11, 0.15)" />
  <circle cx="100" cy="600" r="25" fill="rgba(59, 130, 246, 0.15)" />
  <circle cx="400" cy="500" r="5" fill="rgba(255, 255, 255, 0.2)" />
  <circle cx="420" cy="490" r="3" fill="rgba(255, 255, 255, 0.15)" />
  <circle cx="380" cy="510" r="4" fill="rgba(255, 255, 255, 0.1)" />
  <!-- 底部署名 -->
  <text x="400" y="680" class="body-text" font-size="12" text-anchor="middle" fill="rgba(255, 255, 255, 0.6)">© 2025 API 解释图 </text>
</svg>


最后一版在深色主题下效果才明显。综合来看，还是第二版好一点。


于是有了第四版：

4. 第四版：

<?xml version="1.0" encoding="UTF-8" standalone="no"?>
<svg width="800" height="700" xmlns="http://www.w3.org/2000/svg">
  <!-- 背景 -->
  <defs>
    <linearGradient id="bg-gradient" x1="0%" y1="0%" x2="100%" y2="100%">
      <stop offset="0%" style="stop-color:#1a202c;stop-opacity:1" />
      <stop offset="100%" style="stop-color:#2d3748;stop-opacity:1" />
    </linearGradient>
    <filter id="drop-shadow" x="-20%" y="-20%" width="140%" height="140%">
      <feGaussianBlur in="SourceAlpha" stdDeviation="5" />
      <feOffset dx="3" dy="3" result="offsetblur" />
      <feComponentTransfer>
        <feFuncA type="linear" slope="0.6" />
      </feComponentTransfer>
      <feMerge>
        <feMergeNode />
        <feMergeNode in="SourceGraphic" />
      </feMerge>
    </filter>
    <filter id="glass-effect">
      <feGaussianBlur in="SourceGraphic" stdDeviation="5" result="blur" />
      <feColorMatrix in="blur" type="matrix" values="1 0 0 0 0  0 1 0 0 0  0 0 1 0 0  0 0 0 19 -8" result="glow" />
      <feComposite in="SourceGraphic" in2="glow" operator="atop" />
    </filter>
    <filter id="contrast-boost">
      <feComponentTransfer>
        <feFuncR type="linear" slope="1.2" intercept="-0.1" />
        <feFuncG type="linear" slope="1.2" intercept="-0.1" />
        <feFuncB type="linear" slope="1.2" intercept="-0.1" />
      </feComponentTransfer>
    </filter>
    <style type="text/css">
      @import url('https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500&amp;display=swap');
      .title { font-family: 'Roboto', sans-serif; font-weight: 500; }
      .subtitle { font-family: 'Roboto', sans-serif; font-weight: 400; }
      .body-text { font-family: 'Roboto', sans-serif; font-weight: 300; }
    </style>
  </defs>
  <rect width="800" height="700" fill="url(#bg-gradient)" filter="url(#contrast-boost)" />
  <!-- 标题区域 -->
  <rect x="100" y="30" width="600" height="80" rx="15" ry="15" fill="#4F46E5" filter="url(#glass-effect)" opacity="1" />
  <text x="400" y="70" class="title" font-size="28" text-anchor="middle" fill="white">什么是 API？</text>
  <text x="400" y="100" class="subtitle" font-size="16" text-anchor="middle" fill="white">Application Programming Interface（应用程序编程接口）</text>
  <!-- 定义区域 -->
  <rect x="100" y="130" width="600" height="100" rx="10" ry="10" fill="rgba(255, 255, 255, 0.18)" stroke="rgba(255, 255, 255, 0.5)" stroke-width="1.5" filter="url(#drop-shadow)" />
  <text x="120" y="160" class="subtitle" font-size="18" fill="#f8fafc">定义</text>
  <text x="120" y="190" class="body-text" font-size="14" fill="#f1f5f9">API（应用程序编程接口）是一种机制，允许不同的软件程序或服务之间进行通信和数据</text>
  <text x="120" y="210" class="body-text" font-size="14" fill="#f1f5f9">交换。它就像是软件之间的"翻译官"或"服务员"，帮助它们相互理解和交流。</text>
  <!-- 图示区域 -->
  <rect x="150" y="250" width="500" height="250" rx="10" ry="10" fill="rgba(255, 255, 255, 0.15)" stroke="rgba(255, 255, 255, 0.4)" stroke-width="1.5" filter="url(#glass-effect)" />
  <!-- 客户端 -->
  <ellipse cx="200" cy="350" rx="80" ry="100" fill="rgba(254, 240, 138, 0.95)" stroke="#D97706" stroke-width="2" filter="url(#drop-shadow)" />
  <text x="200" y="320" class="subtitle" font-size="16" text-anchor="middle" fill="#78350F">客户端</text>
  <image x="170" y="330" width="60" height="60" href="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCIgZmlsbD0ibm9uZSIgc3Ryb2tlPSIjRDk3NzA2IiBzdHJva2Utd2lkdGg9IjIiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgc3Ryb2tlLWxpbmVqb2luPSJyb3VuZCIgY2xhc3M9ImZlYXRoZXIgZmVhdGhlci11c2VyIj48cGF0aCBkPSJNMjAgMjF2LTJhNCA0IDAgMCAwLTQtNEg4YTQgNCAwIDAgMC00IDR2MiI+PC9wYXRoPjxjaXJjbGUgY3g9IjEyIiBjeT0iNyIgcj0iNCI+PC9jaXJjbGU+PC9zdmc+" />
  <!-- API -->
  <ellipse cx="400" cy="350" rx="80" ry="100" fill="rgba(186, 230, 253, 0.95)" stroke="#0369A1" stroke-width="2" filter="url(#drop-shadow)" />
  <text x="400" y="320" class="subtitle" font-size="16" text-anchor="middle" fill="#0C4A6E">API</text>
  <image x="370" y="330" width="60" height="60" href="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCIgZmlsbD0ibm9uZSIgc3Ryb2tlPSIjMDM2OUExIiBzdHJva2Utd2lkdGg9IjIiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgc3Ryb2tlLWxpbmVqb2luPSJyb3VuZCIgY2xhc3M9ImZlYXRoZXIgZmVhdGhlci1jb2RlIj48cG9seWxpbmUgcG9pbnRzPSIxNiAxOCAyMiAxMiAxNiA2Ij48L3BvbHlsaW5lPjxwb2x5bGluZSBwb2ludHM9IjggNiAyIDEyIDggMTgiPjwvcG9seWxpbmU+PC9zdmc+" />
  <!-- 服务器 -->
  <ellipse cx="600" cy="350" rx="80" ry="100" fill="rgba(187, 247, 208, 0.95)" stroke="#047857" stroke-width="2" filter="url(#drop-shadow)" />
  <text x="600" y="320" class="subtitle" font-size="16" text-anchor="middle" fill="#064E3B">服务器</text>
  <image x="570" y="330" width="60" height="60" href="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCIgZmlsbD0ibm9uZSIgc3Ryb2tlPSIjMDQ3ODU3IiBzdHJva2Utd2lkdGg9IjIiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgc3Ryb2tlLWxpbmVqb2luPSJyb3VuZCIgY2xhc3M9ImZlYXRoZXIgZmVhdGhlci1zZXJ2ZXIiPjxyZWN0IHg9IjIiIHk9IjIiIHdpZHRoPSIyMCIgaGVpZ2h0PSI4IiByeD0iMiIgcnk9IjIiPjwvcmVjdD48cmVjdCB4PSIyIiB5PSIxNCIgd2lkdGg9IjIwIiBoZWlnaHQ9IjgiIHJ4PSIyIiByeT0iMiI+PC9yZWN0PjxsaW5lIHgxPSI2IiB5MT0iNiIgeDI9IjYuMDEiIHkyPSI2Ij48L2xpbmU+PGxpbmUgeDE9IjYiIHkxPSIxOCIgeDI9IjYuMDEiIHkyPSIxOCI+PC9saW5lPjwvc3ZnPg==" />
  <!-- 箭头和文字 -->
  <path d="M280 320 L320 320" stroke="#f1f5f9" stroke-width="3" marker-end="url(#arrowhead)" />
  <path d="M480 320 L520 320" stroke="#f1f5f9" stroke-width="3" marker-end="url(#arrowhead)" />
  <path d="M520 380 L480 380" stroke="#f1f5f9" stroke-width="3" marker-end="url(#arrowhead)" />
  <path d="M320 380 L280 380" stroke="#f1f5f9" stroke-width="3" marker-end="url(#arrowhead)" />
  <defs>
    <marker id="arrowhead" markerWidth="10" markerHeight="7" refX="9" refY="3.5" orient="auto">
      <polygon points="0 0, 10 3.5, 0 7" fill="#f1f5f9" />
    </marker>
  </defs>
  <text x="300" y="310" class="body-text" font-size="13" text-anchor="middle" fill="#f8fafc" font-weight="bold">请求</text>
  <text x="500" y="310" class="body-text" font-size="13" text-anchor="middle" fill="#f8fafc" font-weight="bold">请求</text>
  <text x="500" y="400" class="body-text" font-size="13" text-anchor="middle" fill="#f8fafc" font-weight="bold">响应</text>
  <text x="300" y="400" class="body-text" font-size="13" text-anchor="middle" fill="#f8fafc" font-weight="bold">响应</text>
  <!-- 比喻说明区域 -->
  <rect x="100" y="520" width="600" height="150" rx="10" ry="10" fill="rgba(255, 255, 255, 0.18)" stroke="rgba(255, 255, 255, 0.4)" stroke-width="1.5" filter="url(#glass-effect)" />
  <text x="120" y="550" class="subtitle" font-size="18" fill="#f8fafc">比喻说明</text>
  <text x="120" y="580" class="body-text" font-size="14" fill="#f1f5f9">想象一下餐厅的场景：顾客（客户端）想要点餐，厨师（服务器）负责准备食物，</text>
  <text x="120" y="600" class="body-text" font-size="14" fill="#f1f5f9">而服务员（API）在中间传递信息。顾客向服务员提出请求，服务员将请求传达给厨师，</text>
  <text x="120" y="620" class="body-text" font-size="14" fill="#f1f5f9">厨师准备食物后，服务员将食物送回给顾客。这样，顾客不需要知道厨师是如何准备</text>
  <text x="120" y="640" class="body-text" font-size="14" fill="#f1f5f9">食物的，只需要知道如何向服务员下单和接收食物即可。</text>
  <!-- 装饰元素 -->
  <circle cx="50" cy="50" r="30" fill="rgba(99, 102, 241, 0.3)" />
  <circle cx="750" cy="650" r="40" fill="rgba(16, 185, 129, 0.3)" />
  <circle cx="700" cy="100" r="20" fill="rgba(245, 158, 11, 0.3)" />
  <circle cx="100" cy="600" r="25" fill="rgba(59, 130, 246, 0.3)" />
  <circle cx="400" cy="500" r="5" fill="rgba(255, 255, 255, 0.35)" />
  <circle cx="420" cy="490" r="3" fill="rgba(255, 255, 255, 0.3)" />
  <circle cx="380" cy="510" r="4" fill="rgba(255, 255, 255, 0.25)" />
  <!-- 底部署名 -->
  <text x="400" y="680" class="body-text" font-size="12" text-anchor="middle" fill="rgba(255, 255, 255, 0.8)">© 2025 API 解释图 </text>
</svg>

---
## API 凭证类型


<?xml version="1.0" encoding="UTF-8" standalone="no"?>
<svg width="800" height="700" xmlns="http://www.w3.org/2000/svg">
  <!-- 背景 -->
  <defs>
    <linearGradient id="bg-gradient" x1="0%" y1="0%" x2="100%" y2="100%">
      <stop offset="0%" style="stop-color:#1a202c;stop-opacity:1" />
      <stop offset="100%" style="stop-color:#2d3748;stop-opacity:1" />
    </linearGradient>
    <filter id="drop-shadow" x="-20%" y="-20%" width="140%" height="140%">
      <feGaussianBlur in="SourceAlpha" stdDeviation="5" />
      <feOffset dx="3" dy="3" result="offsetblur" />
      <feComponentTransfer>
        <feFuncA type="linear" slope="0.6" />
      </feComponentTransfer>
      <feMerge>
        <feMergeNode />
        <feMergeNode in="SourceGraphic" />
      </feMerge>
    </filter>
    <filter id="glass-effect">
      <feGaussianBlur in="SourceGraphic" stdDeviation="5" result="blur" />
      <feColorMatrix in="blur" type="matrix" values="1 0 0 0 0  0 1 0 0 0  0 0 1 0 0  0 0 0 19 -8" result="glow" />
      <feComposite in="SourceGraphic" in2="glow" operator="atop" />
    </filter>
    <filter id="contrast-boost">
      <feComponentTransfer>
        <feFuncR type="linear" slope="1.2" intercept="-0.1" />
        <feFuncG type="linear" slope="1.2" intercept="-0.1" />
        <feFuncB type="linear" slope="1.2" intercept="-0.1" />
      </feComponentTransfer>
    </filter>
    <style type="text/css">
      @import url('https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500&amp;display=swap');
      .title { font-family: 'Roboto', sans-serif; font-weight: 500; }
      .subtitle { font-family: 'Roboto', sans-serif; font-weight: 400; }
      .body-text { font-family: 'Roboto', sans-serif; font-weight: 300; }
    </style>
  </defs>
  <rect width="800" height="700" fill="url(#bg-gradient)" filter="url(#contrast-boost)" />
  <!-- 标题区域 -->
  <rect x="100" y="30" width="600" height="80" rx="15" ry="15" fill="#4F46E5" filter="url(#glass-effect)" opacity="1" />
  <text x="400" y="70" class="title" font-size="28" text-anchor="middle" fill="white">API 凭证类型</text>
  <text x="400" y="100" class="subtitle" font-size="16" text-anchor="middle" fill="white">API Token、Secret Key、Access Token的区别与用途</text>
  <!-- API Token区域 -->
  <rect x="100" y="130" width="600" height="100" rx="10" ry="10" fill="rgba(255, 255, 255, 0.18)" stroke="rgba(255, 255, 255, 0.5)" stroke-width="1.5" filter="url(#drop-shadow)" />
  <text x="120" y="155" class="subtitle" font-size="18" fill="#f8fafc">API Token</text>
  <text x="120" y="180" class="body-text" font-size="14" fill="#f1f5f9">一种用于API身份验证的字符串标识符，可以视为"门票"，用于识别和授权API调用者。</text>
  <text x="120" y="205" class="body-text" font-size="14" fill="#f1f5f9">通常有一定的有效期，权限范围较广，适用于长期服务间通信。</text>
  <!-- Secret Key区域 -->
  <rect x="100" y="245" width="600" height="100" rx="10" ry="10" fill="rgba(255, 255, 255, 0.18)" stroke="rgba(255, 255, 255, 0.5)" stroke-width="1.5" filter="url(#drop-shadow)" />
  <text x="120" y="270" class="subtitle" font-size="18" fill="#f8fafc">Secret Key</text>
  <text x="120" y="295" class="body-text" font-size="14" fill="#f1f5f9">一个敏感的私密密钥，通常与API Key配对使用，用于对API请求进行加密签名。</text>
  <text x="120" y="320" class="body-text" font-size="14" fill="#f1f5f9">永远不应该公开或共享，可以视为"私人印章"，用于证明请求的真实性。</text>
  <!-- Access Token区域 -->
  <rect x="100" y="360" width="600" height="100" rx="10" ry="10" fill="rgba(255, 255, 255, 0.18)" stroke="rgba(255, 255, 255, 0.5)" stroke-width="1.5" filter="url(#drop-shadow)" />
  <text x="120" y="385" class="subtitle" font-size="18" fill="#f8fafc">Access Token</text>
  <text x="120" y="410" class="body-text" font-size="14" fill="#f1f5f9">一种临时凭证，通常通过认证流程（如OAuth）获得，用于代表用户访问特定资源。</text>
  <text x="120" y="435" class="body-text" font-size="14" fill="#f1f5f9">有严格的过期时间和范围限制，可刷新，可视为"临时通行证"。</text>
  <!-- 图示区域 -->
  <rect x="100" y="475" width="600" height="200" rx="10" ry="10" fill="rgba(255, 255, 255, 0.15)" stroke="rgba(255, 255, 255, 0.4)" stroke-width="1.5" filter="url(#glass-effect)" />
  <!-- 客户端 -->
  <rect x="120" y="525" width="100" height="100" rx="10" ry="10" fill="rgba(254, 240, 138, 0.95)" stroke="#D97706" stroke-width="2" filter="url(#drop-shadow)" />
  <text x="170" y="515" class="subtitle" font-size="14" text-anchor="middle" fill="#f8fafc">客户端</text>
  <!-- API服务器 -->
  <rect x="580" y="525" width="100" height="100" rx="10" ry="10" fill="rgba(187, 247, 208, 0.95)" stroke="#047857" stroke-width="2" filter="url(#drop-shadow)" />
  <text x="630" y="515" class="subtitle" font-size="14" text-anchor="middle" fill="#f8fafc">API服务器</text>
  <!-- 认证服务器 -->
  <rect x="350" y="525" width="100" height="100" rx="10" ry="10" fill="rgba(186, 230, 253, 0.95)" stroke="#0369A1" stroke-width="2" filter="url(#drop-shadow)" />
  <text x="400" y="515" class="subtitle" font-size="14" text-anchor="middle" fill="#f8fafc">认证服务器</text>
  <!-- 连接线和标签 -->
  <!-- API Token路径 -->
  <path d="M220 545 L580 545" stroke="#f1f5f9" stroke-width="2" stroke-dasharray="5,5" marker-end="url(#arrowhead)" />
  <rect x="320" y="530" width="150" height="22" rx="5" ry="5" fill="rgba(79, 70, 229, 0.8)" />
  <text x="395" y="546" class="body-text" font-size="12" text-anchor="middle" fill="white">API Token</text>
  <!-- Secret Key路径 -->
  <path d="M220 575 L580 575" stroke="#f1f5f9" stroke-width="2" marker-end="url(#arrowhead)" />
  <rect x="320" y="560" width="150" height="22" rx="5" ry="5" fill="rgba(236, 72, 153, 0.8)" />
  <text x="395" y="576" class="body-text" font-size="12" text-anchor="middle" fill="white">Secret Key签名请求</text>
  <!-- Access Token流程 -->
  <path d="M220 605 L350 605" stroke="#f1f5f9" stroke-width="2" marker-end="url(#arrowhead)" />
  <path d="M450 605 L580 605" stroke="#f1f5f9" stroke-width="2" marker-end="url(#arrowhead)" />
  <rect x="230" y="590" width="100" height="22" rx="5" ry="5" fill="rgba(245, 158, 11, 0.8)" />
  <text x="280" y="606" class="body-text" font-size="12" text-anchor="middle" fill="white">请求Token</text>
  <rect x="470" y="590" width="100" height="22" rx="5" ry="5" fill="rgba(16, 185, 129, 0.8)" />
  <text x="520" y="606" class="body-text" font-size="12" text-anchor="middle" fill="white">Access Token</text>
  <!-- 箭头定义 -->
  <defs>
    <marker id="arrowhead" markerWidth="10" markerHeight="7" refX="9" refY="3.5" orient="auto">
      <polygon points="0 0, 10 3.5, 0 7" fill="#f1f5f9" />
    </marker>
  </defs>
  <!-- 装饰元素 -->
  <circle cx="50" cy="50" r="30" fill="rgba(99, 102, 241, 0.3)" />
  <circle cx="750" cy="650" r="40" fill="rgba(16, 185, 129, 0.3)" />
  <circle cx="700" cy="100" r="20" fill="rgba(245, 158, 11, 0.3)" />
  <circle cx="100" cy="600" r="25" fill="rgba(59, 130, 246, 0.3)" />
  <circle cx="400" cy="460" r="5" fill="rgba(255, 255, 255, 0.35)" />
  <circle cx="420" cy="450" r="3" fill="rgba(255, 255, 255, 0.3)" />
  <circle cx="380" cy="470" r="4" fill="rgba(255, 255, 255, 0.25)" />
  <!-- 底部署名 -->
  <text x="400" y="680" class="body-text" font-size="12" text-anchor="middle" fill="rgba(255, 255, 255, 0.8)">© 2025 API认证与授权图解 </text>
</svg>