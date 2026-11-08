# 第二篇插图生成记录

以下插图使用内置 imagegen 生成，以项目中的 `assets/illustrations/hand-drawn-style-reference.png` 为视觉风格参考。每张图的提示词由公共提示词与对应场景提示词拼接而成。

## 公共提示词

```text
Use case: scientific-educational. Use the attached reference as the definitive visual STYLE only. Match its mature hand-drawn technical whiteboard style: pure white background, clean slightly imperfect charcoal pen lines, neat accurate Chinese and digits, pale blue for endpoint boxes, pale gray network equipment, flat subtle color, ample whitespace, logical 2D layout, no textures, watercolor, shading, mascots or decorations. Render every label exactly as specified; no other text.
```

## 01-local-switch.png

```text
Horizontal diagram of one Ethernet LAN. Exactly two blue endpoint boxes, left labeled '节点 A' and '10.1.0.10', right labeled '节点 B' and '10.1.0.20'. Between them one gray device labeled '交换机'. Connect A to the switch, then switch to B, using clear simple physical-link lines; an arrow on each segment points left to right showing a frame from A to B. Above them show the shared subnet label '10.1.0.0/24'. Do not add IPs, devices, or endpoints.
```

## 02-cross-subnet.png

```text
Horizontal pedagogical network topology. Left light blue host '节点 A' with IP '10.1.0.10', right light blue host '节点 C' with IP '10.2.0.20', center gray router '路由器'. At the left router interface write '10.1.0.1'; at the right router interface write '10.2.0.1'. Group host A and the router left interface in subnet '10.1.0.0/24', group host C and the router right interface in subnet '10.2.0.0/24'. Use one clear left-to-right arrow over each segment. Exactly two endpoints and one router, no extra IPs.
```

## 03-vlan.png

```text
Educational VLAN isolation diagram. One single central gray physical switch box labeled '交换机'. Four pale blue host boxes: top-left '主机 A', top-right '主机 B', bottom-left '主机 C', bottom-right '主机 D'. Top two hosts each connect to a separate switch port labeled 'VLAN 10'; bottom two each connect to a separate switch port labeled 'VLAN 20'. Draw four separate lines terminating at the switch. Label above top pair 'VLAN 10', below bottom pair 'VLAN 20'. Do not draw a router, arrows between groups, or extra devices.
```

## 04-encapsulation.png

```text
A nesting diagram showing protocol encapsulation; exactly four progressively nested rectangles. Outer rectangle labeled '以太网帧', inside it one rectangle labeled 'IP 数据包', inside that one rectangle labeled 'TCP 报文段', inside that one rectangle labeled 'HTTP 请求'. Each label sits visibly near the top-left of its own boundary; every boundary is complete and unambiguous. No extra labels, no arrows, no endpoints. Make nested rectangles large and easy to read.
```

## 补充插图的公共提示词

以下三张图同样使用内置 imagegen，以项目风格参考图作为输入；实际提示词由本段公共提示词和各场景提示词拼接而成。

```text
Use case: scientific-educational. Generate a clear technical textbook illustration for Kubernetes networking beginners. Match the visual STYLE of the attached reference: white background, clean thin subtly hand-drawn charcoal outlines, legible simplified Chinese, pale blue endpoint boxes, pale gray switch/router, flat restrained colors, mature hand-drawn engineering whiteboard look, generous whitespace. No watercolor, no paper texture, no characters or decorations. Render all labels exactly and no other words. Every connector must touch the correct object.
```

## 05-nic-mac.png

```text
Horizontal physical Ethernet link topology with exactly two computers and one switch: large light blue boxes '节点 A' and '节点 B' left and right. Within node A a smaller white rounded rectangle labeled '网卡 A', and inside it smaller text 'MAC-A'. Within node B a smaller rectangle labeled '网卡 B', inside it 'MAC-B'. Between nodes a gray rounded rectangle '交换机'. A clear horizontal cable line runs directly from A's internal network adapter to the switch left port, then another cable line from switch right port directly to B's internal network adapter. Place '端口 1' immediately beside the switch left connection and '端口 2' immediately beside its right connection. Above node A write 'IP 10.1.0.10'; above node B write 'IP 10.1.0.20'. One small right-pointing arrow on each cable to show a frame traveling A to B. Every connector visibly touches its endpoint; precisely one network card in each computer, one switch; no other objects.
```

## 06-mac-per-hop.png

```text
Horizontal diagram of two Ethernet links across a router. Three boxes left-to-right labeled '节点 A', '路由器', '节点 C'. On the first link from A to router one arrow points right, labeled exactly 'MAC-A → MAC-R1'. On the second link from router to C one arrow points right, labeled exactly 'MAC-R2 → MAC-C'. Above both links display text exactly '源 IP：10.1.0.10    目标 IP：10.2.0.20'. Below links display exactly '第一段' and '第二段' respectively. Exactly three objects, exactly two arrows, each arrowhead touches its next-hop device; preserve correct left-to-right flow. Distinguish the two arrow labels clearly, do not draw a direct A-to-C link.
```

## 07-send-lookup.png

```text
A simple left-to-right flowchart showing the sequence for sending an IPv4 packet on Ethernet, no network topology. Three dashed-outline rectangles in one horizontal row, labels exactly '查询路由表', '查询邻居缓存', '发送以太网帧', connected by exactly two clear left-to-right arrows touching the rectangles. Under the first label, smaller text '确定下一跳'; under the second, '查找下一跳 MAC'; under the third, '交给网卡'. Do not add any other text. Three boxes separated, each with two legible lines.
```
