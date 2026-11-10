# 第 4 篇复审插图生成记录

两张图均使用内置 imagegen，以 `assets/illustrations/hand-drawn-style-reference.png` 为视觉风格参考。生成后检查了节点边界、箭头方向、组件连接与所有地址；图中的路径仅为正文限定条件下的去程示例。

## direct-routing-path.png

```text
Use case: scientific-educational. Match attached style reference only: professional hand-drawn whiteboard style, restrained thin charcoal lines, pale blue Pods, pale gray network components, clean white background, legible precise text, wide generous layout, no decorations, no watercolor. Create a detailed accurate network topology showing an example direct-routed request from a Pod on node A to a Pod on node B. Large left boundary labelled "节点 A", large right boundary labelled "节点 B". In node A place three distinct connected components left to right: blue rectangle "Pod A" with "10.244.1.2" in smaller text; gray rectangle "网关与路由" with "10.244.1.1"; gray rectangle "节点网卡" with "192.168.10.11". Outside and centered between node boundaries place one box "交换机". Inside node B place three distinct components left to right: gray rectangle "节点网卡" with "192.168.10.12"; gray rectangle "网关与路由" with "10.244.2.1"; blue rectangle "Pod B" with "10.244.2.3". Seven boxes total. Draw a single clear continuous chain of six rightward arrows exactly in that order, with each arrow touching its component, no bypasses, no return arrows. All 6 IPv4 addresses must be letter-perfect. No additional components, labels, arrows or lines. Layout must show NIC and gateway inside their own respective node boundaries, switch outside.
```

## vxlan-routing-path.png

```text
Use case: scientific-educational. Match attached image as style reference only: professional hand-drawn whiteboard diagram, restrained thin dark lines, pale blue Pods, pale gray network components, white background, exact legible text, generous whitespace. A detailed diagram of one-way VXLAN-encapsulated network traffic. Draw large boundary on the left labeled "节点 A" and large boundary on the right labeled "节点 B". Inside node A three separate horizontal boxes from left to right: "Pod A" with "10.244.1.2"; "VTEP A" with "封装"; "节点网卡" with "192.168.10.11". Outside both node boundaries between them one box labeled "底层网络". Inside node B three separate horizontal boxes from left to right: "节点网卡" with "192.168.10.12"; "VTEP B" with "解封装"; "Pod B" with "10.244.2.3". Connect these seven boxes in this exact order with six horizontal right-pointing arrows, each arrow touching its source and destination. All IPv4 addresses letter-perfect. No other arrows, no extra components, no dangling lines, do not overlap text or borders.
```
