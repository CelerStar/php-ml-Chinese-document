# Apriori Associator

学习基于关联规则 [Apriori algorithm](https://en.wikipedia.org/wiki/Apriori_algorithm) 的频繁项集挖掘。

### Constructor Parameters

* $support - [confidence](https://en.wikipedia.org/wiki/Association_rule_learning#Support), 最小相对频繁项目集的训练样本
* $confidence - [confidence](https://en.wikipedia.org/wiki/Association_rule_learning#Confidence), 最小相对数量的项目集频繁项集

```
use Phpml\Association\Apriori;

$associator = new Apriori($support = 0.5, $confidence = 0.5);
```

### Train

训练只需提供训练样本和标签 (as `array`). 示例:

```
$samples = [['alpha', 'beta', 'epsilon'], ['alpha', 'beta', 'theta'], ['alpha', 'beta', 'epsilon'], ['alpha', 'beta', 'theta']];
$labels  = [];

use Phpml\Association\Apriori;

$associator = new Apriori($support = 0.5, $confidence = 0.5);
$associator->train($samples, $labels);
```

您可以使用多个数据集,训练伙伴将基于预测数据的所有训练。

### Predict

预测样本标签使用 `predict` 方法。 您可以提供一个样品或样本数组:

```
$associator->predict(['alpha','theta']);
// return [[['beta']]]

$associator->predict([['alpha','epsilon'],['beta','theta']]);
// return [[['beta']], [['alpha']]]
```

### Associating

生成关联规则简单地使用 `rules` 方法。
 
```
$associator->getRules();
// return [['antecedent' => ['alpha', 'theta'], 'consequent' => ['beta], 'support' => 1.0, 'confidence' => 1.0], ... ]
```

### Frequent item sets

生成k-length频繁项集简单地使用 `apriori` 方法。

```
$associator->apriori();
// return [ 1 => [['alpha'], ['beta'], ['theta'], ['epsilon']], 2 => [...], ...]
```
