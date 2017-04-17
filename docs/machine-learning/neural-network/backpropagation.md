# Backpropagation

Backpropagation "backward propagation of errors"的缩写，是训练人造神经网络的常用方法，与诸如梯度下降的优化方法结合使用。

## Constructor Parameters

* $network (Network) - 网络训练 (for example MultilayerPerceptron instance)
* $theta (int) - 网络theta参数

```
use Phpml\NeuralNetwork\Network\MultilayerPerceptron;
use Phpml\NeuralNetwork\Training\Backpropagation;

$network = new MultilayerPerceptron([2, 2, 1]);
$training = new Backpropagation($network);
```

## Training

异常训练示例：

```
$training->train(
    $samples = [[1, 0], [0, 1], [1, 1], [0, 0]],
    $targets = [[1], [1], [0], [0]],
    $desiredError = 0.2,
    $maxIteraions = 30000
);
```
您可以使用多个数据集训练神经网络，预测将基于所有训练数据。
