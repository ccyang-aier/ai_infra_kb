# 第 6 篇插图生成记录

使用内置 imagegen，`assets/illustrations/hand-drawn-style-reference.png` 作为视觉风格参考。以下为最终使用的各图提示词。

## service-state.png

```text
Use case scientific-educational, a professional clear hand-drawn engineering whiteboard figure, same visual style as attached reference only: pure white background, fine slightly hand-drawn dark ink, pale blue pods and pale gray system areas, clear legible Chinese labels, flat colors, no shading or texture. All lines touch intended endpoints, accurate direction. Wide horizontal composition. Draw a Kubernetes Service control-plane relationship diagram with clear white space and exactly six boxes. Arrange 'Service 配置' at top left, 'Pod 标签与状态' at bottom left, 'EndpointSlice 控制器' in the middle left, 'EndpointSlice' in the center, 'kube-proxy' at middle right, '节点转发规则' at far right. Draw arrows Service 配置 -> EndpointSlice 控制器, Pod 标签与状态 -> EndpointSlice 控制器, EndpointSlice 控制器 -> EndpointSlice, EndpointSlice -> kube-proxy, kube-proxy -> 节点转发规则, plus a clear separate arrow Service 配置 -> kube-proxy. Arrows are about configuration updates, not data packets. Exactly these six boxes and arrows, exact text, no extra icons, no IP addresses.
```

## service-return.png

```text
Use case scientific-educational, a professional clear hand-drawn engineering whiteboard figure, same visual style as attached reference only: pure white background, fine slightly hand-drawn dark ink, pale blue pods and pale gray system areas, clear legible Chinese labels, flat colors, no shading or texture. All lines touch intended endpoints, accurate direction. Wide horizontal composition. Draw a Kubernetes network topology showing the request and response for ONE connection. Two large node boundaries: left '节点 A', right '节点 B'. In node A draw two boxes side by side '客户端 Pod' and '节点转发与连接跟踪'; in node B draw one box '后端 Pod'. Across the boxes draw exactly TWO parallel paths: top path is request with arrows left to right connecting 客户端 Pod -> 节点转发与连接跟踪 -> 后端 Pod, labelled '请求'; bottom path is response with arrows right to left connecting 后端 Pod -> 节点转发与连接跟踪 -> 客户端 Pod, labelled '响应'. Put 'ClusterIP:80' next to the request segment before node processing and 'Pod IP:8080' next to the request segment after processing. No separate Service server and no DNS. Both arrows touch correct boxes. This is one simplified example with return via source node.
```

## dns-and-connection.png

```text
Use case scientific-educational, a professional clear hand-drawn engineering whiteboard figure, same visual style as attached reference only: pure white background, fine slightly hand-drawn dark ink, pale blue pods and pale gray system areas, clear legible Chinese labels, flat colors, no shading or texture. All lines touch intended endpoints, accurate direction. Wide horizontal composition. Draw an educational sequence diagram with three vertical lifelines labeled '客户端 Pod', '集群 DNS', and 'Service 转发规则' left to right; plus a fourth lifeline '后端 Pod' at far right. Four arrows in vertical time order: 1. client Pod -> DNS labeled '1. 查询 knowledge'; 2. DNS -> client Pod labeled '2. 返回 ClusterIP'; 3. client Pod -> Service rules labeled '3. 连接 ClusterIP:80'; 4. Service rules -> backend Pod labeled '4. 转发到 Pod:8080'. DNS arrows only between client and DNS; business connection only between client, rules and backend, never to DNS. Accurate arrows, exact labels, no other text or boxes.
```
