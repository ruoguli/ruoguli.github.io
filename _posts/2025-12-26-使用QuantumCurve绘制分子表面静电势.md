---
title: 使用QuantumCurve绘制分子表面静电势
date: 2025-12-26 12:00:00 +0800
categories:
  - QC
tags:
  - QC
description: 仅供参考
---
最后更新时间：2025-12-27

## 1. 输入文件准备
你需要载入含有波函数信息的输入文件，以下为支持的文件类型：

> [!example]
> Gaussian产生的.fch或.fchk文件。

> [!example]
> ORCA产生的.molden文件。(.molden.input文件也是一样的)。从0.1.7版本开始，支持含有波函数信息的JSON文件。

⚠️使用**orca_2mkl**命令可以将.gbw文件转化为.molden.input文件。

> [!example]
> .wfn文件或.multiwfn文件。

## 2. 绘制分子表面静电势
在本例中我们使用examples/ESP/benzene.molden文件。你可以在上述路径或者github仓库中找到。
1. 载入文件后，选择Analysis中的Electrostatic potential (ESP)即可。其余部分如无必要，不用修改。
2. 点击Run，需要等待一段时间才能看到结果⌛️。现在计算的效率还不够高，还需要优化。
3. 计算完成后关闭Electrostatic potential (ESP)界面。输入文件的路径中会出现一个benzene_ESP.cube文件。
4. 关闭Electrostatic potential (ESP)界面会显示出分子表面静电势的填色图，下图所示。但是这样的图我们往往无法很好的看到颜色的交界。例如此例中我们很难看到红蓝交界。


![benzene_esp_fig_1](/assets/img/posts/qc/esp/benzene_esp_fig_1.png){: .normal } _Fig. 1. 初次载入后的分子表面静电势图_


5. 右键-Results-Surface修改箭头所指的两处数值，此例中我们修改为-15和15。保存后就能看到红蓝交界的填色图。


![benzene_esp_fig_2](/assets/img/posts/qc/esp/benzene_esp_fig_2.png){: .normal } _Fig. 2. 设置渲染表面_


![benzene_esp_fig_3](/assets/img/posts/qc/esp/benzene_esp_fig_3.png){: .normal } _Fig. 3. 看起来效果更好的分子表面静电势图_


6. 如果需要显示局部极大值/极小值同样可以右键-Results-Surface修改。

⚠️注意如果步骤5中没有立即显示出红蓝交界，可以尝试重新载入benzene_ESP.cube文件。
