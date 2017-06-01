# 关于PHP-ML的安装使用教程@Skyfire-Lee

> **相关资料**：
>
> PHP-ML地址：https://github.com/php-ai/php-ml
>
> PHP-ML实例地址：https://github.com/php-ai/php-ml-examples
>
> PHP-ML英文文档地址：http://php-ml.readthedocs.io/en/latest/
>
> Composer地址：http://www.phpcomposer.com/

## 0x00 简介

**PHP-ML**是一个使用PHP编写的机器学习的框架。将算法，交叉验证，神经网络，预处理，特征提取，多在一库。

**PHP-ML**本身是利用**Composer**包管理工具进行维护。

**Composer**是一个PHP包依赖管理工具，类似于nodejs中的npm工具，是一个用来解决PHP库之间依赖关系的工具。

所以，若需要使用**PHP-ML**，就需要使用**Composer**工具来进行安装。



## 0x02 Composer安装

安装 Composer，你只需要下载 `composer.phar` 可执行文件。

```
curl -sS https://getcomposer.org/installer | php

```

详细请查看 [简介](http://docs.phpcomposer.com/00-intro.html) 章节。

要检查 Composer 是否正常工作，只需要通过 `php` 来执行 PHAR：

```
php composer.phar
```

这将返回给你一个可执行的命令列表。

> **注意：** 你也可以仅执行 `--check` 选项而无需下载 Composer。 要获取更多的信息请使用 `--help`。
>
> ```
> curl -sS https://getcomposer.org/installer | php -- --help
> ```



**注意**：信息来自http://docs.phpcomposer.com/01-basic-usage.html#Basic-usage，请务必先学习Composer工具，了解简单库依赖的安装与更新

## 0x02 实例部署

首先，使用Git将PHP-ML实例克隆至本地，地址为https://github.com/php-ai/php-ml-examples

```
skyfire@skyfire-pc:~/Software$ git clone https://github.com/php-ai/php-ml-examples.git
正克隆到 'php-ml-examples'...
remote: Counting objects: 52, done.
remote: Total 52 (delta 0), reused 0 (delta 0), pack-reused 51
展开对象中: 100% (52/52), 完成.
```

第二步，进入`php-ml-examples`文件夹，然后执行Composer工具进行安装

```
skyfire@skyfire-pc:~/Software$ cd php-ml-examples/
skyfire@skyfire-pc:~/Software/php-ml-examples$ composer install
Loading composer repositories with package information
Installing dependencies (including require-dev) from lock file
Package operations: 1 install, 0 updates, 0 removals
  - Installing php-ai/php-ml (dev-develop 52cd58a) Cloning 52cd58acb0 from cache
Generating autoload files
```

由上可知，该项目已经将`php-ai/php-ml`下载安装，可以发现目录中出现了`vendor`和`composer.lock`文件，其中`vendor`文件夹是用来存放库文件的文件夹，例如`php-ai/php-ml`。

最后，通过运行命令来执行`php-ml`的实例：

```
skyfire@skyfire-pc:~/Software/php-ml-examples$ php classification/languageDetection.php
Accuracy: 0.83333333333333
```

最后一行就是实例的执行结果，每次运行的结果是不同的，本人也不知道那个程序是干嘛的，好像是分析语言的。



## 0x03 结语

参照`composer.json`内容：

```
{
  "name": "php-ai/php-ml-examples",
  "type": "project",
  "description": "Examples of the use of PHP-ML library",
  "license": "MIT",
  "keywords": ["machine learning","pattern recognition","computational learning theory","artificial intelligence"],
  "homepage": "https://github.com/php-ai/php-ml-examples",
  "authors": [
    {
      "name": "Arkadiusz Kondas",
      "email": "arkadiusz.kondas@gmail.com"
    }
  ],
  "require": {
    "php-ai/php-ml": "dev-develop"
  }
}
```

可以得知当前的`php-ml`版本是`dev-develop`，建议将`dev-develop`改为`*`，在利用命令`composer update`来获取最新的版本。

> 最新版本包含一些新功能，例如神经网络等。