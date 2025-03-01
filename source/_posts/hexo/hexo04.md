---
title: "Hexo博客部署指南（四）—— 主题安装与个性化"
date: 2025-02-28 10:10:31
categories: ["技术教程","hexo"]
tags: ["Hexo", "主题配置", "Butterfly主题"]
subtitle: "打造个性化博客界面"
summary: "以Butterfly主题为例演示主题安装与基础配置"
---
# Hexo博客部署指南（四）—— 主题安装与个性化
本篇将介绍如何安装主题，以及如何对主题进行简单个配置，之后将以Butterfly主题为系列做一个教程。

## 一、主题安装

```bash blog根目录
# 进入主题目录
cd themes/
# 克隆Butterfly主题仓库
git clone -b master https://github.com/jerryc127/hexo-theme-butterfly.git butterfly
```

## 二、启用主题

修改博客根目录的`_config.yml`：

```yaml _config.yml
# 将主题设置为butterfly
theme: butterfly
```

## 三、基础配置

### 1. 主题配置文件
建议创建`_config.butterfly.yml`进行配置（复制原主题配置）：

```bash blog根目录
cp themes/butterfly/_config.yml _config.butterfly.yml
```
手动添加：在更目录中创建`_config.butterfly.yml`，并复制`themes/butterfly/_config.yml`的内容。

### 2. 基础个性化设置
修改`_config.butterfly.yml`：

```yaml _config.butterfly.yml
# 网站图标
favicon: /img/favicon.png

# 导航菜单
menu:
  首页: / || fas fa-home
  归档: /archives/ || fas fa-archive

# 社交链接
social:
  GitHub: https://github.com/yourname || fab fa-github
  邮箱: mailto:your@email.com || fas fa-envelope

# 主题颜色
theme_color:
  enable: true
  main: "#49B1F5"
```

## 四、应用配置
修改完成后执行：

```bash blog根目录
hexo clean && hexo g && hexo s
```

后续将推出Butterfly主题深度配置教程，涵盖以下内容：
1. 页面样式定制
2. 第三方服务集成
3. 高级动画效果配置
4. 插件系统使用技巧