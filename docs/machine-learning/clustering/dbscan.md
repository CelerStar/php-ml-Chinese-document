# DBSCAN clustering

它是一种基于密度的聚类算法：给定一些空间中的一组点，将聚集在一起的点（多个邻近邻域的点）组合在一起，标记为低密度区域（最接近的区域）的离群点邻居离太远）。DBSCAN是最常见的聚类算法之一，也是科学文献中最引用的。 （来源：维基百科）

### Constructor Parameters

* $epsilon - 两个样本之间的最大距离被认为在同一个识别区
* $minSamples - 要被视为核心点的点的邻域中的样本数（这包括点本身）
* $distanceMetric - 距离对象，默认欧几里德距离 (查看 [distance documentation](../../math/distance.md))

```
$dbscan = new DBSCAN($epsilon = 2, $minSamples = 3);
$dbscan = new DBSCAN($epsilon = 2, $minSamples = 3, new Minkowski($lambda=4));
```

### Clustering

要将样本分成簇，只需使用 `cluster` 方法即可。它返回 `array` 带有样本的集群。

```
$samples = [[1, 1], [8, 7], [1, 2], [7, 8], [2, 1], [8, 9]];

$dbscan = new DBSCAN($epsilon = 2, $minSamples = 3);
$dbscan->cluster($samples);
// return [0=>[[1, 1], ...], 1=>[[8, 7], ...]] 
```
