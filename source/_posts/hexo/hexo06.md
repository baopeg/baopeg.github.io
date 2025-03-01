---
title: "Hexo博客部署指南（六）—— GitHub Pages自动化部署"
date: 2025-02-28 11:38:00
categories: ["技术教程", "hexo"]
tags: ["Hexo", "GitHub Pages", "持续集成"]
description: "实现自动化云端部署,配置GitHub Actions实现提交自动部署"
---

# Hexo博客部署指南（六）—— GitHub Pages自动化部署
参考文章：
- [hexo，push你的新博客到Github](https://durant35.github.io/2016/01/22/hexo_push%E4%BD%A0%E7%9A%84%E6%96%B0%E5%8D%9A%E5%AE%A2%E5%88%B0Github/)
- [hexo+github搭建个人博客教程和各种坑记录](https://www.cnblogs.com/cuteerha/p/13150495.html)
- [使用Hexo搭建自己的博客：最佳推荐，该博主的Python教程，已有161k star](https://github.com/jackfrued/Python-100-Days/blob/master/%E7%95%AA%E5%A4%96%E7%AF%87/%E4%BD%BF%E7%94%A8Hexo%E6%90%AD%E5%BB%BA%E8%87%AA%E5%B7%B1%E7%9A%84%E5%8D%9A%E5%AE%A2.md)
## GitHub 仓库配置
1. 创建GitHub仓库：
   - 访问 [GitHub](https://github.com/new) 创建新仓库
   - 仓库名称必须为 `<username>.github.io` (替换为你的GitHub用户名,我这里已经创建了，无法在新建，用my_blog代替)
   - ![GitHub仓库创建](create_repository.png)
   - 选择public可见性
   - 勾选"Initialize this repository with a README"

2. 本地仓库初始化：
```bash terminal
git init
git remote add origin https://github.com/<your-username>/<your-repo>.git
```

3. 推送Hexo源码：
```bash terminal
git add .
git commit -m "初始化Hexo项目"
git push -u origin master
```

## 部署准备
1. 安装部署插件：
```bash package.json
npm install hexo-deployer-git --save
```

2. 配置站点文件：
```yaml _config.yml
deploy:
  type: git
  repo: https://github.com/<your-username>/<your-repo>.git
  branch: gh-pages  # 静态文件分支
  message: "站点更新: {{ now('YYYY-MM-DD HH:mm:ss') }}"
```

## 自动化部署流程
1. 生成并部署静态文件：
```bash terminal
hexo clean && hexo generate --deploy
```

2. 验证部署结果：
```bash terminal
git checkout gh-pages  # 切换到静态文件分支
ls  # 应看到生成的public目录内容
```

## 访问验证
部署完成后访问（首次生效约需5分钟）：
`https://<username>.github.io`

再次部署后访问：如果内容不更新，可能是github pages没有更新，
检查步骤：
1. 访问GitHub仓库，查看分支列表，确认`gh-pages`分支存在且为最新。
2. 查看settings，确认`GitHub Pages`的分支为`gh-pages`。并且检查更新时间时候是否最新。
![GitHub Pages设置](github_pages.png)
3. 如果未跟新，手动更新。步骤：github仓库-> acotins —> run workflow
![workflow](workflow.png)]
## GitHub Actions 配置（可选）
创建持续集成工作流：
```yaml .github/workflows/deploy.yml
name: Hexo Deploy

on:
  push:
    branches:
      - master

jobs:
  build-and-deploy:
    runs-on: ubuntu-latest
    steps:
    - name: Checkout source
      uses: actions/checkout@v3
      
    - name: Setup Node.js
      uses: actions/setup-node@v3
      with:
        node-version: 18.x

    - name: Install Dependencies
      run: |
        npm install hexo-cli -g
        npm install
```

## 分支策略建议
| 分支类型   | 内容说明               | 保护规则         |
|------------|------------------------|------------------|
| `master`   | Hexo源码（Markdown等） | 需要PR合并       |
| `gh-pages` | 生成的静态文件         | 仅允许CI自动更新 |