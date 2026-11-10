# 第三篇插图提示词

使用内置 imagegen，风格参考：`assets/illustrations/hand-drawn-style-reference.png`。图片已核查后存入本目录。

通用提示：

```text
Use case scientific-educational. Input image is only a visual style reference. Professional precise hand drawn technical whiteboard diagram, white background, thin dark clean pen lines, pale blue endpoints, pale grey infrastructure, readable text. Avoid shading, watercolour, visual clutter. Carefully preserve the exact topology, all labels, all arrow directions.
```

`host-gateway.png` 主题提示：

```text
Create a detailed educational networking topology with a large outer boundary labelled 'Linux 节点'. Inside it, on the left, a small boundary labelled '网络空间 A' containing a small box 'eth0' with caption '10.200.0.1/24'. In the host network area draw in order from left to right boxes 'kb-a1', '网桥 kb-br' with caption '10.200.0.254', 'IP 转发', and '物理接口' with caption '192.0.2.10'. All four are inside the Linux node, and outside network space A. Outside the Linux node to the right draw a box '外部网络'. Draw one arrow from A eth0 to kb-a1, another from kb-a1 to 网桥 kb-br, another from 网桥 kb-br to IP 转发, another from IP 转发 to 物理接口, and the last from 物理接口 to 外部网络. Arrows show only outward request direction. Exactly one chain, every arrowhead touches its destination, no shortcuts, no other objects, no return arrows. Host and namespace boundaries must be visually unambiguous.
```

`neighbor-and-fdb.png` 主题提示：

```text
Draw a technically accurate educational illustration with two side-by-side parts. Left panel boundary labelled '网络空间 A' contains a heading '邻居表' and exactly one table row '10.200.0.2 → MAC-B' and below it a small box 'eth0'. Right panel boundary labelled '宿主机网络空间' contains a heading '网桥转发表' and exactly one table row 'MAC-B → kb-b1' and below it a small box '网桥 kb-br'. A thin line represents connection between the eth0 and bridge only as topology. No arrows from tables, no IPs except 10.200.0.2, no extra text. Clear distinguish the namespace each table belongs to.
```

为避免简略拓扑误导，将初图作为编辑目标，只保留两张表：

```text
Edit this exact image. Keep its two panels and two tables exactly as they are, including Chinese labels and entries. REMOVE ONLY the bottom two boxes labelled 'eth0' and '网桥 kb-br' and the connecting line between them. Leave clean white/gray empty space instead. No other changes, no additional symbols or words.
```
