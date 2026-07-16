# 栈长的博客

一个基于 [Jekyll](https://jekyllrb.com/) 的纯静态个人博客，托管在 GitHub Pages，白蓝简洁风格。文章分三类：**计算机安全 / 看过的影视作品 / 杂谈**。

线上地址：<https://singleghost2.github.io/>

---

## ✍️ 如何写一篇新文章（日常更新）

有两种方式，都是**在浏览器里完成、无需回到本地改代码**，写完保存后 GitHub Pages 会自动重新构建（约 1–3 分钟后生效）。

### 方式一：prose.io（推荐，像写文档一样）

1. 浏览器打开 **<https://prose.io/#singleghost2/singleghost2.github.io>**
2. 首次使用点 **Authorize** 用 GitHub 账号授权（只需一次）
3. 右上角 **New File** 新建文章 → 会自动出现表单：填**标题**、选**分类**、写**摘要**、写正文
4. 点 **Save** 保存即提交，稍等片刻线上就更新了

> 手机浏览器也能用同样的地址，随时随地发文。

### 方式二：GitHub 网页 / 手机 App 直接新建文件

1. 进入仓库的 `_posts/` 目录 → **Add file → Create new file**
2. 文件名格式必须是：`YYYY-MM-DD-标题.md`，例如 `2026-07-15-某内核漏洞分析.md`
3. 顶部粘贴下面的模板并填好，正文写在 `---` 之下，**Commit** 即可：

```markdown
---
title: "文章标题"
date: 2026-07-15
category: security
description: 一句话摘要，会显示在列表页。
---

正文从这里开始，用 Markdown 书写。
```

### 分类对照表（`category` 只能填这三个英文值之一）

| 想归到哪一类   | `category` 填 | 分类页地址   |
| -------------- | ------------- | ------------ |
| 计算机安全     | `security`    | `/security/` |
| 看过的影视作品 | `media`       | `/media/`    |
| 杂谈           | `misc`        | `/misc/`     |

### 插入图片

把图片放进 `assets/img/`（prose.io 在正文里插图会自动上传到这里），正文中引用：

```markdown
![说明文字](/assets/img/图片文件名.png)
```

---

## 🖥️ 本地预览（可选）

改样式/布局时可在本地实时预览。需要 Ruby 环境：

```bash
bundle install                 # 首次执行，安装依赖
bundle exec jekyll serve       # 启动本地服务器
```

然后浏览器打开 <http://localhost:4000/>。改动文件会自动重建刷新。

---

## 📁 目录结构

```
_config.yml        站点配置（标题、导航、分类映射、插件）
_layouts/          页面布局（default/home/post/category/page）
_includes/         可复用组件（head/header/footer/post-card）
_sass/             样式源码（白蓝调色板与各模块样式）
assets/css/        样式入口，assets/img/ 存放图片
categories/        三个分类的列表页
_posts/            所有文章（文件名 YYYY-MM-DD-标题.md）
about.md           关于页
_prose.yml         prose.io 编辑器配置
```

## 🎨 改配色 / 站点信息

- 配色、字体：`_sass/_variables.scss`
- 站点标题、描述、导航项、分类中文名：`_config.yml`

---

## 🚀 首次上线（一次性操作，在 GitHub 网页完成）

1. **把仓库改名为用户主页站点**：仓库 **Settings → General → Repository name**，改成 `singleghost2.github.io` → Rename。
2. **开启 Pages**：**Settings → Pages → Build and deployment**，Source 选 **Deploy from a branch**，分支选 **main**、目录 **/(root)**，Save。
3. 等待构建完成，访问 <https://singleghost2.github.io/> 即可。

> 因为只使用了 GitHub Pages 官方支持的插件（jekyll-feed / jekyll-seo-tag / jekyll-sitemap），GitHub 会自动构建，无需额外配置 Actions。
