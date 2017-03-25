# Classification Report

计算主分类器度量的类： precision, recall, F1 score and support.

### Report

要生成报告，您必须提供以下参数：

* $actualLabels - (array) true sample labels
* $predictedLabels - (array) 预测标签（来自测试组）

```
use Phpml\Metric\ClassificationReport;

$actualLabels = ['cat', 'ant', 'bird', 'bird', 'bird'];
$predictedLabels = ['cat', 'cat', 'bird', 'bird', 'ant'];

$report = new ClassificationReport($actualLabels, $predictedLabels);
```

### Metrics

创建报告后，您可以绘制其各自的指标：

* precision (`getPrecision()`) - 相关的检索到的实例的分数
* recall (`getRecall()`) - 检索到的相关实例的分数
* F1 score (`getF1score()`) - 测试测试的准确性
* support (`getSupport()`) - 测试样本数

```
$precision = $report->getPrecision();

// $precision = ['cat' => 0.5, 'ant' => 0.0, 'bird' => 1.0];
```

### Example

```
use Phpml\Metric\ClassificationReport;

$actualLabels = ['cat', 'ant', 'bird', 'bird', 'bird'];
$predictedLabels = ['cat', 'cat', 'bird', 'bird', 'ant'];

$report = new ClassificationReport($actualLabels, $predictedLabels);

$report->getPrecision();
// ['cat' => 0.5, 'ant' => 0.0, 'bird' => 1.0]

$report->getRecall();
// ['cat' => 1.0, 'ant' => 0.0, 'bird' => 0.67]

$report->getF1score();
// ['cat' => 0.67, 'ant' => 0.0, 'bird' => 0.80]

$report->getSupport();
// ['cat' => 1, 'ant' => 1, 'bird' => 3]

$report->getAverage();
// ['precision' => 0.75, 'recall' => 0.83, 'f1score' => 0.73]

```
