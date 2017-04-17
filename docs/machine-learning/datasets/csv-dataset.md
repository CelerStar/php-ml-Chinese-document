# CsvDataset

从CSV文件加载数据的助手类。它扩展了 `ArrayDataset`.

### Constructors Parameters

* $filepath - (string) 文件路径
* $features - (int) 特征列数（从第一列开始），最后一列必须是一个标签
* $headingRow - (bool) define是文件有一个标题行（如果true第一行将被忽略）

```
$dataset = new CsvDataset('dataset.csv', 2, true);
```

See [ArrayDataset](array-dataset.md) for more information.
