# 自动吔咩

「吔咩」是一套 Telegram Sticker，我基于 GIMP 做了个自动化生成器。

你只需安装 yamie.scm，然后把所有文件扔到 `images` 目录下运行 `convert.sh` 即可。

## 选项添加

forked from ksqsf

将convert.sh改成deal.sh，使其支持命令行选项，如果不添加任何选项，则依旧使用默认参数。

-m [MODE]  the mode you use when processing.

-s [SOURCE]  the source image you use.

-e [TEMPLATE]   the xcf template you use.

-t [TARGET]  the target photo you want to restore.

-h --help   print this help menu.

```
# 对 GIMP 2.8 版本
cp yamie.scm ~/.gimp-2.8/scripts/

添加了frames.scm，与frames.xcf配套使用，效果是将图片嵌入相框

```

## 依赖
* GIMP 2.8+
* GIMP-WebP 插件

Arch Linux 用户可从 AUR 中安装 `gimp-webp` 获取 WebP 格式支持。

## 说明
1. WebP 插件无视 Non-interactive 参数。如需全自动转换，请将 convert.sh 中的 .webp 改为 .png 或其他格式，待转换完成后再用图片格式转换工具批量转换为 WebP。
2. 通过改变 YaMie.xcf 中的选区和 yamie.scm 中的相关代码，还能做出其他类似的功能。其实 YaMie.xcf 的主要功能是作为模板并提供不规则选区。
