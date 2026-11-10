# 第 8 篇审校插图生成记录

使用内置 imagegen，输入图片 `assets/illustrations/hand-drawn-style-reference.png` 只作为风格参考。两张输出均由人工目视检查连接、文字和方向，正文另行限定逻辑关系与实际路径。

## 公共风格提示

```text
Use case: scientific-educational. Create a professional technical hand-drawn tutorial diagram, based on the attached image ONLY as visual style reference: white background, thin dark lines, pale blue Pods, pale gray infrastructure, simple clean typography and generous spacing; no texture, no shading, no cartoon. Every Chinese label must be correct, all arrows must clearly touch their endpoints.
```

## comparison.png

```text
A conceptual Kubernetes diagnostic illustration arranged as a clear horizontal topology. At left one blue box labelled '客户端 Pod'. At center top one gray box labelled '集群 DNS', below it one dashed box labelled 'Service'. At right two blue boxes stacked labelled '后端 Pod 1' and '后端 Pod 2'. Draw a pair of opposing arrows ONLY between client and DNS, label '查询名称' and '返回地址'. Draw a separate arrow client to Service and two branches from Service to each backend, representing alternative backend choices. Draw one additional clearly separate curved arrow from client to backend Pod 1 labelled '直接访问'. All arrows precisely meet their destination; do not make DNS sit in the business request path. Do not add labels or boxes beyond those specified.
```

## capture-points.png

```text
A wide educational diagram of observation points on a cross-node Pod-to-Pod request path. Two big separate node boundaries labeled '节点 A' and '节点 B'. Inside node A place a blue box '客户端 Pod' and a small gray box '节点接口 A', inside node B place a gray box '节点接口 B' and a blue box '后端 Pod'. Between nodes place a gray box '节点间网络'. Show exactly one directional path with arrows touching each object in this order: 客户端 Pod → 节点接口 A → 节点间网络 → 节点接口 B → 后端 Pod. Include small circular numbered markers 1 next to 客户端 Pod, 2 next to 节点接口 A, 3 next to 节点接口 B, 4 next to 后端 Pod. These are four capture locations, not additional hops. No IP addresses, no Service or DNS box, no tunnel drawn, no return path, no other text. The node boundaries must not intersect any interior boxes.
```
