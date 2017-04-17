# Persistency

您可以保存经过培训的模型以备将来使用 通过将序列化估计器保存并恢复为文件而实现的请求的持续性。
### Example

```
use Phpml\Classification\KNearestNeighbors;
use Phpml\ModelManager;

$samples = [[1, 3], [1, 4], [2, 4], [3, 1], [4, 1], [4, 2]];
$labels = ['a', 'a', 'a', 'b', 'b', 'b'];

$classifier = new KNearestNeighbors();
$classifier->train($samples, $labels);

$filepath = '/path/to/store/the/model';
$modelManager = new ModelManager();
$modelManager->saveToFile($classifier, $filepath);

$restoredClassifier = $modelManager->restoreFromFile($filepath);
$restoredClassifier->predict([3, 2]);
// return 'b'
```
