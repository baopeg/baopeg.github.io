---
title: "Hexo博客部署指南（一）—— Node.js与Git环境搭建"
date: 2025-02-28 08:36:05
categories: [ "技术教程","hexo" ]
tags: [ "Hexo", "环境搭建", "Node.js", "Git" ]
description: "从零开始配置Hexo运行环境,详细介绍Node.js和Git的安装配置过程，验证基础环境可用性"
---

# Hexo博客部署指南（一）—— Node.js与Git环境搭建

## 环境准备

1. 安装Node.js（建议v16+）,详细教程：[https://nodejs.org/zh-cn/download/](https://nodejs.org/zh-cn/download/)
   ```shell
   # 验证安装
   node -v
   npm -v
   ```
   > 注意：Node.js和npm安装完成后，需要重启电脑才能生效

![node,npm版本](node_npm_version.png)

2. 安装Git,详细教程：[https://git-scm.com/downloads](https://git-scm.com/downloads)
   ```shell
   git --version
   ```
   
![git版本](git_version.png)

## 初始化Hexo项目

````shell
npm install -g hexo-cli # 安装hexo
hexo init myblog # 初始化项目
cd myblog # 进入项目
npm install # 安装依赖
````

## 目录结构说明

```shell
myblog
├── _config.yml # 配置文件
├── .gitignore # git忽略文件
├── package.json # 项目依赖包
├── scaffolds # 模板文件
├── source # 源文件
├── themes # 主题文件
├── .deploy_git # 部署文件
```

## 本地服务启动

```shell
hexo clean # 清理缓存
hexo generate # 生成静态文件
hexo server # 启动本地服务
```

>所有命令需在项目目录下执行

访问[http://localhost:4000](http://localhost:4000)查看效果，按住Ctrl+C退出服务

## Git环境搭建
说明：本次部署使用GitHub Pages作为Hexo博客的部署平台，GitHub Pages支持使用Git进行部署，因此需要先配置Git环境。
1. 创建GitHub账号，并创建一个仓库，仓库名称为`<username>.github.io`，其中`<username>`为GitHub账号的用户名，例如`https://github.com/<username>.github.io`
2. 本地hexo项目根目录下执行以下命令，将本地hexo项目推送到GitHub仓库中，并指定分支为`main`，默认为`master`(也可以不指定)
3. 安装部署插件
```shell
git init
git add .
git commit -m "first commit"
git remote add origin https://github.com/<username>/<username>.github.io.git
git push -u origin main/master(不指定分支默认为master)

npm install hexo-deployer-git --save
```
**仅仅搭建环境，不做任何配置**
 


