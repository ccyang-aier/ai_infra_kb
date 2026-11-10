# 第二篇审校新增插图提示词

使用内置 imagegen；输入图片仅作为风格参考：`assets/illustrations/hand-drawn-style-reference.png`。

## 公共风格提示

```text
Use case: scientific-educational. Use the attached image ONLY as visual style reference. Draw a professionally art-directed hand-drawn technical teaching diagram with white background, fine consistent dark strokes, pale blue host boxes, pale grey switches, clear precise labels, generous whitespace, no texture, no shadows, no cartoons, no decoration. Make it detailed and technically accurate, with no extraneous objects.
```

## 13-arp-request-reply.png

```text
Create one diagram consisting of TWO stacked independent horizontal strips, each showing exactly three distinct boxes in left-to-right order: '节点 A', '交换机', '节点 B'. In top strip use two horizontal rightward arrows A to switch and switch to B. Put top heading '1. ARP 请求（广播）' and caption above arrow '谁是 10.1.0.20？'. In bottom strip use two horizontal leftward arrows B to switch and switch to A. Put bottom heading '2. ARP 回复（单播）' and caption above arrow '10.1.0.20 对应 MAC-B'. Both strips display the SAME A switch B topology; precise arrow directions and connection endpoints are essential. No other labels.
```

## 14-routed-through-switches.png

```text
Draw a detailed left-to-right network topology. Five separate boxes in order: blue '节点 A', grey '交换机 1', grey '路由器', grey '交换机 2', blue '节点 C'. Draw exactly four connected rightward arrow segments from A through switch 1 and router and switch 2 to C. Under Node A write '10.1.0.10'; under Node C write '10.2.0.20'. Above the first link region A to router write '第一段：MAC-A → MAC-R1'; above the second region router to C write '第二段：MAC-R2 → MAC-C'. At the top a separate wide note clearly labeled 'IP：10.1.0.10 → 10.2.0.20'. No arrows connect to the note. Avoid changing any of these labels or omitting switches. Do not depict a return path.
```
