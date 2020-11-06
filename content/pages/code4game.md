---
title: "Code 4 Game"
date: 2020-02-01T00:00:00+08:00
#draft: true
menu: "main"
weight: 0
#image: "/images/*.jpg"
meta: true
toc: true
comment: false
categories: []
tags: []
---

> 关注于游戏相关开发，为游戏开发者提供一些有用的工具

## [glTF]

这是由[Khronos]提出的三维场景数据格式，类似于Autodesk的FBX或Pixel的USD，不过该格式对于网页端更友好。
以下是为支持该格式所开发的项目：

### [libgltf]

这是一个C++项目，用于加载和解析[glTF]文件，同时兼容很多[glTF]的扩展。

此外该项目还包含一个用python开发的一个C++代码生成器，在[glTF]的格式有更新时可以通过该工具自动更新项目中的C++代码。

### [libgltf_ue4]

一个UE4的第三方库。

### [glTF for UE4]

一个UE4的插件，当前可以将[glTF]文件导入到UE4编辑器中。

详情请见[这里](https://gltf-for-ue4.readthedocs.io/)。

[Khronos]: https://www.khronos.org/
[glTF]: https://www.khronos.org/gltf
[libgltf]: https://github.com/code4game/libgltf
[libgltf_ue4]: https://github.com/code4game/libgltf_ue4
[glTF for UE4]: https://github.com/code4game/glTFForUE4

