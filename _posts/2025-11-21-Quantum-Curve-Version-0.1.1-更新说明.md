---
title: Quantum Curve Version 0.1.1 更新说明
date:   2025-11-21 12:00:00 +0800
categories: [QC]
tags: [QC]
description: 仅供参考
---

[下载链接🔗](https://github.com/ruoguli/Quantum-Curve)

1. 更新了右键移动的交互方式，之前的版本中会导致移动后奇怪的旋转中心。Ctrl + 右键的逻辑没有更改。

2. 支持了从ORCA的.out/.hess文件中中读取振动频率信息和结构信息，可以在Results-IR中查看。支持输出频率文件为.txt/.csv文件。

3. 支持了Gaussian的输出文件.out/.log中读取频率信息和结构信息。

4. 支持了从ORCA的.out文件中提取结构优化中每一步的结构信息。

5. 支持了从ORCA的.molden文件(由.gbw文件产生)中读取信息，并产生对应的HOMO/LUMO轨道信息为.cube文件。

6. 支持了从.cif文件中读取结构信息和晶胞信息，并可以在面板中修改晶胞参数。支持输出文件为.cif文件。支持带有结构信息的.gjf文件与.cif文件的相互转换。

7. 支持了从ORCA/Gaussian的输出文件中结构优化过程中提取能量变化情况。
 
8. 碳原子的标签修改为白色。

9. 新增棍模型和线模型。支持了化学键的着色开关，开启后将按照临近原子的着色来渲染化学键的颜色。

10. 支持了将渲染区域的内容输出为.jpg/.svg/.pdf。

11. 支持了修改渲染区的背景颜色。

12. 实现了从POSCAR/STRU/.wfn/.wfx文件中读取化学结构信息。

13. 实现从QE的.in文件中读取化学结构信息。

14. 支持Gaussian/ORCA中的幽灵原子的可视化。元素周期表中添加了幽灵原子。

15. 支持了修改应用的字体。

16. 支持了SSH连接远程服务器。

17. 剩下的懒得写了。

⚠️注意：
1. .cif文件的读取依然存在问题。特别是一些棘手的地方，例如某个碳原子的位置并不准确，有两个可能的位置。而原始数据中的占据数均为1，那么解析出来的坐标可能是含有重复原子的结构。
2. ORCA面板的输入暂未完善还有较大缺失。


以下是目前版本支持读取/输入的文件类型：



| V 0.1.1  |     Format     | Atom coordinates (I/O) | Cell | Vibrations (I) | Optimization (I) | GTFs | Version |
| :------: | :------------: | :--------------------: | ---- | :------------: | :--------------: | :--: | :-----: |
|          |      .xyz      |          ✅/✅           |      |                |                  |      |  Beta   |
|          |      .mol      |          ✅/❌           |      |                |                  |      |  Beta   |
|          |     .mol2      |          ✅/❌           |      |                |                  |      |  Beta   |
|          |      .pdb      |          ✅/✅           |      |                |                  |      |  Beta   |
|          |      .cif      |          ✅/✅           | ✅    |                |                  |      |  Beta   |
|          |   .cube/.cub   |          ✅/❌           |      |                |                  |      |  Beta   |
|          |      .wfn      |          ✅/❌           |      |                |                  |      |  Beta   |
|   ORCA   |      .inp      |          ✅/✅           |      |                |                  |      |  Beta   |
|   ORCA   |      .out      |          ✅/❌           |      |       ✅        |        ✅         |      |  Beta   |
|   ORCA   |     .hess      |          ✅/❌           |      |       ✅        |                  |      |  Beta   |
|   ORCA   | .molden/.input |          ✅/❌           |      |                |                  |  ✅   |  Beta   |
| Gaussian |      .gjf      |          ✅/✅           | ✅    |                |                  |      |  Beta   |
| Gaussian |   .out/.log    |          ✅/❌           |      |       ✅        |        ✅         |      |  Beta   |
| Gaussian |   .fch/.fchk   |          ✅/❌           |      |                |                  |  ✅   |  Beta   |
| Gaussian |      .wfx      |          ✅/❌           |      |                |                  |      |  Beta   |
|  MOPAC   |      .mop      |          ✅/❌           |      |                |                  |      |  Beta   |
|   PSI4   |      .inp      |          ✅/❌           |      |                |                  |      |  Beta   |
|   CP2K   | .inp/.restart  |          ✅/❌           | ✅    |                |                  |      |  Beta   |
|    QE    |      .in       |          ✅/❌           | ✅    |                |                  |      |  Beta   |
|   VASP   |     POSCAR     |          ✅/✅           | ✅    |                |                  |      |  Beta   |
|  ABACUS  |      STRU      |          ✅/❌           | ✅    |                |                  |      |  Beta   |
|          |                |                        |      |                |                  |      |         |

⚠️这个版本支持了渲染HOMO/LUMO轨道，但依然属于早期版本。可以载入Gaussian产生的.fch/.fchk文件和ORCA产生的.molden/.input文件。ORCA产生.molden/.input文件的方法为，在filename.gbw文件所在路径下使用命令：
`orca_2mkl filename -molden`
即可以得到filename.molden.input文件。如果你不喜欢Quantum Curve产生的HOMO/LUMO填色图，可以导出为.cube然后导入到其他程序中，例如VESTA。

⚠️这个版本同样支持.xyz的多帧文件，但优化了一些布局页面。

⚠️这个版本绘制IR图谱所用的FWHM为10。













