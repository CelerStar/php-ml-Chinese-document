# Tf-idf Transformer

Tf–idf, 是术语频率逆文档频率的缩写，是一个数字统计，旨在反映词汇对集合或语料库中的文档的重要性。

### Constructor Parameters

* $samples (array) - 适合tf-idf模型的样本

```
use Phpml\FeatureExtraction\TfIdfTransformer;

$samples = [
    [1, 2, 4],
    [0, 2, 1]
];

$transformer = new TfIdfTransformer($samples);
```

### Transformation

要转换文本样本的集合使用 `transform`方法。例：

```
use Phpml\FeatureExtraction\TfIdfTransformer;

$samples = [
    [0 => 1, 1 => 1, 2 => 2, 3 => 1, 4 => 0, 5 => 0],
    [0 => 1, 1 => 1, 2 => 0, 3 => 0, 4 => 2, 5 => 3],
];
        
$transformer = new TfIdfTransformer($samples);
$transformer->transform($samples);

/*
$samples = [
   [0 => 0, 1 => 0, 2 => 0.602, 3 => 0.301, 4 => 0, 5 => 0],
   [0 => 0, 1 => 0, 2 => 0, 3 => 0, 4 => 0.602, 5 => 0.903],
];
*/
        
```
