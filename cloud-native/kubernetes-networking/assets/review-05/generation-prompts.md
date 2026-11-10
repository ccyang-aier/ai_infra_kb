# 第 5 篇审校插图提示词

使用内置 imagegen；参考图为 `assets/illustrations/hand-drawn-style-reference.png`，只用于统一风格。每张图使用公共提示词加对应主题提示词。

## 公共提示词

```text
Use case: scientific-educational. Use the attached image as STYLE REFERENCE ONLY. Clean professional hand-drawn engineering whiteboard diagram, pure white background, fine consistent dark strokes, pale blue Pod boxes, gray node infrastructure, clear Chinese text, generous whitespace, no shadows, no cartoon or watercolor. Diagram must be technically accurate, readable and show full layout.
```

## pod-cross-node-path.png

```text
Draw a wide detailed Kubernetes Pod cross-node communication topology. Two separate large boundaries labeled exactly '节点 A' on the left and '节点 B' on the right. Inside node A from top down place a box labelled 'Pod A' containing label 'eth0  10.244.1.2', a box below labelled '节点 A 网络', and a small box below labelled '物理网卡 A'. Inside node B from bottom up place a small box '物理网卡 B', a box '节点 B 网络', then a box 'Pod B' containing 'eth0  10.244.2.3'. Below both node boundaries, outside them, place one box centered labelled '节点间网络'. Connect Pod A down to 节点 A 网络 with a line labeled 'veth', then to 物理网卡 A, then to 节点间网络, then to 物理网卡 B, then to 节点 B 网络, then to Pod B with line labeled 'veth'. Draw exactly ONE continuous request path with rightward/down/up arrows touching every object in order. No additional objects, no Service, no kubelet, no return path. The packet crosses physical NICs. All labels must be accurate.
```

## cni-setup.png

```text
Draw an educational CNI setup diagram, no traffic path. On the left three process boxes vertically: 'kubelet', '容器运行时', 'CNI 插件'. Right side show a large outlined area labelled 'Pod 网络空间', inside it a blue box labeled 'eth0' and below it label 'Pod IP'. Outside that area on far right place a box labelled '节点侧接口'. Place one arrow from kubelet down to 容器运行时 labeled 'CRI', then one arrow from 容器运行时 down to CNI 插件 labeled 'CNI ADD'. From CNI 插件 a single arrow goes to Pod 网络空间 labeled '配置接口和地址'. Connect eth0 to 节点侧接口 with a line labeled 'veth 对'; they are two ends of one veth. Do not draw packet traffic. No IP literals or extra text.
```
