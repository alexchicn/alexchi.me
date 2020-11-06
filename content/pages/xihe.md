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

这是一个**渲染服务**项目，希望未来能够以云服务形式让更多人轻易地接触到高质量渲染效果，并且通过不断地迭代技术来提升其易用性。

## 特性和进展

* 基础
    * [x] 整合[CUDA] 11.0
    * [x] 整合[OptiX] 7.0
    * [x] 整合[MDL]
    * [x] 使用[FlatBuffers]定义渲染数据
    * [x] 构建光线追踪算法框架
    * [ ] 检查显卡驱动和CUDA版本
    * [ ] 支持多GPU
    * [ ] 渲染服务
* 灯光
    * [x] 平行光
        * [x] 颜色
        * [x] 强度
        * [x] 方向
        * [x] 散射角
        * [x] 长度
    * 点光
        * [x] 颜色
        * [x] 强度
        * [x] 半径
        * [x] 长度
    * 射灯
        * [ ] 颜色
        * [ ] 强度
        * [ ] 半径
        * [ ] 长度
        * [ ] 方向
        * [ ] 内角
        * [ ] 外角
        * [ ] IES
    * [ ] 面光
* 材质
    * [x] 固有色
    * [ ] 漫反射贴图
    * [x] 金属色
    * [ ] 金属贴图
    * [x] 粗糙度/光滑度
    * [ ] 粗糙贴图/光滑贴图
    * [x] 自发光
    * [ ] 半透明
    * [ ] 折射率
    * [ ] 遮罩贴图
    * [ ] 多层重叠
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
        * [ ] 景深
    * [ ] 平视
    * [ ] 全景
* 场景
    * [ ] 背景材质
    * [ ] 反弹次数
        * [ ] 半透材质
        * [ ] 非半透材质
    * [ ] 采样次数
* 后期
    * 降噪
        * [x] [Nvidia DLSS]
        * [ ] [Intel Open Image Denoise]
    * 输出
        * [x] 光线跟踪图
        * [x] 法线图
        * [x] 模型实例分层图
        * [ ] 金属度图
        * [ ] 粗糙度图
* 工具
    * 构建[FlatBuffers]场景数据
        * 通过[glTF]
            * [x] 平行光
            * [x] 点光
            * [ ] 射灯
            * [ ] 面光
            * [ ] glTF材质
            * [x] 模型
            * [x] 透视相机
        * 通过[Blender]
            * [ ] 平行光
            * [ ] 点光
            * [ ] 射灯
            * [ ] 面光
            * [ ] 内置材质
            * [x] 模型
            * [x] 透视相机
    * [x] 场景查看器

## 相关文章

* [羲和开发日志（一） 项目介绍](/posts/xihe-development-log-1st-intro)
* [羲和开发日志（二） 平行光](/posts/xihe-development-log-2-direction-light)
* [羲和开发日志（三） 点光](/posts/xihe-development-log-3-point-light)

## 渲染效果展示

### 2020-11-06

![xihe-result-20201106a](/images/xihe-result-20201106a.jpg)

![xihe-result-20201106b](/images/xihe-result-20201106b.jpg)

*相关场景模型取自[The Breakfast Room(License: CC-BY)](https://blendswap.com/blend/13363)*

### 2020-11-03

![xihe-result-20201103a](/images/xihe-result-20201103a.jpg)

*相关场景模型取自[The Breakfast Room(License: CC-BY)](https://blendswap.com/blend/13363)*

### 2020-11-01

![xihe-result-20201103a](/images/xihe-intro-result.jpg)

[CUDA]: https://developer.nvidia.com/cuda-toolkit
[OptiX]: https://developer.nvidia.com/optix
[MDL]: https://www.nvidia.com/en-us/design-visualization/technologies/material-definition-language/
[FlatBuffers]: https://google.github.io/flatbuffers/
[Nvidia DLSS]: https://developer.nvidia.com/dlss
[Intel Open Image Denoise]: https://www.openimagedenoise.org/
[glTF]: https://khronos.org/gltf
[Blender]: http://blender.org/
