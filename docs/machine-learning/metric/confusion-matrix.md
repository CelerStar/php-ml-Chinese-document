# Confusion Matrix

用于计算混淆矩阵的类来评估分类的准确性。

### Example (all targets)

为所有目标计算ConfusionMatrix。

```
use Phpml\Metric\ConfusionMatrix;

$actualTargets = [2, 0, 2, 2, 0, 1];
$predictedTargets = [0, 0, 2, 2, 0, 2];

$confusionMatrix = ConfusionMatrix::compute($actualTargets, $predictedTargets)

/*
$confusionMatrix = [
    [2, 0, 0],
    [0, 0, 1],
    [1, 0, 2],
];
*/
```

### Example (chosen targets)

为所选目标计算ConfusionMatrix。

```
use Phpml\Metric\ConfusionMatrix;

$actualTargets = ['cat', 'ant', 'cat', 'cat', 'ant', 'bird'];
$predictedTargets = ['ant', 'ant', 'cat', 'cat', 'ant', 'cat'];

$confusionMatrix = ConfusionMatrix::compute($actualTargets, $predictedTargets, ['ant', 'bird'])

/*
$confusionMatrix = [
    [2, 0],
    [0, 0],
];
*/
```
