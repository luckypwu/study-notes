# MkDocs

For full documentation visit [mkdocs.org](https://www.mkdocs.org).

## Installation

```shell
pip install mkdocs -U -i https://pypi.tuna.tsinghua.edu.cn/simple
pip install "mkdocstrings[python]" -U -i https://pypi.tuna.tsinghua.edu.cn/simple
pip install mkdocs-material -U -i https://pypi.tuna.tsinghua.edu.cn/simple
```

## Commands

* `mkdocs new [dir-name]` - Create a new project.
* `mkdocs serve` - Start the live-reloading docs server.
* `mkdocs build` - Build the documentation site.
* `mkdocs -h` - Print help message and exit.

## Project layout

    mkdocs.yml    # The configuration file.
    docs/
        index.md  # The documentation homepage.
        ...       # Other markdown pages, images and other files.

### 上传文档到 GitHub Pages

mkdocs-material 一个很棒的特性是可以一键将代码部署到GIthub Pages上，并且通过GitHub Actions配置，Push 代码时自动更新文档。 假如你的GitHub 仓库地址是`https://github.com/user/repo`，那完成配置后你就可以在`https://user.github.io/repo` 网址查看你的mkdocs-material 文档了。

具体来说，假设你已经创建了一个Git 仓库，需要做下面的事情：

1. 将`mkdocs.yml` 和`docs` 目录提交到Git仓库

2. 增加GitHub Action 配置文件`.github/workflows/ci.yml`，写入下面的内容并提交到GitHub:

    ```yaml
    name: ci 
    on:
      push:
        branches:
          - master 
          - main
    permissions:
      contents: write
    jobs:
      deploy:
        runs-on: ubuntu-latest
        steps:
          - uses: actions/checkout@v3
          - uses: actions/setup-python@v4
            with:
              python-version: 3.x
          - run: echo "cache_id=$(date --utc '+%V')" >> $GITHUB_ENV 
          - uses: actions/cache@v3
            with:
              key: mkdocs-material-${{ env.cache_id }}
              path: .cache
              restore-keys: |
                mkdocs-material-
          - run: pip install mkdocs-material 
          - run: mkdocs gh-deploy --force
    ```

3. 在GitHub仓库的`Settings` -> `Pages` -> `Build and deployment` 部分，Source 选项选择"Deploy from a branch", Branch 选择`gh-pages`, folder选择`/(root)` 经过这个配置后，每次向`master` 或`main` 分支push代码，会自动更新`user.github.io/repo`下的文档。



【相关链接】

1. [用 Material for MkDocs 来生成专业的技术文档 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/630165427)
