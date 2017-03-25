# K-means clustering

K-Means算法通过尝试分离n个相等方差组的样本来聚集数据，从而将称为惯性或簇内和平方的标准最小化。该算法需要指定簇的数量。

### Constructor Parameters

* $clustersNumber - 要查找的群集数
* $initialization - 初始化方法，默认kmeans ++（见下文）

```
$kmeans = new KMeans(2);
$kmeans = new KMeans(4, KMeans::INIT_RANDOM);
```

### Clustering

要将样本分成簇，只需使用 `cluster` 方法即可。它返回 `array` 带有样本的集群。

```
$samples = [[1, 1], [8, 7], [1, 2], [7, 8], [2, 1], [8, 9]];

$kmeans = new KMeans(2);
$kmeans->cluster($samples);
// return [0=>[[1, 1], ...], 1=>[[8, 7], ...]] 
```

### Initialization methods

#### kmeans++ (default)

K-means ++方法以智能方式选择k-均值聚类的初始聚类中心，以加速收敛。它使用DASV播种方法包括为群集找到良好的初始质心。
#### random

随机初始化方法选择完全随机的中心。它获得空间边界，以避免将集群中心与样本数据相距太远。
