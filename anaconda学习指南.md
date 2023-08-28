# anaconda安装及配置

先在[Free Download | Anaconda](https://www.anaconda.com/download)上下载windows版本的exe安装程序

## 源（channel）

每个频道都包含了一些软件包的发布版本，可以通过这些频道来获取并安装这些软件包。不同的频道可能包含不同的软件包或不同的版本，因此选择合适的频道可以帮助我们获取到我们需要的软件包，并且也可以提高软件包下载和安装的速度。在这里，这些频道都是针对Anaconda的，而且使用了清华大学镜像站提供的地址，因此可以更快地从这些镜像站获取软件包。

```shell
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/menpo/
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/bioconda/
conda config --add channels http://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/fastai/
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/msys2/ 
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/peterjc123/
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/pytorch/
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge/ 
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/ 
conda config --set show_channel_urls yes
```

- 添加安装源（channel）

```shell
conda config --add channels http://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/
```

- 查看安装源

```shell
conda config --show-sources
```

- 删除安装源

```shell
conda config --remove channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/menpo/
conda config --remove channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/bioconda/
conda config --remove channels http://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/fastai/
conda config --remove channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/msys2/ 
conda config --remove channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/peterjc123/
conda config --remove channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/pytorch/
conda config --remove channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge/ 
conda config --remove channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
conda config --remove channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/ 
```

# 管理环境

## conda env list列出已有环境

conda env list

## conda create建立新环境

conda create --name carla2 python=3.7

conda activate carla2

conda deactivate

## conda remove删除环境

conda remove --name carla-sampling --all

### 

# 管理包

### conda list查看所有已安装包

```shell
conda list
```

### conda list查看特定的已安装包的版本

```shell
conda list [package]
conda list numpy
```

### conda install安装包

```shell
conda install absl-py
conda install absl-py==0.9.0

conda search absl-py//查找能安装的版本

如需更换版本，不需要卸载原来的，直接安装新的，conda会自动删除原来的
The following packages will be DOWNGRADED:
  nodejs                       18.16.0-haa95532_0 --> 16.13.1-haa95532_0
```

# 疑难解答

## 激活环境时如果激活失败并显示以下信息

conda activate carla2
usage: conda-script.py [-h] [--no-plugins] [-V] COMMAND ...
conda-script.py: error: argument COMMAND: invalid choice: 'activate' (choose from 'clean', 'compare', 'config', 'create', 'info', 'init', 'install', 'list', 'notices', 'package', 'remove', 'uninstall', 'rename', 'run', 'search', 'update', 'upgrade', 'doctor', 'build', 'content-trust', 'inspect', 'token', 'debug', 'repo', 'render', 'index', 'metapackage', 'env', 'server', 'pack', 'develop', 'verify', 'skeleton', 'convert')

是因为base环境未激活，所以无法激活其他环境，先使用命令

`activate`

再激活环境

`conda activate carla2`

## 连接github.com的server超时

[解决fatal: unable to access ‘https://github.com/NVIDIA/apex.git/‘: Recv failure: Connection was reset_git_dd_Zing-华为开发者联盟HarmonyOS专区](https://huaweidevelopers.csdn.net/648c342c6bf8dd0412f506b3.html?dp_token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpZCI6MzMyNjczOSwiZXhwIjoxNjkzMjAxNTYyLCJpYXQiOjE2OTI1OTY3NjIsInVzZXJuYW1lIjoicXFfMzc0NjIyNDUifQ.FLdz7Rf_QXXBO53J3hGzH_xkX8KhI37Izmcw3Sz9irc)

1：确保VPN打开的情况下，打开系统设置->网络和Internet->代理。找到自己的代理IP，如下：

![](C:\Users\54690\AppData\Roaming\marktext\images\2023-08-21-13-52-20-image.png)

2：在git bash 中依次输入以下指令

```shell
git config --global http.proxy http://127.0.0.1:7890
git config --global git.proxy http://127.0.0.1:7890
git config --global --unset https.proxy
```

问题得到解决。

fatal: unable to access 'https://github.com/jingyue01/Cybersecurity/': HTTP/2 stream 1 was not closed cleanly before end of the underlying stream

https://zhuanlan.zhihu.com/p/393055486

## 问题描述

使用git的时候发现一直提示**HTTP/2 stream 1 was not closed cleanly before end of the underlying stream。**通过排查发现，是git默认使用的通信协议出现了问题，可以通过将默认通信协议修改为http/1.1来解决该问题。

## 解决方法

```text
git config --global http.version HTTP/1.1
```

# pip常用命令

查看下载源

pip config list
