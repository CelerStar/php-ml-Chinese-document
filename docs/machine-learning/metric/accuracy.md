# Accuracy

用于计算分类器精度的类。

### Score

计算分类器精度得分使用 `score` 静态方法。参数：

* $actualLabels - (array) true sample labels
* $predictedLabels - (array) 预测标签（来自测试组）
* $normalize - (bool) normalize或not结果 (default: true)

### Example

```
$actualLabels = ['a', 'b', 'a', 'b'];
$predictedLabels = ['a', 'a', 'a', 'b'];

Accuracy::score($actualLabels, $predictedLabels);
// return 0.75

Accuracy::score($actualLabels, $predictedLabels, false);
// return 3
```
