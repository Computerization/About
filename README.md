# 关于 Computerization 世外信息化社

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
[![Build Status](https://travis-ci.com/Computerization/about.svg?branch=master)](https://travis-ci.com/Computerization/about)

**本项目的所有文档采用 [知识共享署名 4.0 国际许可协议](http://creativecommons.org/licenses/by/4.0/) 进行许可。**

这是一个基于 [`gitbook-cli`](https://www.npmjs.com/package/gitbook-cli) 的 GitHub Pages 静态网站项目。

这个项目中包含了对于世外信息化社的说明：我们是谁，我们做过什么项目，我们追求的是什么。

原文档位于 `master` branch 下。编译后的静态网站位于 `gh-pages` branch 下，并通过 GitHub Pages 部署在 [https://computerization.github.io/about/](https://computerization.github.io/about/)。


## 目录结构

### [`/SUMMARY.md`](/SUMMARY.md)

这个文件相当于 Table of Content，是显示在侧边栏中的内容。里面包含了各级文档标题，以及指向对应文档的路径

### `/About`

这个目录中包含了对于社团的基本说明：我们是谁，我们的哲学，以及对于我们活动内容的简介

### `/learning`

这个目录中包含了我们开展的一系列课程及说明

### `/SAM`

这个目录中是对于曾经的作业收发平台 SAM 以及其衍生作品的介绍。

## 如何编辑并发布更改

#### Git clone
```shell
git clone https://github.com/Computerization/about.git
cd about
```

#### 安装 `gitbook-cli`

你将需要先安装 [`npm`](https://www.npmjs.com/get-npm)，并通过 `npm` 安装 `gitbook-cli`

```shell
npm install -g gitbook-cli
gitbook install #install all plugins dependencies
```

#### 编辑文档  

**在编辑文档前，建议新建一个 branch 并提交 Pull Request**

```shell
git branch my-new-branch #please replace the branch name with something meaningful
```

**注意：所有文档均使用 Markdown 语言进行编写**

你可以自由地新建目录（文件夹）并在里面添加新的 `*.md` 文件，但是为了让新文件在网站上显示，你还需要在 `SUMMARY.md` 中增加指向新文件的条目

如果你已经安装了 `gitbook-cli`，那么你可以通过 `gitbook serve` 实时预览你的更改。

#### 保存更改

使用 git commit 保存更改并 push

```shell
git add .
git commit -m "some message"
git push
```

**如果你是在新的 branch 中进行编辑，那么你需要前往 [Pull Request 页面](https://github.com/Computerization/about/pulls) 提交PR**

#### 部署

本项目已经集成 [Travis Continuous Integration](https://travis-ci.com/Computerization/about)，因此无需手动编译与部属。

在新的编辑被 merge 到 `master` branch 后，Travis CI 会自动进行编译并部署到 `gh-pages` branch 下。

因此，我们建议对于所有编辑**新建 branch，并提交 Pull Request**。所有的 Pull Request 需要通过 Travis CI 的测试后才能 merge。

**我们强烈不建议手动编译与部署，但我们仍提供以下教程供参考：**

##### 手动编译
```shell
gitbook install #install all plugins dependencies
gitbook build
```

##### 手动部署
```shell
# checkout to the gh-pages branch and pull latest updates
git checkout gh-pages
git pull origin gh-pages --rebase

# copy the static site files into the current directory.
cp -R _book/* .

# add all files and commit
git add .
git commit -a -m "Update docs"

# push to the origin
git push origin gh-pages

# checkout back to the master branch
git checkout master
```
