>Tag: #conda包管理器 
---
>   目录
>- [[#很赞的conda的教程|很赞的conda的教程]]
>- [[#Conda介绍|Conda介绍]]
>- [[#安装Acaconda|安装Acaconda]]
>- [[#配置镜像|配置镜像]]
>- [[#Conda安装Pytorch]]|[[Conda安装Pytorch]]


![[attachments/Pasted image 20231018182952.png]]
##### 很赞的conda的教程

- [Anaconda使用教程一（新手友好） - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/348120084)
- [Conda 安装使用图文详解](http://t.csdnimg.cn/8Inwt)
- [Conda官方文档](https://conda.io/en/latest/)
##### Conda介绍
Conda是一个开源的软件包管理系统和环境管理系统，不仅适用于Python，还适用于其他多种语言，如R、Scala、Java、JavaScript、C/C++、FORTRAN等。它的核心功能主要包括包管理与环境管理。

此外，Conda经常被打包在Anaconda和Miniconda中，这是因为Anaconda是一个预先构建和配置好的软件发行版，包含了conda、特定版本的python以及众多的程序包和科学计算工具等。

使用Conda，你可以方便地创建和管理不同的环境。例如，你可以创建一个名为python34的环境，并指定Python版本为3.5（Conda会自动寻找3.5.x中的最新版本）。此外，你还可以激活某个特定的环境，以便在这个环境中安装和使用特定的软件包。
##### 安装Acaconda

Acaconda官网：[Free Download | Anaconda](https://www.anaconda.com/download)
清华源镜像：[Index of /anaconda/archive/ | 清华大学开源软件镜像站](https://mirrors.tuna.tsinghua.edu.cn/anaconda/archive/)

在清华源镜像下载好acaconda.sh文件之后，在命令行中`bash acaconda.sh`执行，中途可能有两个yes需要输入，走完流程即安装成功。
```shell
bash Anaconda3-2021.11-Linux-x86_64.sh
```

##### 配置镜像

Linux：`vim ~/.condarc`

Windows：文件在 `C:\Users\你的用户名\.condarc`

> 如果没有`.condarc`文件，可以先执行 
  `conda config --set show_channel_urls yes` 生成该文件
  
`.condarc`中的内容类似下面：
```text
channels:
  - defaults
show_channel_urls: true
default_channels:
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/r
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/msys2
custom_channels:
  conda-forge: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  pytorch: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud

```
[15 个 Anaconda 国内开源镜像站](http://t.csdnimg.cn/EQ1HO)
[命令行配置镜像地址](http://t.csdnimg.cn/3uVgJ)
命令行配置镜像地址如下格式：
```shell
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge/
#设置搜索时显示通道地址
conda config --set show_channel_urls yes
```
##### [[Conda安装Pytorch]]
