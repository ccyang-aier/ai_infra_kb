# 第一篇复审插图生成记录

使用内置 imagegen；项目 `assets/illustrations/hand-drawn-style-reference.png` 仅用作视觉风格参考。生成结果经人工核对对象位置、箭头方向与文字，并在正文说明它是逻辑关系图。

## 08-complete-request-overview.png

```text
Use case: scientific-educational. The attached image is a VISUAL STYLE reference only. Create a professional hand-drawn tutorial architecture diagram with white background, clean thin dark outlines, pale blue pods, pale gray node boundaries, black readable Chinese labels, simple flat colors, no decorative objects. Wide horizontal layout, highly legible, generously spaced. Show a whole Kubernetes knowledge website logical request relationship, not physical packet path. Draw a large boundary titled exactly 'Kubernetes 集群'. Outside on the far left is a small box '用户浏览器'. Inside the boundary, arrange FROM LEFT TO RIGHT: a dashed box '外部入口'; a dashed box '网站 Service'; a large NODE boundary '节点 A' containing a blue box '网站 Pod'; a dashed box 'knowledge Service'; a large NODE boundary '节点 B' containing exactly two separate blue boxes stacked '知识库 Pod 1' and '知识库 Pod 2'. Draw one right-pointing arrow between each successive box from browser to external entry to website Service to website Pod to knowledge Service. From knowledge Service draw TWO separate right-pointing arrow branches to Pod 1 and Pod 2, each terminating exactly at its destination box. Each arrow is an alternative logical request route, not data packet routing. Place all arrows cleanly without crossing labels, and all arrowheads touch corresponding object boundaries. No other boxes, no other labels, no return arrows, no decorative imagery; keep namespace/service independent of the node containers. Nodes A and B MUST be inside cluster; both knowledge pods MUST be inside node B; website Pod MUST be inside node A.
```
