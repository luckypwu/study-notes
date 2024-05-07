# Python虚拟环境

## Conda

首先需要安装 Anaconda，点击清华大学开源镜像网站[链接](https://mirrors.tuna.tsinghua.edu.cn/anaconda/archive/)下载。

### conda配置

1. 配置清华镜像源，参考[Anaconda 镜像使用帮助 | 清华大学开源软件镜像站](https://mirrors.tuna.tsinghua.edu.cn/help/anaconda/).

    ```bash
    conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main 
    conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/r
    conda config --add https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/msys2
    conda config --set show_channel_urls yes
    ```

    

2. 配置默认线程数，参考[Configuring number of threads— conda 4.14.0 documentation](https://docs.conda.io/projects/conda/en/4.14.x/user-guide/configuration/use-condarc.html#configuring-number-of-threads)。

    ```bash
    conda config --set default_threads 4
    ```

### conda环境管理

```bash
# 查看系统中的所有环境
conda info -e
conda env list
# 创建环境
conda create -n py35 python=3.5 -y
# 激活环境
conda activate py35
# 退出环境
conda deactivate 
# 删除环境
conda remove -n py35 --all -y
```

### conda包管理

```bash
# 查看已经安装的packages
conda list
# 查看某个指定环境的已安装包
conda list -n py35
# 查找可用package信息
conda search numpy
# 在当前环境安装包
conda install numpy
# 安装package到指定的环境
conda install -n py35 numpy
# 删除package
conda remove -n py35 numpy
```



