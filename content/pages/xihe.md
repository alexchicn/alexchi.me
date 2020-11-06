---
title: "羲和"
#author: "Alex Chi"
date: 2020-03-01T00:00:00+08:00
draft: false
menu: "main"
weight: 1
#image: "images/*.jpg"
meta: true
toc: true
categories: []
tags: []
---

一个承载最新技术的渲染器。

## 特性和进展

* 基础
    * [x] 整合[OptiX] 7.0
    * [x] 整合[MDL]
    * [x] 基于FlatBuffers定义渲染数据
* 灯光
    * [x] 平行光
        * [x] 颜色
        * [x] 强度
        * [x] 方向
        * [x] 散射
        * [x] 距离
    * 点光
        * [x] 颜色
        * [x] 强度
        * [ ] 发光体半径
        * [x] 距离
    * 射灯
        * [ ] 颜色
        * [ ] 强度
        * [ ] 发光体半径
        * [ ] 距离
        * [ ] 方向
        * [ ] IES
    * [ ] 面光
* 材质
    * [x] 整合[MDL]
    * [x] 固有色
    * [ ] 漫反射贴图
    * [x] 金属色
    * [ ] 金属贴图
    * [x] 粗糙度/光滑度
    * [ ] 粗糙贴图/光滑贴图
    * [x] 自发光
    * [ ] 折射率
    * [ ] 遮罩
* 模型
    * [x] 三角面
        * [x] 顶点
        * [x] 颜色
        * [x] 法线
        * [x] 切线
        * [x] UV
* 相机
    * 透视
        * [x] FOV
        * [ ] 最近距离
        * [ ] 最远距离
    * [ ] 平视
    * [ ] 全景
* 工具
    * 将glTF转换为可加载的FlatBuffers二进制数据
        * [x] 平行光
        * [ ] 点光
        * [ ] glTF材质
        * [x] 模型
        * [x] 透视相机
    * [x] 场景查看器


## 相关文章

* [羲和开发日志（二） 平行光](/posts/xihe-development-log-2-direction-light)
* [羲和开发日志（一） 项目介绍](/posts/xihe-development-log-1st-intro)

## 渲染结果

### 2020-11-06

![xihe-result-20201106](/images/xihe-result-20201106.jpg)

*相关场景模型取自[The Breakfast Room(License: CC-BY)](https://blendswap.com/blend/13363)*

### 2020-11-03

![xihe-result-20201103a](/images/xihe-result-20201103a.jpg)

*相关场景模型取自[The Breakfast Room(License: CC-BY)](https://blendswap.com/blend/13363)*

### 2020-11-01

![xihe-result-20201103a](/images/xihe-intro-result.jpg)

[MDL]: https://www.nvidia.com/en-us/design-visualization/technologies/material-definition-language/
[OptiX]: https://developer.nvidia.com/optix
[CUDA]: https://developer.nvidia.com/cuda-toolkit
