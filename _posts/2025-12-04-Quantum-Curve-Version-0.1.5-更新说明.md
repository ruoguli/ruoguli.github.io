---
title: Quantum Curve Version 0.1.5 更新说明
date: 2025-12-17 12:00:00 +0800
categories:
  - QC
tags:
  - QC
description: 仅供参考
---

[下载链接🔗](https://github.com/ruoguli/Quantum-Curve)

1. 本次更新主要是优化了性能，特别是在载入.cube/.cub文件上。在测试集中3MB大小的cube文件的载入速度加快了4倍，在30MB大小的文件中加快了10倍。
2. 修改了双键/三键的显示逻辑。这个问题是根据NFBO所提供的一些文件在使用旧版本的QC中发现的。目前对于新逻辑可能造成的其他影响还需要广泛验证。
3. 实现了更高性能的分子渲染，在400+原子的测试集中帧率由30+提升至50+。效果不错，但是还是需要继续改进，VESTA中的帧率明显会更顺畅。
