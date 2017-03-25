# LeastSquares Linear Regression

使用最小二乘法逼近解的线性模型。

### Train

训练模型只需提供列车样本和目标值 (as `array`). 示例:

```
$samples = [[60], [61], [62], [63], [65]];
$targets = [3.1, 3.6, 3.8, 4, 4.1];

$regression = new LeastSquares();
$regression->train($samples, $targets);
```

您可以使用多个数据集来训练模型，预测将基于所有的训练数据。

### Predict

`predict` 用样本预测样本目标值使用方法，以检查 (as `array`). 示例:

```
$regression->predict([64]);
// return 4.06
```

### Multiple Linear Regression

与线性回归相关的术语多数表示有两个或更多个样本参数用于预测目标。例如，您可以使用：里程和生产年份来预测汽车的价格。

```
$samples = [[73676, 1996], [77006, 1998], [10565, 2000], [146088, 1995], [15000, 2001], [65940, 2000], [9300, 2000], [93739, 1996], [153260, 1994], [17764, 2002], [57000, 1998], [15000, 2000]];
$targets = [2000, 2750, 15500, 960, 4400, 8800, 7100, 2550, 1025, 5900, 4600, 4400];

$regression = new LeastSquares();
$regression->train($samples, $targets);
$regression->predict([60000, 1996])
// return 4094.82
```

### Intercept and Coefficients

训练你的模型后，你可以得到截距和系数数组。
```
$regression->getIntercept();
// return -7.9635135135131

$regression->getCoefficients();
// return [array(1) {[0]=>float(0.18783783783783)}]
```
