---
title: "Hexo博客部署指南（五）—— 文章写作与静态生成"
date: 2025-02-28 10:22:31
categories: ["技术教程","hexo"]
tags: ["Hexo", "Markdown写作", "静态生成"]
description: "从写作到生成的完整流程,详解文章创建、Front-matter配置和静态文件生成"
---

# Hexo博客部署指南（五）—— 文章写作与静态生成

## 一、创建新文章
```bash [终端]
hexo new "文章标题"
```
- 默认在`source/_posts`目录生成Markdown文件
- 使用`hexo new draft "标题"`创建草稿
- 发布草稿：`hexo publish "标题"`

## 二、Front-matter 配置
```yaml [示例文章.md]
---
title: "示例文章"
date: 2025-03-01 14:00:00
categories:
  - 技术教程
  - 前端开发
tags: 
  - Hexo
  - Node.js
updated: 2025-03-02 09:00:00
comments: true
toc: true
mathjax: false
---
```

| 字段       | 说明                          | 必填 |
|------------|-------------------------------|------|
| title      | 文章标题                      | 是   |
| date       | 创建时间（ISO 8601格式）      | 是   |
| categories | 分类（最多两级）              | 否   |
| tags       | 标签（多个用数组或逗号分隔）  | 否   |
| updated    | 最后更新时间                  | 否   |

## 三、Markdown写作规范

```markdown [写作示例]
## 二级标题
### 三级标题

- 列表项
- [x] 任务列表
- [ ] 未完成任务

`行内代码`
\```python [demo.py]  # 这里的'\' 是转义字符，用于转义反引号，防止Markdown解析器将其视为代码块，
导致语法错误，无意义，书写是不需要，下同。
print("代码块示例")
\ ```

[链接文字](https://example.com)

![图片描述](image.jpg)   
```
如果显示图片插入错误，请检查图片路径是否正确。改错参考[错误解决](https://blog.csdn.net/m0_43401436/article/details/107191688)

## 四、生成与部署
```bash [终端命令]
# 生成静态文件

hexo clean # 清除缓存

hexo generate # 生成并部署

hexo server # 本地预览（默认http://localhost:4000）

```

## 五、高级技巧
1. **自定义模板**：
   在`scaffolds`目录创建自定义模板
2. **资源文件夹**：
   在Front-matter添加`resource: true`启用独立资源目录
3. **文章摘要**：
   使用`<!-- more -->`分隔摘要和正文

## 六、常见问题
1. **图片路径错误**：
   - 使用绝对路径`/images/example.jpg`
   - 启用`post_asset_folder`插件
2. **Front-matter格式错误**：
   - 确保冒号后保留空格，英文冒号和中文冒号不能混用
   - 正确使用缩进
3. **生成后样式丢失**：
   - 清除缓存：`hexo clean`
   - 重新生成：`hexo g --force`