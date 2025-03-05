---
title: "Hexo博客部署指南（二）—— 项目初始化与目录解析"
date: <%= date(page.date) %>
updated: <%= date(Date.now()) %> 
categories: [ "技术教程","hexo" ]
tags: [ "Hexo", "项目初始化", "目录结构" ]
description: "创建你的第一个Hexo项目,通过hexo init命令初始化项目，解析核心目录结构"
cover: /img/hexo02_cover.png
---

# Hexo博客部署指南（二）—— 项目初始化与目录解析

内容与上一章 Hexo博客部署指南（一）—— 安装Hexo，会有所重合，这里主要讲解项目初始化与目录解析。

## 项目初始化

### 1. 创建项目目录
```bash
mkdir my-hexo-blog && cd my-hexo-blog
```

### 2. 初始化Hexo项目
```bash
hexo init
```
该命令会自动：
1. 下载核心依赖包
2. 创建基础目录结构
3. 安装默认主题landscape

### 3. 安装依赖包
```bash
npm install
```

## 目录结构解析
项目目录结构如下：
```bash
my-hexo-blog/ 
├── scaffolds/ # 模板文件夹 
├── source/ # 资源文件夹 
│ └── _posts/ # 文章存放目录 
├── themes/ # 主题文件夹 
├── public/ # 生成的静态文件（自动生成） 
├── node_modules/ # 依赖模块（自动生成） 
├── _config.yml # 全局配置文件 
└── package.json # 项目依赖配置
```

### 关键文件说明

```yaml _config.yml
# 网站基本信息配置
title: Hexo技术博客
subtitle: 记录开发点滴
description: 一个前端开发者的技术博客
keywords: Hexo,JavaScript,Web开发
author: 开发者
language: zh-CN



