---
title: "羲和开发日志（三） 点光"
#author: "Alex Chi"
date: 2020-11-06T21:02:36+08:00
draft: false
image: "images/xihe-result-light-point.jpg"
toc: true
comment: true
categories: [ "羲和", "XiHe", "开发", "Development" ]
tags: [ "渲染", "Render", "光线追踪", "Ray Tracing", "灯光", "Light", "点光", "Point Light" ]
---

## 点光

图形学中，通过点光来模拟小型发光体，如：灯泡、火把、蜡烛等。
这类发光体的特点是从自身表面向周围所有物体发射光线，所以在光线追踪时需要在发光体表面进行采样。
通常使用球体模拟此类物体的形状，根据半径在球表面随机采样。

## 相关参数

* 颜色 - 光源颜色
* 强度 - 光源亮度
* 位置 - 光源位置
* 半径
    * 用于模拟光源尺寸
    * 尺寸不同造成的阴影也不同
    * 参见下图

## 效果展示

颜色、强度和位置是常识，这里就不进行展示。

### 半径

> **通过影子柔和程度可以看出点光半径的大小**

半径为0cm，如下图：

![xihe-result-light-point-radius0](/images/xihe-result-light-point-radius0.jpg)

半径为5cm，如下图：

![xihe-result-light-point-radius5](/images/xihe-result-light-point-radius5.jpg)

半径为20cm，如下图：

![xihe-result-light-point-radius20](/images/xihe-result-light-point-radius20.jpg)

*相关场景模型取自[The Breakfast Room(License: CC-BY)](https://blendswap.com/blend/13363)*
