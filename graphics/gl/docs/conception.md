# WEBGL 的基本概念

## 基本元素的渲染

### 点

### 线

### 三角形

三角形由三个坐标组成, 坐标如下：

```text
V1
|  .
|   .
|    .
|     .
|      .
|       .
|        .
|         .
V2---------V3
```

绘制三角形的渲染顺序则以`逆时针`来完成，即 V1 -> V2 -> V3 ，对应代码中的坐标顺序为 [V1, V2, V3]

### 矩形

由于一个矩形可以由两个共线的三角形组成，坐标如下：

```text
V0-------------V3
|               |
|               |
|               |
|               |
|               |
|               |
V1-------------V2
```

通过每三个坐标来绘制一个三角形，由上面已知绘制需要由两个三角形组成，则以`逆时针`来规定渲染顺序,
构成矩形的三角形如下：

- 坐标顺序为 V0 -> V1 -> V2
- 坐标顺序为 V0 -> V2 -> V3

因此，代码中的坐标顺序需要遵循 [V0, V1, V2, V3] 来编写

但由于在三维的世界中存在正面和背面的区分，而背面的顺序则`与正面相反`。