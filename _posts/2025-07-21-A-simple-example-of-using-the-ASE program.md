---
title: ASE调用代码解析
date: 2025-07-21 09:00:00 +0800
categories:
  - ASE
tags:
  - ASE
description: A burger
---
这是一个简单的ASE入门解析，原始代码来源于官方文档。掌握一定的DFT和Python基础之后，很快就能明白该部分内容。让我们来看看这段代码[🔗](https://wiki.fysik.dtu.dk/ase/gettingstarted/surface.html)：

```python
#调用库 ,这里的MET指的是原子势，不适用于纯金属体系
from ase import Atoms
from ase.build import add_adsorbate, fcc111
from ase.calculators.emt import EMT
from ase.constraints import FixAtoms
from ase.optimize import QuasiNewton

h = 1.85
d = 1.10#另一个N原子在c方向上的高度，既然N-N键的长度，埃米，第一个N原子位于布拉维点阵原点

slab = fcc111('Cu', size=(4, 4, 2), vacuum=10.0)
slab.calc = EMT()
e_slab = slab.get_potential_energy()
molecule = Atoms('2N', positions=[(0.0, 0.0, 0.0), (0.0, 0.0, d)])
molecule.calc = EMT()
e_N2 = molecule.get_potential_energy()
add_adsorbate(slab, molecule, h, 'ontop')
constraint = FixAtoms(mask=[a.symbol != 'N' for a in slab])
slab.set_constraint(constraint)
dyn = QuasiNewton(slab, trajectory='N2Cu.traj')
dyn.run(fmax=0.05)
print('Adsorption energy:', e_slab + e_N2 - slab.get_potential_energy())
```



