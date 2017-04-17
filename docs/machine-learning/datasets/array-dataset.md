# ArrayDataset

将数据保存为PHP  `array`类型的Helper类。实现 `Dataset`在其他类中大量使用的接口。

### Constructors Parameters

* $samples - (array) 的样本
* $labels - (array) 的标签

```
$dataset = new ArrayDataset([[1, 1], [2, 1], [3, 2], [4, 1]], ['a', 'a', 'b', 'b']);
```

### Samples and labels

要获取样品或标签，您可以使用 getters:

```
$dataset->getSamples();
$dataset->getTargets();
```
