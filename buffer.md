# buffer

## 超声波换能器要符合食品级标准问题

详细问题：液内型超声波换能器NU1ME12TR-1的表面材料不符合食品级标准。现需要将超声波换能器浸入食用酒精(长时间接触，浓度大于50%，最高温度超过50摄氏度)。怎么解决？

悬赏：400元

时间：本页面存在期间有效；本页面内容删除时失效。

交付：1完整可行的机械结构方案(不需要交付软硬件方案)；2涉及的技术及泛化的相关技术细节全部交接。

能做并且想接的，请先和我联系沟通细节。

### 附件-思路

公开购买渠道目前暂未找到符合要求的食品级超声波探头。

用某种可以和待测酒精接触的材料隔开(如将换能器放在食品级不锈钢、玻璃等材料的平底管子里)；但如果分隔的不锈钢太厚(如0.5mm)，则由于阻抗严重不匹配，超声波换能器无法检出回波，所以间隔层不能厚。

公开购买渠道目前暂未找到符合要求的材料(如搜不到食品级0.1mm厚的不锈钢)，自己加工也不会(例如如何加工出0.1mm厚的玻璃层，且保证和换能器的固定角度)。

如果采用给换能器镀膜的方法，目前暂未找到合适的膜材料，就算找到，如何解决长时间使用时膜被固定装置磨掉等问题。

等等。

### 附件-比较理想的机械结构件3D图（暂无代加工的接，也有可能是国庆放假）

freecad软件

```

import Part

from FreeCAD import Vector


radius = 6.5

thickness = 0.5


cylinder = Part.makeCylinder(radius + thickness, 50, Vector(0,0,0))#tube

cylinder2 = Part.makeCylinder(radius, 50, Vector(0,0,0))

cylinder = cylinder.cut(cylinder2)

Part.show(cylinder)


cylinder = Part.makeCylinder(radius, 0.1, Vector(0,0,0))#bottom

Part.show(cylinder)


cylinder = Part.makeCylinder(radius + thickness, 50, Vector(0,0,-50))#tube

cylinder2 = Part.makeCylinder(radius, 50, Vector(0,0,-50))

cylinder = cylinder.cut(cylinder2)

box = Part.makeBox(2 * (radius+thickness), radius/2, 50, Vector(-(radius+thickness), -radius/4, -50))

cylinder = cylinder.cut(box)

box = Part.makeBox(radius/2, 2 * (radius+thickness), 50, Vector(-radius/4, -(radius+thickness), -50))

cylinder = cylinder.cut(box)

Part.show(cylinder)


cylinder = Part.makeCylinder(radius, 1, Vector(0,0,-50))#bottom

Part.show(cylinder)

```

## 其它
