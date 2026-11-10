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

## 补充主机通信与多网卡插图

以下两张图使用内置 imagegen，以项目风格参考图作为输入；提示词由公共部分与各场景部分拼接而成。

```text
Use case: scientific-educational. Style reference is attached. Match its hand-drawn engineering whiteboard style for mature adult readers: pure white background, charcoal thin line work with slight hand-drawn character, pale blue app and interface blocks, pale gray hardware, legible simplified Chinese, ample whitespace. No textures, no watercolor, no decoration. All objects and text must be accurate, with clean connections and unambiguous arrowheads.
```

### 08-host-flow.png

```text
Draw a request path between two computers through a switch. Put two large side-by-side node boundaries labeled '节点 A' and '节点 B', and a switch labeled '交换机' in the whitespace between them. INSIDE each node show three vertically stacked clearly separated boxes: at top '应用 A' or '应用 B'; center '操作系统' with '网络接口 eth0' written INSIDE the OS area; bottom '网卡 A' or '网卡 B' as hardware outside and below the OS area but still INSIDE its node. Draw the forward request as separate arrows: on A, 应用 A down to 操作系统, then 操作系统 down to 网卡 A; 网卡 A across to 交换机, then 交换机 across to 网卡 B; on B, 网卡 B up to 操作系统, then 操作系统 up to 应用 B. Every arrowhead must touch its intended box boundary, all directions unambiguous. No reverse arrows, no IPs or MAC labels, no extra boxes or text. Do not conflate the software interface and hardware NIC.
```

### 09-multinic.png

```text
Draw a clear simple illustration of ONE computer with TWO separately connected physical network cards. Show a large outer container labeled '节点 A'. Inside, show a software area labeled '操作系统', containing two separate interface boxes: '接口 eth0' with 'IP 10.1.0.10' and '接口 eth1' with 'IP 192.168.1.10'. Below the software area, still inside node A, show two separate hardware boxes '网卡 1' and '网卡 2'. Connect eth0 only to 网卡 1 and eth1 only to 网卡 2 using clear separate lines. Outside the node at bottom show separate destinations '网络 1' connected to 网卡 1, and '网络 2' connected to 网卡 2. All labels exactly as given. IP address digits must be accurate. Interfaces are inside OS and NICs outside OS; no extra text, no duplicate lines, no crossed connections.
```

## 10-same-network.png

使用内置 imagegen，以项目风格参考图作为输入：

```text
Use case: scientific-educational. Make a clean professional hand-drawn technical whiteboard diagram, matching the attached reference's visual style: pure white, thin slightly hand-drawn dark lines, pale blue interface boxes, pale gray hardware, precise readable Chinese and numbers, no shading, no watercolor, no decorative objects. Diagram shows ONE computer with two independent network cards connected by two separate physical cables to ONE switch in the SAME local subnet. Put large outer boundary labelled '节点 A'. Inside it, an operating system area labelled '操作系统' contains two separated pale blue interfaces labelled exactly 'eth0  10.1.0.10/24' and 'eth1  10.1.0.11/24'. Below, still inside node A and outside the operating system area, show two gray hardware boxes '网卡 1' and '网卡 2'. Connect eth0 only to 网卡 1; connect eth1 only to 网卡 2. Draw two separate cables from 网卡 1 and 网卡 2 to distinct sides of ONE external gray box labelled '交换机'. Label the shared network clearly '同一网络 10.1.0.0/24'. This image shows physical connections and interface-to-card mappings, not packet direction: use plain lines with NO ARROWHEADS. Clear connections, no crossing lines, exact IP numbers, nothing else.
```

## 11-direct-link.png

使用内置 imagegen，以项目风格参考图作为输入：

```text
Use case: scientific-educational. Match the attached reference's mature professional hand-drawn technical whiteboard style: white background, thin subtly hand-drawn charcoal lines, pale blue blocks, precise legible Chinese labels and numbers, flat color, no decoration or textures. Illustrate exactly two computers connected DIRECTLY by one Ethernet cable, with no switch or router. Left container labeled '节点 A', containing one smaller box '网卡 A'; right container '节点 B', containing box '网卡 B'. Above left node label '10.1.0.10/24'; above right node label '10.1.0.20/24'. Draw exactly one continuous line connecting 网卡 A and 网卡 B, passing through the node boundaries, labeled '网线'. There are no arrowheads because it represents a physical cable. No other boxes, IPs, labels or hardware. Make sure the cable touches each network card clearly.
```

## 12-direct-host-flow.png

使用内置 imagegen，以 `08-host-flow.png` 为编辑目标：

```text
Edit this diagram showing the journey of a request. Preserve exact visual style, white background, two node frames labeled '节点 A' and '节点 B', all the app, operating system, network interface eth0, and network card boxes and their positions. Make exactly one change: REMOVE the middle switch completely, including its rectangle and label, and replace it with one continuous horizontal cable/arrow connecting the right edge of the 网卡 A box directly to the left edge of the 网卡 B box. A single clear arrowhead points right and touches 网卡 B. Keep node A internal arrows downward and node B internal arrows upward, ensure their tips touch the intended boxes. Two nodes are directly connected without switch, gateway, or other device. Do not add text, objects, logos, or decorative marks.
```
