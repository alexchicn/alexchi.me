---
title: "羲和开发日志（二） 平行光"
#author: "Alex Chi"
date: 2020-11-03T10:12:39+08:00
draft: false
image: "/images/xihe-result-light-direction.jpg"
math: true
toc: true
comment: true
categories: [ "羲和", "XiHe", "开发", "Development" ]
tags: [ "渲染", "Render", "光线追踪", "Ray Tracing", "灯光", "Light", "平行光", "Directional Light" ]
---

## 平行光

光都是由光源体发射出来的，光源体形状和物体形状决定了物体影子。

平行光是为了模拟远距离巨型光源体而构建的概念，这样可以减少对光源体的碰撞运算。
现实中太阳对于地球来讲就是这么一个光源体，远而且巨大。

## 相关参数

* 颜色 - 光源颜色
* 强度 - 光源亮度
* 位置 - 该参数与平行光无关，但是为便于场景编辑，都会保留此参数
* 长度 - 光源的影响范围
* 方向 - 决定了模型的哪些面（依赖法线）可以被照亮
* 散射角
    * 即一个物体可以从什么角度范围受到光源体的照射
    * 简单来讲散射角度越大，物体可能受到的光照就越多
    * 下面有展示

## 效果展示

颜色、强度和方向是常识，这里就不进行展示。

### 散射角

> **从百叶窗在墙上的阴影形态可以看出光源的大小。**

散射角度为0，如下图：

![xihe-result-light-direction-angle0](/images/xihe-result-light-direction-angle0.jpg)

散射角度为2，如下图：

![xihe-result-light-direction-angle2](/images/xihe-result-light-direction-angle2.jpg)

散射角度为17，如下图：

![xihe-result-light-direction-angle17](/images/xihe-result-light-direction-angle17.jpg)

散射角度为57，如下图：

![xihe-result-light-direction-angle57](/images/xihe-result-light-direction-angle57.jpg)


*相关场景模型取自[The Breakfast Room(License: CC-BY)](https://blendswap.com/blend/13363)*
