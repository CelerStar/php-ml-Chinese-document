# KNearestNeighbors Classifier

分类器实现再邻居算法。

## 构造函数参数

* $k - 最近的临近扫描数量n (默认: 3)
* $distanceMetric - 距离对象, 默认欧几里得 (查阅 [distance documentation](../../math/distance.md))

```
$classifier = new KNearestNeighbors($k=4);
$classifier = new KNearestNeighbors($k=3, new Minkowski($lambda=4));
```

## Train

训练一个分类器只提供训练样本和标签 (as `array`). 示例:

```
$samples = [[1, 3], [1, 4], [2, 4], [3, 1], [4, 1], [4, 2]];
$labels = ['a', 'a', 'a', 'b', 'b', 'b'];

$classifier = new KNearestNeighbors();
$classifier->train($samples, $labels);
```

您可以使用多个数据集,训练分类器的预测将基于数据的所有训练。
## Predict

预测样本标签使用 `predict` 方法。 您可以提供一个样品或样本数组:

```
$classifier->predict([3, 2]);
// return 'b'

$classifier->predict([[3, 2], [1, 5]]);
// return ['b', 'a']
```
