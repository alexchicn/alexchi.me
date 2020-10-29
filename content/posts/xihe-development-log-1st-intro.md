---
title: "“羲和”开发日志（一） 项目介绍"
#author: "Alex Chi"
date: 2020-10-28T22:24:05+08:00
#draft: true
#menu: "main"
image: "images/xihe-intro.jpg"
meta: false
toc: true
comment: true
tags: [ "渲染", "光线追踪", "介绍", "Render", "Ray Tracing", "CUDA", "OptiX", "MDL", "Introduction" ]
categories: [ "羲和", "XiHe" ]
---

> 本文介绍[羲和]项目的背景、目标和技术，当前项目状态请点[这里](../../pages/xihe/)。

## 背景

最近几年随着GPU的进步原来费时费力的光线追踪技术变成了一个热门话题，并且出现了大量相关项目，这样大大降低了渲染技术的门槛。通过很多开源项目可以快速地搭建出属于自己的渲染器。

本人过去几年搞游戏开发，近几年从事家装软件的开发，参与的项目都十分看重效果，所以累积了不少渲染技术。
为了能实现一些想法也构建过自己的渲染器，但是在看到[UnrealEngine]和[CryEngine]都开源了自己的引擎，就放弃了自己的项目:cry:。
不过现在在光线追踪方面有了大量开源项目的支撑，可以让我更专注于渲染核心算法，实现自己的想法:smile:。

### 现状

市面上的渲染器有很多，针对不同市场各自的架构也不同。以下是个人对一些渲染器的了解和看法：

* [OptiX]是由[NVIDIA]提供的光线追踪技术。
* [OpenShaderLanguage] ([OSL])是由[ImageWorks](来自索尼影视)开源的一款影视级着色语言。

#### [Appleseed]

开源，基于CPU进行渲染，出色的性能。不少影视作品采用了此项目进行场景渲染，我所知道《权力游戏》就采用此软件。

#### [Mitsuba2]

开源，由几位行业知名的教授共同构建，既可以进行CPU渲染，也可以通过[OptiX]进行GPU渲染。它是一个非常值得好好研究学习的项目。

#### [V-Ray]

建筑行业的标杆，无需多介绍。目前也支持GPU运算。

#### [Iray]

[NVIDIA]开发的渲染库，需要购买商业授权。从介绍来看既可以实时渲染也可以进行影视渲染，功能十分强大，像知名的[KeyShot]这样的渲染软件就是基于此库开发的。

#### [OctaneRender]

很早就开始使用GPU进行渲染的一款软件，其渲染内核是基于[OptiX]和[OSL]。一方面它在运用GPU加速方面十分出色，另一方面[OSL]使得其使用起来更方便快捷。

它有几种渲染内核，其中**Path Tracing**是最耗时但效果最真实的，每种内核都是在光栅化和光线追踪之间进行取舍。用户可以通过**Direct Lighting**进行快速地预览，通过**Path Tracing**得到最终的产品。
另外最近几年又针对AMD的GPU进行了开发使得它能够脱离[NVIDIA]的[OptiX]在更多GPU上运行。

#### [UnrealEngine]

严格来讲UE4不算是渲染器，是一个游戏引擎，但是近几年来它以出色的实时渲染效果和开源政策，得到了市场的青睐。各个行业都拿它来秀效果，从游戏到房地产，从影视到智慧城市，都想和它有交集。不过在经过一段时间的磨合后会发现UE4的开发难度真的不低，对于软件开发和技术美术来说都是不小的挑战。要知道**各个行业的需求不仅仅是画面和效果，还包含很多特有的功能，而一个游戏引擎是无法满足的，所以找到合适的最重要。**

前段时间UE5的演示也震撼了很多人，个人觉得[EpicGames]在实时渲染方面运用了更多光线追踪原理，使得实时渲染进一步靠近光线追踪。

## 目的

市面上已经有这么多渲染器为什么还要再做一个呢？
的确市面上有很多非常棒的渲染器，但是想要实现自己的算法在现有渲染器下进行改造是比较困难的。
所以这个项目的目的就是能够承载更多的渲染算法和最新技术。

## 技术

通过NVIDIA的[OptiX]和[CUDA]实现光线追踪算法，并利用[MDL]来表达材质。

> #### 关于命名
>
> 渲染离不开对光的研究，而光学追踪更是如此，那么传说中的太阳神应该对光十分了解。在中国的神话中“**羲和**”是[中国古代神话的太阳女神](https://baike.baidu.com/item/%E7%BE%B2%E5%92%8C/278594)，所以选用“**羲和**”来命名这个项目。

[羲和]: ../../pages/xihe/
[UnrealEngine]: https://www.unrealengine.com/
[CryEngine]: https://www.cryengine.com/
[Appleseed]: https://appleseedhq.net/
[LuxCoreRender]: https://luxcorerender.org/
[Mitsuba2]: https://github.com/mitsuba-renderer/mitsuba2
[V-Ray]: https://www.chaosgroup.com/
[Iray]: https://www.nvidia.com/en-us/design-visualization/iray/
[OctaneRender]: https://home.otoy.com/render/octane-render/
[MDL]: https://www.nvidia.com/en-us/design-visualization/technologies/material-definition-language/
[OptiX]: https://developer.nvidia.com/optix
[CUDA]: https://developer.nvidia.com/cuda-toolkit
[OSL]: https://github.com/imageworks/OpenShadingLanguage/
[OpenShaderLanguage]: https://github.com/imageworks/OpenShadingLanguage/
[ImageWorks]: http://opensource.imageworks.com/
[NVIDIA]: https://www.nvidia.com/
[KeyShot]: https://www.keyshot.com/
[EpicGames]: https://www.epicgames.com/