# 0006 Live2D 嘴型参数被 motion 覆盖

- 现象：setParameterValueById('ParamMouthOpenY', 1) 之后嘴还是闭的。
- 根因：model.update(dt) 里 motion 会把参数重写一遍。
- 解法：先 internalModel.motionManager.stopAllMotions() → model.update() → 设参数 → coreModel.update() → render。
- 下次注意：Live2D 的参数要在 motion 求值之后再盖。
