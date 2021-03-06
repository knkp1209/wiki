# 扩展安装

Swow 扩展安装提供了以下几种方法

## 编译安装

下载或者 clone 源代码后，在终端进入源码目录，执行下面的命令进行编译和安装

```shell
git clone git@github.com:swow/swow.git

cd swow
phpize
./configure
make
sudo make install
```

!> 编译成功后，不要忘记在 php.ini 中加入一行 `extension=swow.so` 来启用 Swow 扩展

## Composer

可以使用 Composer 下载源码

```shell
composer require swow/swow
```

下载完成后在 `vendor/bin` 目录中会有一个 `swow-builder` 的文件，我们可以使用此脚本文件来安装扩展

此脚本提供了4个参数，分别为`rebuild`, `show-log`, `debug`, `enable`，支持同时多个参数，示例如下

```shell
#编译扩展
php vendor/bin/swow-builder

#重新编译扩展
php vendor/bin/swow-builder --rebuild

#编译扩展时显示完整编译日志信息
php vendor/bin/swow-builder --show-log

#编译扩展并打开扩展的调试模式
php vendor/bin/swow-builder --debug

#编译扩展时增加一些编译参数
php vendor/bin/swow-builder --enable="--enable-debug"
```

!> 编译成功后，不要忘记在 php.ini 中加入一行 `extension=swow.so` 来启用 Swow 扩展

## 编译参数

* `--enable-debug`

打开调试模式