---
title: Quantum Curve Version 0.1.3 更新说明
date: 2025-12-04 12:00:00 +0800
categories:
  - QC
tags:
  - QC
description: 仅供参考
---

[下载链接🔗](https://github.com/ruoguli/Quantum-Curve)

1. 这个版本中我们支持了Qbics项目的输入文件/输出文件的基本分子坐标的解析，也支持了对于结构优化过程中的能量变化情况跟踪。(潜在的错误是播放帧的时候旋转分子可能会出现跳动问题)
2. 支持了Multiwfn的.mwfn类文件的载入支持。
3. 支持了VASP的CHGCAR文件的支持。
4. 支持了电子密度差的计算。仅测试了.fchk/.molden类文件。
5. 修改了部分渲染功能的实现。

⚠️1. 当前程序对于含有周期性结构信息文件的支持依旧太差。
⚠️2. 当前原子数较多的时候，程序容易出现卡死。
