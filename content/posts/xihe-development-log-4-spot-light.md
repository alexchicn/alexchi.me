---
title: "羲和开发日志（四） 射灯"
#author: "Alex Chi"
date: 2020-11-07T12:19:41+08:00
draft: false
image: "/images/xihe-result-light-spot.webp"
toc: true
math: false
comment: true
categories: [ "羲和", "XiHe", "开发", "Development" ]
tags: [ "渲染", "Render", "光线追踪", "Ray Tracing", "灯光", "Light", "射灯", "Spot Light" ]
---

## 射灯

该类型的灯是在点光基础增加了光的散射方向和范围。

## 相关参数

* 颜色 - 光源颜色
* 强度 - 光源亮度
* 位置 - 光源位置
* 长度 - 光源的影响范围
* 半径 - 与点光半径相同
* 方向 - 射灯的朝向
* 内角和外角
    * 对于内角范围内的物体，光源强度不会衰减
    * 对于内角到外角范围内的物体，光源强度会线性衰减
    * 对于外角以外的物体，光源无法照射到

## 效果展示

### 半径与内外角

半径为0cm，外角60度，内角60度：

|羲和|Blender|
|-|-|
|![xihe-result-light-spot-r00b00](/images/xihe-result-light-spot-r00b00.webp)|![blender-result-light-spot-r00b00](/images/blender-result-light-spot-r00b00.webp)|

---------------

半径为0cm，外角60度，内角30度：

|羲和|Blender|
|-|-|
|![xihe-result-light-spot-r00b50](/images/xihe-result-light-spot-r00b50.webp)|![blender-result-light-spot-r00b50](/images/blender-result-light-spot-r00b50.webp)|

---------------

半径为10cm，外角60度，内角60度：

|羲和|Blender|
|-|-|
|![xihe-result-light-spot-r10b00](/images/xihe-result-light-spot-r10b00.webp)|![blender-result-light-spot-r10b00](/images/blender-result-light-spot-r10b00.webp)|

---------------

半径为10cm，外角60度，内角30度：

|羲和|Blender|
|-|-|
|![xihe-result-light-spot-r10b50](/images/xihe-result-light-spot-r10b50.webp)|![blender-result-light-spot-r10b50](/images/blender-result-light-spot-r10b50.webp)|

*相关场景模型取自[The Breakfast Room(License: CC-BY)](https://blendswap.com/blend/13363)*
