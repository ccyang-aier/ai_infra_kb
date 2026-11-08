# 第一篇插图生成记录

本组插图使用内置 imagegen 生成。`03-pod-network.png` 复用经用户确认的风格参考图，其余六张均使用该参考图，并将下方公共提示词与各自的场景提示词拼接后生成。

## 公共提示词

```text
Use case: scientific-educational. Reference image is the definitive visual style, not the content layout. Match its clean, mature hand-drawn technical whiteboard style precisely: white background, thin charcoal sketch outlines, neat legible Chinese handwritten labels, pale gray node boxes, pale blue Pod boxes, restrained flat colors, generous whitespace, horizontal 2D composition. No watercolor, paper texture, shading, mascot, decoration or extra labels. Draw all exact text accurately.
```

## 01-nodes.png

```text
Create a two-node Kubernetes cluster diagram for beginners. A large outline labeled 'Kubernetes 集群' encloses two side-by-side light-gray node regions. Left node '节点 A' contains one pale-blue box '网站 Pod' with smaller text '网站应用'. Right node '节点 B' contains one pale-blue box '知识库 Pod' with smaller text '知识库应用'. Exactly two nodes, exactly one pod in each. No arrows, no network connections, no IP addresses.
```

## 02-pod-ip.png

```text
Create a two-node Kubernetes cluster communication diagram. Large outer boundary 'Kubernetes 集群'; two gray node regions labeled '节点 A' and '节点 B'. Left node contains a blue Pod labeled '网站 Pod' and exactly '10.1.0.2'. Right node contains a blue Pod labeled '知识库 Pod' and exactly '10.1.1.3'. One single arrow from website Pod to knowledge Pod labeled '查询请求'. Place each IP inside its own corresponding Pod. No other IPs or arrows.
```

## 03-pod-network.png

复用项目风格参考图 `assets/illustrations/hand-drawn-style-reference.png`。该图由内置 imagegen 以先前生成的水彩样稿为编辑目标，使用以下提示词生成：

```text
Edit the supplied Kubernetes educational diagram. Preserve its exact technical content, layout, hierarchy and all six Chinese labels: outer 'Kubernetes 集群', left '节点 A' with inner '网站 Pod', right '节点 B' with inner '知识库 Pod', one left-to-right arrow labelled '查询请求'. Change only the visual style: create a professional, clean hand-drawn technical whiteboard sketch for adult software engineers, like a carefully inked engineering notebook or Excalidraw diagram. Use a pure white background, thin consistent dark charcoal pen lines with only very subtle natural hand-drawn irregularity, neat handwritten Chinese and English with highly legible precise strokes, a restrained flat light-blue fill for Pod boxes and very light neutral gray node boundaries. Sharp edges and crisp text, generous whitespace, no shading or texture. No watercolor, wash, ink bleed, paper texture, brush calligraphy, childlike design, mascots, stickers, doodles or decoration. Maintain correct containment and exactly one clear arrow.
```

## 04-two-pods.png

```text
Create a simple application request diagram: left blue box labeled '网站 Pod', on right two separate equal blue boxes stacked vertically labeled '知识库 Pod 1' and '知识库 Pod 2'. One arrow from website to first target and a second arrow from website to second target, indicating possible destinations. No Service, no other boxes, no nodes, no other text. Arrows point right.
```

## 05-service.png

```text
Create a logical service routing diagram. Left blue rounded rectangle labeled '网站 Pod'; center a distinct dashed-outline rounded rectangle labelled 'knowledge 服务入口'; right two separate identical blue rounded rectangles stacked vertically labeled '知识库 Pod 1' and '知识库 Pod 2'. One arrow left-to-right from website Pod to service entrance, then two arrows from the service entrance, one to each backend Pod. Dashed outline is a logical endpoint rather than a physical machine. Exactly these four objects, exactly three arrows, no other text or physical icons.
```

## 06-response.png

```text
Create a logical Kubernetes request and response flow diagram. In one row: blue box '网站 Pod', dashed outline box 'knowledge 服务入口', blue box '知识库 Pod'. Along the upper half, show arrows left to right from website to service entrance to knowledge Pod with label '查询请求'. Along the lower half, show one return arrow directly right to left from knowledge Pod to website Pod, labeled '查询结果返回'. Exactly three objects, exactly two request arrows and one distinct return arrow. The dashed service outline is a logical access point, not a physical machine.
```

## 07-external.png

```text
Create a simple readable logical flow diagram about Kubernetes. On the left outside a large boundary labelled 'Kubernetes 集群' show a simple box labelled '用户浏览器'. Inside the cluster boundary lay out exactly four elements left-to-right: dashed outline box '外部入口', dashed outline box '网站服务', blue box '网站 Pod', dashed outline box 'knowledge 服务', then blue box '知识库 Pod'. Connect adjacent elements in this order with a single arrow pointing left to right. Exactly one browser outside and all five other elements inside the cluster. Clearly separate boxes with generous space, technically a logical relationship diagram, no physical appliance, no extra objects or text.
```

## 06-response-v2.png

使用内置 imagegen，以 `06-response.png` 为编辑目标，更新逻辑请求和响应方向：

```text
Edit the attached Kubernetes educational diagram, preserving its exact style, white background, handwritten Chinese, top title, left '网站 Pod' blue box, right '知识库 Pod' blue box, and middle dashed logical box 'knowledge 服务入口'. Update ONLY the arrows: depict the request and the response as two distinct logical directions BOTH connected via the central dashed box. Upper request: arrow from left pod to middle box and another from middle box to right pod, both point right; label above '查询请求'. Lower response: arrow from right pod to middle box and another from middle box to left pod, both point left; label below '查询结果'. Put the two directions at different vertical positions to avoid overlaps. Keep precisely three boxes, two Pod boxes and one dashed service logical entry. Ensure arrowheads unambiguously point in the directions specified. No direct arrow bypassing the middle box, no extra objects, no extra text. This is a logical service communication illustration, not a diagram of physical packet hops.
```

## 06-response-v3.png

使用内置 imagegen，以 `06-response-v2.png` 为编辑目标，对齐返回路径与服务入口的边缘：

```text
Edit the provided diagram; fix ONLY the return arrow alignment. Keep all labels, objects, styles, colors and overall layout unchanged. There are three boxes left-to-right: 网站 Pod, dashed knowledge 服务入口, 知识库 Pod. The dashed center box has a left vertical edge and a right vertical edge. Make both the request and response paths connect directly to those VERTICAL side edges, not to the bottom or rounded corners. Place the response line higher, clearly inside the top-to-bottom height of the dashed center box. On the right, the response arrow runs horizontally leftward from the right Pod box and its arrowhead touches the right vertical edge of the dashed center box halfway down. On the left, a second separate horizontal response arrow starts exactly at the left vertical edge of the center box at that same height and points left to the left Pod box. Both response segments must be horizontally aligned, and both segments meet the center box on its side edges. Keep the upper request arrows pointing right. No bypass line, no gaps. Move the response labels below the arrows so they do not cover the lines. This is a logical relationship diagram, not a claim that Service is a physical proxy.
```
