# 第 3～9 篇插图生成记录

使用内置 imagegen，参考项目 `assets/illustrations/hand-drawn-style-reference.png` 的视觉风格；图片用于教学示意，最终内容与标注均按正文核对。以下每条主题提示与各组公共风格提示共同使用。

## 第一组公共风格提示

```text
Use case: scientific-educational. Use attached image as STYLE REFERENCE ONLY. Professional hand-drawn technical whiteboard diagram, white background, thin charcoal pen lines, pale blue endpoint boxes, pale gray infrastructure, clean exact Chinese lettering, flat colors, no decorations, no shadows, no texture. Horizontal layout, generous whitespace; connectors touch their objects; diagram technically accurate.
```

### 03-linux.png

```text
Two distinct network namespaces inside ONE Linux host. Draw one large boundary labelled 'Linux 节点'. Inside, two separate boxes side by side labelled '网络空间 A' and '网络空间 B'; in each put one small box 'eth0'. Below both show one box labelled 'Linux 网桥'. Connect each eth0 by one separate line to the bridge, label each link 'veth'. Exactly two namespaces, two eth0, one bridge, two links. Show topology only; no arrows; no IPs; no extra words.
```

### 04-sdn.png

```text
A VXLAN overlay diagram. Two separate large gray node boxes labeled '节点 A' and '节点 B'; each contains one blue box labeled 'Pod A' or 'Pod B'. Between the nodes draw exactly one connecting horizontal line labelled '节点之间的底层网络'. Above this line draw a separate dashed logical arc connecting the two node boxes, labelled 'VXLAN 隧道'. No other lines, no arrows, no IP addresses, no icons. The tunnel is logical and uses the underlay line; distinguish them clearly.
```

原图中底层网络连线位置不准确，使用原图作为编辑目标进行了修正：

```text
Edit this educational image for network accuracy. Preserve its exact professional hand-drawn whiteboard style, labels, dashed VXLAN tunnel and two node boxes containing Pod A and Pod B. The solid line labelled '节点之间的底层网络' MUST connect only the outer boundaries of 节点 A and 节点 B, never enter either node and never touch Pod A or Pod B. Move the solid line vertically to an empty horizontal level between the node labels and the Pod boxes, so its left endpoint touches the outer right border of 节点 A and its right endpoint touches the outer left border of 节点 B. Keep the Pods entirely enclosed inside their respective nodes. No other changes, no extra text.
```

### 05-cni.png

```text
A container networking setup sequence, four boxes left to right labeled exactly 'kubelet', '容器运行时', 'CNI 插件', and '配置 Pod 网络'. Connect adjacent boxes with clear right-pointing arrows. Label the first arrow 'CRI', second arrow 'CNI ADD'. The final box is the outcome, not another program. Exactly four boxes, no IPs, no Pod traffic arrow, no extra text.
```

### 06-service.png

```text
A Kubernetes Service logical routing diagram, client Pod left box '客户端 Pod', central dashed outline box 'Service', two right boxes stacked vertically '后端 Pod 1' and '后端 Pod 2'. One arrow from client to Service, two arrows from Service to the two pods, each arrow touching its target. Show both as possible destinations, no DNS box, no return arrows, no other text; a logical relationship diagram not a physical proxy.
```

### 07-ingress.png

```text
A logical Kubernetes ingress path. Outer cluster boundary 'Kubernetes 集群'. Outside on left '客户端', inside from left to right '入口控制器', 'Service', '后端 Pod'. Connect each adjacent object with one arrow pointing right, ensure boundaries and arrowheads touch their objects. Label Service as a dashed logical box, Pod pale blue. Include no other nodes or captions. It is a logical flow, not a claim every packet goes through Service IP.
```

### 08-debug.png

```text
A horizontal four-step troubleshooting flowchart with four equal boxes left to right labelled exactly '检查后端 Pod', '检查 Service', '检查 DNS', '检查外部入口'. Join each neighbouring box with a right-pointing arrow, arrowheads touch boxes. No extra labels or icons. It is a checklist of stages, not packet flow.
```

### 09-ai.png

```text
Two AI server node boundaries labeled '节点 A' and '节点 B'. Each contains one box 'GPU' and one box '网卡'. Outside nodes between them show a box '交换机'. Connect each network card to the switch with separate lines, no arrows. Do NOT draw a direct line between GPU and NIC, and do not imply RDMA or GPUDirect is active. No extra labels, no cables crossing.
```

## 第二组公共风格提示

```text
Use case: scientific-educational. The attached image is a visual style reference. Match its mature hand-drawn whiteboard style: white background, thin slightly hand-drawn dark lines, pale blue application blocks, pale gray system blocks, accurate legible Chinese text, no shading, no decorations, generous whitespace. All arrows must connect to correct endpoints, all labels exact.
```

### 03-localhost.png

```text
Draw one Pod boundary labelled '同一个 Pod'. Inside one network namespace boundary labelled '共享网络空间'. Inside that boundary draw two blue boxes side by side '容器 A' and '容器 B'. Show one arrow from container A to container B labelled 'localhost:8080'. Exactly one Pod, one shared network namespace, two containers, one arrow. No other labels, no IP addresses, no nodes.
```

### 04-headers.png

```text
A nested packet diagram with four nested rectangular boundaries. The outermost labeled '外层 IP' contains next boundary 'UDP + VXLAN', which contains '内层以太网帧', which contains '内层 IP 包'. Use no addresses, no arrows, no devices. Correct strict nesting, each label fully visible, sufficient padding.
```

### 06-dns-steps.png

```text
Three consecutive logical stages in three equally sized boxes from left to right, connected by arrows, exact labels: '1. 查询服务名', '2. 得到服务 IP', '3. 连接服务'. These are ordered steps, not packets or a topology. No other text or icons.
```

### 07-policy.png

```text
A logical network policy example with three Pod boxes: upper left '前端 Pod', lower left '测试 Pod', right '知识库 Pod'. Exactly two rightward arrows each connecting one left Pod to the knowledge Pod. Label the upper arrow '允许' and the lower arrow '阻止', and put a clear X on the lower arrow. Do not add a policy device in the path. No IP, no other boxes or labels.
```

### 09-multinet.png

```text
Draw one Pod large boundary labelled '训练 Pod'. Inside draw two interface blocks 'eth0' and 'net1'. Outside on the right draw two distinct network boxes '集群默认网络' on top and '附加数据网络' below. Connect eth0 only to 集群默认网络 and net1 only to 附加数据网络, with clean separate lines touching boundary and no arrowheads. No GPU, no NIC, no RDMA claims, no extra labels.
```

## 第三组公共风格提示

```text
Use case: scientific-educational. Use attached image only as style reference. Clean professional hand-drawn engineering whiteboard diagram: white background, fine dark strokes, pale blue application blocks and pale grey network infrastructure, no shading or texture, legible accurate labels. Connections must touch their boxes and be technically precise.
```

### 03-veth-pairs.png

```text
Draw a wide educational topology: one large boundary labelled 'Linux 节点'. Inside, at left a smaller boundary labelled '网络空间 A' contains one box labelled 'eth0'; at right another boundary labelled '网络空间 B' contains one box labelled 'eth0'. Outside those two boundaries but inside the Linux node, below them, show two small boxes labelled 'kb-a1' and 'kb-b1', and one centered box labelled '网桥 kb-br'. One line from the left eth0 to kb-a1, one from kb-a1 to the bridge; one line from right eth0 to kb-b1, one from kb-b1 to the bridge. Labels 'veth 对 A' and 'veth 对 B' by their own respective eth0-to-kb links. No arrows, no additional devices. The two eth0 interfaces belong to distinct namespaces.
```

### 08-tcp-handshake.png

```text
Draw a simple technically correct TCP handshake sequence diagram. Two vertical lifelines, left labelled '客户端', right labelled '服务端'. Between them show exactly three horizontal arrows in descending order: top arrow goes left to right labelled '1. SYN'; middle arrow goes right to left labelled '2. SYN + ACK'; bottom arrow goes left to right labelled '3. ACK'. All arrowheads precisely touch the destination lifeline. Whiteboard diagram, no network devices, no extra arrows or text.
```
