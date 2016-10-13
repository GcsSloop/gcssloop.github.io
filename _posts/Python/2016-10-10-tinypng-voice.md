---
layout: post
category: Python
title: 让脚本说话"厉害了我的哥"
tags: GcsSloop, python
keywords: GcsSloop, python, tinypng
excerpt: 让python脚本开始说话。前段时间发现 Mac 上一个有趣的方法 say 可以让系统说话。于是给我经常用的图片压缩脚本升了一下级，可以语音提示当前信息，本次升级加了安全判断，并不会影响其它平台用户的正常使用。
---

前段时间发现 Mac 上一个有趣的方法可以让系统说话。例如在终端输入：

```shell
say "厉害了我的哥"
```

![](https://ws3.sinaimg.cn/large/cf673337jw1f8mjw9h099j204g04gwed)

于是把我自己经常使用的图片压缩脚本升了一下级，**人工**(智能)**语音提示，开启装逼新时代!**

>本次升级进行了平台安全判断，不会影响其它平台用户的正常使用。  
>在 Mac 上，它说话同时输出信息，在其他平台上只会输出信息。

![](https://ws3.sinaimg.cn/large/cf673337jw1f8mks1rzhqj20fu0a675e)

语音提示默认开启，可以关闭语音提示，将源码中`voice`设置为 False 即关闭语音提示。

```python
voice = False 	# 是否语音提示
```

想要调教输出内容的自己进源文件修改吧，代码量不到一百行，短小精悍，纯种 Python，优雅简洁。相信对大家来说，调教一下也不是什么难事。

[**点击此处下载脚本(右键 -> 另存为)**][tingpng-script]{:target="_blank"}

## 使用方法

> **注意：这是我的图片压缩脚本使用方法，不需要的可以关闭了。**

### 一.配置环境

**Python:** 保证电脑中存在 Python 环境，(如果是Mac，则自带的有Python环境)。

**Tinify:** 导入Tinify
```
  pip install --upgrade tinify
```

### 二.申请 API key

[点击此处申请 API key][tinypng-api]{:target="_blank"}

>
>一个 key 每个月可以免费压缩500张图片，可以申请多个 key。

### 三.配置脚本并运行

[**点击此处下载脚本(右键 -> 另存为)**][tingpng-script]{:target="_blank"}

下载完该脚本后，你需要简单编辑一下该脚本，将申请到到API key 填写进去。

```
tinify.key = "你申请到的API key"
```

之后你可以将该脚本放入到需要压缩的图片的文件夹下，然后在命令行(终端)中进入到该文件夹，执行如下命令即可:

```
python tinypng.py
```

生成的文件会存入当前目录下一个名为tiny的文件夹中。

**运行示例及大小对比(有图有真相):**

![](http://ww3.sinaimg.cn/large/005Xtdi2jw1f4mdtld2r9j30rs0hctcc.jpg)

![](http://ww2.sinaimg.cn/large/005Xtdi2jw1f4mdy2e8zjj30rs0hcwir.jpg)

### 四.支持参数

在 v1.0.1 版本中进行了参数支持，详情见下表:

|  参数  | 参数类型 | 摘要                | 示例                                      |
| :--: | ---- | ----------------- | --------------------------------------- |
|  无参  |      | 压缩当前文件夹下所有图片文件    | `tinypng.py`                            |
| `－f` | 图像文件 | 压缩指定的单个文件         | `tinypng.py -f /User/GcsSloop/demo.jpg` |
| `－d` | 文件夹  | 压缩指定文件夹下所有图片文件    | `tinypng.py -d /User/GcsSloop/DemoDir`  |
| `-w` | 整型数字 | 压缩后图片的宽度，不指定则宽度不变 | `tinypng.py -w 300`                     |

**参数优先级:**
```
  －f > －d > 无参
```
如果指定了 `－f` 则只会压缩指定文件，即使后续跟了 `－d` 也不会压缩指定的文件夹

```
 －w 无冲突，均可使用
```

`－w` 用于指定压缩后图片的宽度(width)高度自适应缩放，所以均可使用，(选项没有先后顺序)示例如下:

```
tinypng.py －w 300                              // 压缩当前目录所有图片文件，压缩后文件跨度为300

tinypng.py －w 300 -f /User/GcsSloop/demo.jpg   // 指定压缩一个文件，压缩后文件宽度为300
```

### 五.辅助优化

这一步不是必要的步骤，只是帮助你优化一些内容:

**任意位置启动(适用于 Linux 和 OS X 平台):**

如果你觉得每次都需要复制 `tinypng.py` 文件到需要压缩到目录太麻烦， 可以将该脚本存储到一个文件夹中， 之后将该文件夹添加进环境变量，就能在任意位置执行该脚本了,(仅适用于 Linux 和 OS X 平台)
使用命令直接是文件名，前面无需加python,如:
```
tinypng.py
```

如果使用直接使用文件名无法执行，则说明文件没有可执行权限，使用如下命令添加可执行权限:
```
chmod +x tinypng.py
```

[Mac 配置环境变量](https://github.com/GcsSloop/MacDeveloper/blob/master/Skill/Path.md){:target="_blank"}


**从当前目录启动(适用于 OS X 平台):**

如果从命令行中进入到某个目录比较麻烦，所以在 Mac 上你可以使用 XtraFinder 插件来给你的右键添加一个从当前目录启动选项，直接在当前目录下启动终端，添加方式在 XtraFinder 到偏好设置里面。

当然了，你也可以直接用 `tinypng.py -d 目录` 的形式直接指定压缩某个文件夹下的所有图片文件，非图片文件不会受到影响。

[点击这里查看Finder增强插件到安装方法](https://github.com/GcsSloop/MacDeveloper/blob/master/Tools/XtraFinder.md){:target="_blank"}

![](http://ww3.sinaimg.cn/large/005Xtdi2gw1f4kl9j34vij30rs0hcabg.jpg)

[**更多关于脚本的详情戳这里**](https://github.com/GcsSloop/MacDeveloper/blob/master/PythonProject/TinyPng/README.md){:target="_blank"}  
[**Tinypng官网**][tinypng]{:target="_blank"}

## About

> 据说关注作者微博，不仅能第一时间收到新文章发布信息，还能变帅哦!

### 作者微博: [@GcsSloop](http://weibo.com/GcsSloop){:target="_blank"}

<a href="http://www.gcssloop.com/info/about/" target="_blank"> <img src="http://ww4.sinaimg.cn/large/005Xtdi2gw1f1qn89ihu3j315o0dwwjc.jpg"  width="300" style="display:inline;"/> </a>


[tinypng]: https://tinypng.com/
[tinypng-api]: https://tinypng.com/developers
[tingpng-script]: https://raw.githubusercontent.com/GcsSloop/MacDeveloper/master/PythonProject/TinyPng/tinypng.py