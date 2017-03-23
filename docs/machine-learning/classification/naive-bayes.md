# NaiveBayes Classifier

分类器基于应用贝叶斯定理(naive)强劲的独立假设之间的特性。

### Train

训练一个分类器只提供训练样本和标签 (as `array`). 示例:

```
$samples = [[5, 1, 1], [1, 5, 1], [1, 1, 5]];
$labels = ['a', 'b', 'c'];

$classifier = new NaiveBayes();
$classifier->train($samples, $labels);
```

您可以使用多个数据集,训练分类器的预测将基于数据的所有训练。

### Predict

预测样本标签使用 `predict` 方法。 您可以提供一个样品或样本数组:

```
$classifier->predict([3, 1, 1]);
// return 'a'

$classifier->predict([[3, 1, 1], [1, 4, 1]);
// return ['a', 'b']
```
