# Token Count Vectorizer

将文本样本集合转换为令牌计数向量。

### Constructor Parameters

* $tokenizer (Tokenizer) - tokenizer object (see below)
* $minDF (float) -  忽略具有严格低于给定阈值的采样频率的令牌。这个值在文献中也被称为截止值。(default 0)

```
use Phpml\FeatureExtraction\TokenCountVectorizer;
use Phpml\Tokenization\WhitespaceTokenizer;

$vectorizer = new TokenCountVectorizer(new WhitespaceTokenizer());
```

### Transformation

要转换文本样本的集合使用 `transform`方法。例：

```
$samples = [
    'Lorem ipsum dolor sit amet dolor',
    'Mauris placerat ipsum dolor',
    'Mauris diam eros fringilla diam',
];

$vectorizer = new TokenCountVectorizer(new WhitespaceTokenizer());
$vectorizer->transform($samples)
// return $vector = [
//    [0 => 1, 1 => 1, 2 => 2, 3 => 1, 4 => 1],
//    [5 => 1, 6 => 1, 1 => 1, 2 => 1],
//    [5 => 1, 7 => 2, 8 => 1, 9 => 1],
//];
        
```

### Vocabulary

您可以使用 `getVocabulary()` 方法提取词汇。例：

```
$vectorizer->getVocabulary();
// return $vocabulary = ['Lorem', 'ipsum', 'dolor', 'sit', 'amet', 'Mauris', 'placerat', 'diam', 'eros', 'fringilla'];
```

### Tokenizers

* WhitespaceTokenizer - 由空格选择令牌。
* WordTokenizer - 选择2个或更多字母数字字符的标记（标点符号被完全忽略，并始终被视为令牌分隔符）。