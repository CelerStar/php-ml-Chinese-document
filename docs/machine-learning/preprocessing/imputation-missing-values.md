# Imputation missing values

由于各种原因，许多现实世界的数据集包含缺少的值，通常编码为空白，NaN或其他占位符。要解决这个问题，你可以使用 `Imputer` 该类。

## Constructor Parameters

* $missingValue (mixed) -  此值将被替换 (default null)
* $strategy (Strategy) -  插补策略 (read to use: MeanStrategy, MedianStrategy, MostFrequentStrategy)
* $axis (int) - 用于策略的轴，Imputer::AXIS_COLUMN or Imputer::AXIS_ROW

```
$imputer = new Imputer(null, new MeanStrategy(), Imputer::AXIS_COLUMN);
$imputer = new Imputer(null, new MedianStrategy(), Imputer::AXIS_ROW);
```

## Strategy

* MeanStrategy - 使用沿轴的平均值替换缺失值
* MedianStrategy - 使用沿轴的中位数替换缺失值
* MostFrequentStrategy - 使用轴上最频繁的值替换丢失

## Example of use

```
use Phpml\Preprocessing\Imputer;
use Phpml\Preprocessing\Imputer\Strategy\MeanStrategy;

$data = [
    [1, null, 3, 4],
    [4, 3, 2, 1],
    [null, 6, 7, 8],
    [8, 7, null, 5],
];

$imputer = new Imputer(null, new MeanStrategy(), Imputer::AXIS_COLUMN);
$imputer->transform($data);

/*
$data = [
    [1, 5.33, 3, 4],
    [4, 3, 2, 1],
    [4.33, 6, 7, 8],
    [8, 7, 4, 5],
];
*/

```
