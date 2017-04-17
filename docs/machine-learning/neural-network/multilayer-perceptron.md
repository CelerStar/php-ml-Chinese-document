# MultilayerPerceptron

多层感知器（MLP）是前馈人工神经网络模型，其将输入数据集合映射到一组适当的输出。

## Constructor Parameters

* $layers (array) -具有层配置的数组，每个值表示每层中的神经元数
* $activationFunction (ActivationFunction) - 神经元激活功能

```
use Phpml\NeuralNetwork\Network\MultilayerPerceptron;
$mlp = new MultilayerPerceptron([2, 2, 1]);

// 2 nodes in input layer, 2 nodes in first hidden layer and 1 node in output layer 
```

## Methods

* setInput(array $input)
* getOutput()
* getLayers()
* addLayer(Layer $layer)

## Activation Functions

* BinaryStep
* Gaussian
* HyperbolicTangent
* Sigmoid (default)
