# FilesDataset

从文件加载数据集的助手类。使用文件夹名称作为目标。它扩展了 `ArrayDataset`.

### Constructors Parameters

* $rootPath - (string)包含文件数据集的根文件夹的路径

```
use Phpml\Dataset\FilesDataset;

$dataset = new FilesDataset('path/to/data');
```

查看 [ArrayDataset](array-dataset.md)以获取更多信息。

### Example

文件结构：

```
data
    business
        001.txt
        002.txt
        ...
    entertainment
        001.txt
        002.txt
        ...
    politics
        001.txt
        002.txt
        ...
    sport
        001.txt
        002.txt
        ...
    tech
        001.txt
        002.txt
        ...
```

加载文件数据 `FilesDataset`: 

```
use Phpml\Dataset\FilesDataset;

$dataset = new FilesDataset('path/to/data');

$dataset->getSamples()[0][0]  // content from file path/to/data/business/001.txt
$dataset->getTargets()[0]     // business

$dataset->getSamples()[40][0] // content from file path/to/data/tech/001.txt
$dataset->getTargets()[0]     // tech
```
