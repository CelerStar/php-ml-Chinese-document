# PHP-ML——机器学习PHP库

[![Minimum PHP Version](https://img.shields.io/badge/php-%3E%3D%207.0-8892BF.svg)](https://php.net/)
[![Latest Stable Version](https://img.shields.io/packagist/v/php-ai/php-ml.svg)](https://packagist.org/packages/php-ai/php-ml)
[![Build Status](https://scrutinizer-ci.com/g/php-ai/php-ml/badges/build.png?b=develop)](https://scrutinizer-ci.com/g/php-ai/php-ml/build-status/develop)
[![Documentation Status](https://readthedocs.org/projects/php-ml/badge/?version=develop)](http://php-ml.readthedocs.org/en/develop/?badge=develop)
[![Total Downloads](https://poser.pugx.org/php-ai/php-ml/downloads.svg)](https://packagist.org/packages/php-ai/php-ml)
[![License](https://poser.pugx.org/php-ai/php-ml/license.svg)](https://packagist.org/packages/php-ai/php-ml)
[![Scrutinizer Code Quality](https://scrutinizer-ci.com/g/php-ai/php-ml/badges/quality-score.png?b=develop)](https://scrutinizer-ci.com/g/php-ai/php-ml/?branch=develop)

#### 本文档由 赛灵开源技术研发社区 维护
#### 参与汉化项目地址
#### https://github.com/CelerStar/php-ml-Chinese-document

![PHP-ML - Machine Learning library for PHP](assets/php-ml-logo.png)

使用PHP语言构建的新的机器学习方法。包括相关算法,交叉验证、预处理、特征提取和更多的机器学习的函数库。

PHP-ML 需要 PHP >= 7.0.

简单的例子分类:
```php
use Phpml\Classification\KNearestNeighbors;

$samples = [[1, 3], [1, 4], [2, 4], [3, 1], [4, 1], [4, 2]];
$labels = ['a', 'a', 'a', 'b', 'b', 'b'];

$classifier = new KNearestNeighbors();
$classifier->train($samples, $labels);

$classifier->predict([3, 2]); 
// return 'b'
```

## 文档

如何使用 PHP-ML 请阅读以下 [文档](http://php-ml.readthedocs.org/).

## 安装

目前这个库是在发展的过程中,但你可以自行安装它

```
composer require php-ai/php-ml
```

## 示例

示例脚本放在一个单独的存储库 [php-ai/php-ml-examples](https://github.com/php-ai/php-ml-examples).

## 特征

* 关联性规则学习
    * [Apriori](machine-learning/association/apriori/)
* 分类
    * [SVC](machine-learning/classification/svc/)
    * [k-Nearest Neighbors](machine-learning/classification/k-nearest-neighbors/)
    * [Naive Bayes](machine-learning/classification/naive-bayes/)
* 回归
    * [Least Squares](machine-learning/regression/least-squares/)
    * [SVR](machine-learning/regression/svr/)
* 聚类
    * [k-Means](machine-learning/clustering/k-means/)
    * [DBSCAN](machine-learning/clustering/dbscan/)
* 指标
    * [Accuracy](machine-learning/metric/accuracy/)
    * [Confusion Matrix](machine-learning/metric/confusion-matrix/)
    * [Classification Report](machine-learning/metric/classification-report/)
* 工作流
    * [Pipeline](machine-learning/workflow/pipeline)
* 神经网络
    * [Multilayer Perceptron](machine-learning/neural-network/multilayer-perceptron/)
    * [Backpropagation training](machine-learning/neural-network/backpropagation/)
* 交叉验证
    * [Random Split](machine-learning/cross-validation/random-split/)
    * [Stratified Random Split](machine-learning/cross-validation/stratified-random-split/)
* 预处理
    * [Normalization](machine-learning/preprocessing/normalization/)
    * [Imputation missing values](machine-learning/preprocessing/imputation-missing-values/)
* 特征提取
    * [Token Count Vectorizer](machine-learning/feature-extraction/token-count-vectorizer/)
    * [Tf-idf Transformer](machine-learning/feature-extraction/tf-idf-transformer/)
* 数据集
    * [Array](machine-learning/datasets/array-dataset/)
    * [CSV](machine-learning/datasets/csv-dataset/)
    * [Files](machine-learning/datasets/files-dataset/)
    * Ready to use:
        * [Iris](machine-learning/datasets/demo/iris/)
        * [Wine](machine-learning/datasets/demo/wine/)
        * [Glass](machine-learning/datasets/demo/glass/)
* 模型管理
    * [Persistency](machine-learning/model-manager/persistency/)
* 数学
    * [Distance](math/distance/)
    * [Matrix](math/matrix/)
    * [Set](math/set/)
    * [Statistic](math/statistic/)
    

## 贡献

- 问题追踪: github.com/php-ai/php-ml/issues
- 源代码: github.com/php-ai/php-ml

你可以找到更多关于贡献 [CONTRIBUTING.md](CONTRIBUTING.md).

## 许可证

PHP-ML MIT许可下发布。 有关详细信息,请参阅捆绑许可证文件。

## 作者

Arkadiusz Kondas (@ArkadiuszKondas)
