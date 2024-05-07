# Git学习笔记

## Git使用SSH配置

1. **Github配置ssh key**

    **第一步：检查本地主机是否已经存在ssh key**

    ```bash
    ls ~/.ssh
    #看是否存在 id_rsa 和 id_rsa.pub文件，如果存在，说明已经有SSH Key
    ```

    **第二步：生成ssh key**

    如果不存在ssh key，使用如下命令生成

    ```bash
    ssh-keygen -t rsa -C "xxx@xxx.com"
    # 执行后一直回车即可
    ```

    **第三步：获取ssh key公钥内容（id_rsa.pub）**

    复制以下文件中的内容

    ```bash
    cat ~/.ssh/id_rsa.pub
    ```

    **第四步：Github账号上添加公钥**

    打开[github ssh key配置页面](https://github.com/settings/keys)，添加ssh key。

    **第五步：验证是否设置成功**

    ```bash
    ssh -T git@github.com
    ```

2. **Gitee配置ssh key**



## Git Bash下安装tree

- Windows
    1. 下载[Tree for Windows](http://gnuwin32.sourceforge.net/packages/tree.htm)，选择 Binaries 类型的 zip 包。
    2. 将下载的 zip文件（`tree-1.5.2.2-bin.zip` ）中 `bin/tree.exe` 文件复制到 Git Bash 安装目录（如：`C:\Program Files\Git\usr\bin`）下。

​	

**【相关链接】**

1. [Git Bash下安装使用tree（在windows）_git tree tools-CSDN博客](https://blog.csdn.net/qq_33154343/article/details/100064726)	

 

