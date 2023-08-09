# anaconda学习指南

## anaconda下载及安装

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

## 管理环境

conda create --name carla2 python=3.7

conda activate carla-sampling

conda deactivate

conda remove --name carla-sampling --all

### 查看所有已安装包

```shell
conda list
```

### 查看已安装包的版本

```shell
conda list [package]
conda list numpy
```

### 安装包

```shell
conda install absl-py
conda install absl-py==0.9.0

conda search absl-py//查找能安装的版本

如需更换版本，不需要卸载原来的，直接安装新的，conda会自动删除原来的
The following packages will be DOWNGRADED:
  nodejs                       18.16.0-haa95532_0 --> 16.13.1-haa95532_0
```

# conda建立新环境
