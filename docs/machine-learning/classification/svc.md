# Support Vector Classification

基于libsvm实现支持向量机分类器。

### 构造函数参数

* $kernel (int) - 内核类型使用的算法 (默认 Kernel::LINEAR)
* $cost (float) - 参数 C of C-SVC (默认 1.0)
* $degree (int) - Kernel::POLYNOMIAL function 等级(默认 3)
* $gamma (float) - kernel coefficient for ‘Kernel::RBF’, ‘Kernel::POLYNOMIAL’ and ‘Kernel::SIGMOID’. 如果 gamma 是 ‘null’ 则 1/features 将被使用.
* $coef0 (float) - 独立 term in kernel function. 它仅在 ‘Kernel::POLYNOMIAL’ and ‘Kernel::SIGMOID’ 有效(默认 0.0)
* $tolerance (float) - 标准公差 (默认 0.001)
* $cacheSize (int) - 缓存内存大小 MB (默认 100)
* $shrinking (bool) - 是否使用启发式 (默认 true)
* $probabilityEstimates (bool) - 是否启用概率估计 (默认 false)

```
$classifier = new SVC(Kernel::LINEAR, $cost = 1000);
$classifier = new SVC(Kernel::RBF, $cost = 1000, $degree = 3, $gamma = 6);
```

### Train

训练一个分类器只提供训练样本和标签 (as `array`). 示例:

```
use Phpml\Classification\SVC;
use Phpml\SupportVectorMachine\Kernel;

$samples = [[1, 3], [1, 4], [2, 4], [3, 1], [4, 1], [4, 2]];
$labels = ['a', 'a', 'a', 'b', 'b', 'b'];

$classifier = new SVC(Kernel::LINEAR, $cost = 1000);
$classifier->train($samples, $labels);
```

您可以使用多个数据集,训练分类器的预测将基于数据的所有训练。

### Predict

预测样本标签使用 `predict` 方法。 您可以提供一个样品或样本数组:

```
$classifier->predict([3, 2]);
// return 'b'

$classifier->predict([[3, 2], [1, 5]]);
// return ['b', 'a']
```
