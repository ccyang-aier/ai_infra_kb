# 第 7 篇插图生成记录

使用内置 imagegen，项目风格参考图为 `assets/illustrations/hand-drawn-style-reference.png`。公共提示词：

```text
Use case: scientific-educational. The attached image is STYLE reference only. Match exact professional hand-drawn technical whiteboard style: thin black fine hand-drawn lines, pure white background, pale blue endpoints, pale gray infrastructure, neat accurate Chinese labels, no textures, no decorative elements. Use ample padding. Horizontal tutorial diagram, all line segments touch their objects and all arrowheads point to correct destination.
```

## ingress-connections.png

```text
Draw a concrete ingress implementation example, showing two independently terminated TCP connections. Place four boxes left to right: '浏览器', '外部负载均衡器', '入口代理', '后端 Pod'. The first two boxes are OUTSIDE a large boundary labelled 'Kubernetes 集群'; the last two are INSIDE the cluster boundary. Draw a single rightward arrow from 浏览器 to 外部负载均衡器 and then to 入口代理, with above both arrows one caption '客户端连接：HTTPS'. Draw a second rightward arrow from 入口代理 to 后端 Pod, labelled '上游连接：HTTP'. The HTTP route is one selected example only, not universal. Both arrowheads clearly touch the next box. No response arrows, no extra components, no service box, no DNS server, no additional lines or text. Labels in clear Chinese.
```

## snat-roundtrip.png

```text
Draw a step-by-step SNAT address translation infographic. Four horizontal rows each starting with a numbered caption. Row 1 label '1 请求：Pod 发出' followed by '10.244.1.2:53000 → 203.0.113.20:443'. Row 2 label '2 请求：源地址转换后' followed by '192.0.2.10:45000 → 203.0.113.20:443'. Row 3 label '3 响应：外部服务发出' followed by '203.0.113.20:443 → 192.0.2.10:45000'. Row 4 label '4 响应：反向转换后' followed by '203.0.113.20:443 → 10.244.1.2:53000'. Exactly these four numbered lines, use monospaced digits, each arrow correctly left-to-right between IP:port pairs. No additional devices, arrows or labels.
```
