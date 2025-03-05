---
title: "Hexo博客部署指南（三）—— _config.yml配置详解"
date: <%= date(page.date) %>
updated: <%= date(Date.now()) %> 
categories: ["技术教程","hexo"]
tags: ["Hexo", "配置优化", "YAML语法"]
description: "全局配置文件深度解析,逐步讲解站点标题、作者信息、URL格式等基础配置项"
cover: /img/hexo03_cover.png
---

# Hexo博客部署指南（三）—— _config.yml配置详解

---
title: "Hexo博客部署指南（三）—— _config.yml配置详解"
date: 2025-02-28 09:52:26
categories: ["技术教程"]
tags: ["Hexo", "配置优化", "YAML语法"]
subtitle: "全局配置文件深度解析"
summary: "逐步讲解站点标题、作者信息、URL格式等基础配置项"
---

# Hexo博客部署指南（三）—— _config.yml配置详解

## 配置文件概述
`_config.yml`是Hexo的核心配置文件，采用[YAML语法](https://yaml.org/)编写。文件包含：

1. 站点基本信息配置
2. 目录结构配置
3. URL格式配置
4. 文章元数据配置
5. 插件扩展配置

## 基础配置详解

### 站点设置（Site）
```yaml _config.yml
# 网站基础信息
title: 技术漫谈                  # 网站标题
subtitle: 探索编程之美            # 网站副标题
description: 技术博客与开发笔记    # 网站描述（SEO重要字段）
keywords: 编程,Web开发,人工智能    # 网站关键词
author: 张伟                     # 作者姓名
language: zh-CN                  # 网站语言
timezone: Asia/Shanghai          # 时区设置
```

### URL格式配置
```yaml _config.yml
# 永久链接格式
url: https://yourdomain.com      # 网站域名
root: /                          # 网站根路径
permalink: :year/:month/:title/  # 文章永久链接格式
permalink_defaults:             
  lang: zh-CN                    # 默认语言参数
```

### 目录结构配置
```yaml _config.yml
# 路径自定义（建议保持默认）
source_dir: source              # 源文件目录
public_dir: public              # 生成文件目录
tag_dir: tags                    # 标签页目录
archive_dir: archives            # 归档目录
category_dir: categories         # 分类目录
```

## 高级配置项

### 文章元数据
```yaml _config.yml
# 文章默认设置
default_layout: post             # 默认布局类型
auto_spacing: false              # 中英文自动空格
titlecase: false                 # 标题首字母大写
external_link:
  enable: true                   # 外链新窗口打开
  exclude: []                    # 例外域名
filename_case: 0                 # 文件名大小写转换（0-不转换）
```

### 分页设置
```yaml _config.yml
# 分页配置
index_generator:
  path: ''                       # 首页路径
  per_page: 10                   # 每页文章数
  order_by: -date                # 排序方式（-表示倒序）
```

## 配置注意事项
1. **缩进敏感**：必须使用空格缩进，禁止使用Tab
2. **保留字段**：`source`、`public`等目录名不建议修改
3. **环境变量覆盖**：支持通过`hexo server --config config.yml`指定配置文件
4. **主题配置**：主题相关配置建议在主题目录的`_config.yml`中修改
5. **重启生效**：修改配置后需要重启服务器（`hexo clean && hexo server`）

## 配置验证技巧
使用[YAML Lint](https://yamllint.com/)在线工具验证语法，或执行：
```bash
hexo g --debug  # 生成时显示调试信息
```

> 完整配置参考：[Hexo官方文档](https://hexo.io/zh-cn/docs/configuration)