---
title: Quantum Curve Version 0.1.7 更新说明
date: 2025-12-26 12:00:00 +0800
categories:
  - QC
tags:
  - QC
description: 仅供参考
---

[下载链接🔗](https://github.com/ruoguli/Quantum-Curve)

1. 修改了ORCA的.out文件的读取逻辑，我注意到在某些情况下会出现错误的轨迹读取结果。
2. 修改了IR光谱页面的列表区域。
3. 支持了orca_2json产生的.json文件中分子坐标和轨道信息的读取。这是一个早期的版本，由于ORCA本身对于JSON输出的支持还处于早期，我们会持续跟进。对于轨道信息的读取可能还存在错误，需要广泛测试。载入ORCA产生的JSON文件后，会在同一路径下产生一个.molden文件。
4. 修正了渲染等值面后修改ISO可能存在的错误。

