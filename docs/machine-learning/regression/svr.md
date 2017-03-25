# Support Vector Regression

基于libsvm实现Epsilon支持向量回归的类。

### Constructor Parameters

* $kernel (int) -在算法中使用的内核类型 (默认 Kernel::LINEAR)
* $degree (int) - Kernel::POLYNOMIAL 函数等级 (default 3)
* $epsilon (float) -  epsilon in loss function of epsilon-SVR (默认 0.1)
* $cost (float) - C-SVC 的参数C (default 1.0)
* $gamma (float) - ‘Kernel::RBF’, ‘Kernel::POLYNOMIAL’ 和 ‘Kernel::SIGMOID’ 内核系数。 如果 gamma 是 ‘null’ 则将使用 1/features 。
* $coef0 (float) - 内核函数中的独立项。 It is only significant in ‘Kernel::POLYNOMIAL’ and ‘Kernel::SIGMOID’ (default 0.0)
* $tolerance (float) - 终止标准容限 (默认 0.001)
* $cacheSize (int) -  缓存内存大小（MB） (默认 100)
* $shrinking (bool) - 是否使用缩减启发式 (默认 true)

```
$regression = new SVR(Kernel::LINEAR);
$regression = new SVR(Kernel::LINEAR, $degree = 3, $epsilon=10.0);
```

### Train

训练模型只需提供列车样本和目标值 (as `array`). 示例:

```
use Phpml\Regression\SVR;
use Phpml\SupportVectorMachine\Kernel;

$samples = [[60], [61], [62], [63], [65]];
$targets = [3.1, 3.6, 3.8, 4, 4.1];

$regression = new SVR(Kernel::LINEAR);
$regression->train($samples, $targets);
```

您可以使用多个数据集来训练模型，预测将基于所有的训练数据。

### Predict

预测样本目标值使用 `predict` 方法。您可以提供一个样品或样品阵列：

```
$regression->predict([64])
// return 4.03
```
