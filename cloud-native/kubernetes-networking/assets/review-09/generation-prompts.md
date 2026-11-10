# 第 9 篇审校插图提示词

使用内置 imagegen，以项目风格参考图 `assets/illustrations/hand-drawn-style-reference.png` 为视觉参考。以下公共风格提示分别与各张主题提示组合。

```text
Use case: scientific-educational. Reference image is style reference ONLY. Professional technical hand-drawn diagram, pure white background, clean thin dark lines, pale blue and pale gray flat fills, generously spaced, labels correctly spelled, no texture, no shadows, no decoration, clear containment and connectors.
```

## two-networks.png

```text
Draw a wide educational architecture diagram for distributed Kubernetes training. Two large separate node boundaries, left "节点 A" and right "节点 B". Inside each node is one blue Pod boundary named respectively "训练 Pod A" and "训练 Pod B". Inside Pod A there are two distinct interface boxes stacked vertically: top "eth0  10.244.1.2", bottom "net1  172.20.1.2". Inside Pod B there are two interface boxes stacked vertically: top "eth0  10.244.2.3", bottom "net1  172.20.1.3". In the center between nodes put two gray boxes stacked vertically: top "集群默认网络", bottom "附加数据网络". Draw four separate simple horizontal connections, no arrowheads: the two eth0 boxes connect ONLY to the central top network box; the two net1 boxes connect ONLY to the central bottom network box. Lines run through node boundaries and touch correct interface boxes; no diagonal crossings, no GPU or NIC icon, no extra labels, no arrows. Image is a logical connectivity diagram only.
```

## allreduce.png

```text
Draw a clear two-stage educational diagram, one stage above the other. Upper stage title "同步前", with left blue box "进程 A：梯度 8" and right blue box "进程 B：梯度 12". Lower stage title "求和 AllReduce 后", with left blue box "进程 A：结果 20" and right blue box "进程 B：结果 20". Within each stage place the two boxes on the same row. Between the two stages a single downward arrow labelled "交换并求和" indicates the stage transition; do NOT depict a central server, GPU interconnect, switch or physical network path. Exact labels only.
```

## pcie-topology.png

```text
Use case: scientific-educational. Reference image is style reference ONLY. Professional technical hand-drawn diagram, pure white background, thin dark lines, pale blue and pale gray flat fills, generous space, exact legible labels, no shading, no texture, no decoration. Draw one large boundary labelled '训练节点'. Inside it put four distinct rectangular components: 'CPU' at top center, 'PCIe 交换芯片' below CPU, 'GPU' at bottom left, and '网卡' at bottom right. Outside this boundary at far right put one separate box '网络交换机'. Draw exactly four undirected lines: CPU to PCIe 交换芯片, PCIe 交换芯片 to GPU, PCIe 交换芯片 to 网卡, and 网卡 to 网络交换机. Each line touches the correct labeled component, no arrowheads, no crossing lines. Do not add any additional labels or components. This is an example hardware topology, NOT a direct data path or a GPUDirect claim.
```
