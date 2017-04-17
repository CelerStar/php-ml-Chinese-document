# Pipeline

在机器学习中，通常运行一系列算法来处理和学习数据集。例如：

    * Split each document’s text into tokens.
    * Convert each document’s words into a numerical feature vector ([Token Count Vectorizer](machine-learning/feature-extraction/token-count-vectorizer/)).
    * Learn a prediction model using the feature vectors and labels.
    
PHP-ML表示作为流水线的工作流程，其中包含变压器序列和估计器。


### Constructor Parameters

* $transformers (array|Transformer[]) - 实现Transformer接口的对象序列
* $estimator (Estimator) - 可以训练和预测的估计

```
use Phpml\Classification\SVC;
use Phpml\FeatureExtraction\TfIdfTransformer;
use Phpml\Pipeline;

$transformers = [
    new TfIdfTransformer(),
];
$estimator = new SVC();

$pipeline = new Pipeline($transformers, $estimator);
```

### Example

首先我们的管道代替缺失值，然后对样本进行归一化，最后训练SVC估计。如此制备的管道重复每个转化步骤用于预测样品。

```
use Phpml\Classification\SVC;
use Phpml\Pipeline;
use Phpml\Preprocessing\Imputer;
use Phpml\Preprocessing\Normalizer;
use Phpml\Preprocessing\Imputer\Strategy\MostFrequentStrategy;

$transformers = [
    new Imputer(null, new MostFrequentStrategy()),
    new Normalizer(),
];
$estimator = new SVC();

$samples = [
    [1, -1, 2],
    [2, 0, null],
    [null, 1, -1],
];

$targets = [
    4,
    1,
    4,
];

$pipeline = new Pipeline($transformers, $estimator);
$pipeline->train($samples, $targets);

$predicted = $pipeline->predict([[0, 0, 0]]);

// $predicted == 4
```
