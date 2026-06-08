# myblog — 零成本静态博客

一个基于 **Jekyll + GitHub Pages** 的个人博客，完全免费，无需域名、服务器或数据库。写完 Markdown，push 即发布。

## 快速开始

### 方式一：GitHub 网页端上传（最省事）

1. 在 GitHub 上新建一个空仓库，命名为 `myblog`。
2. 将本目录下的所有文件拖拽上传到仓库根目录。
3. 进入仓库 **Settings → Pages**。
4. `Source` 选择 **Deploy from a branch**，分支选 `main`，目录选 `/ (root)`，点 Save。
5. 等待约 1 分钟，页面顶部会显示 `Your site is live at https://你的用户名.github.io/myblog/`。

### 方式二：命令行（如果你装了 git）

```bash
git clone https://github.com/你的用户名/myblog.git
cd myblog
# 把本目录的所有文件复制进去
git add .
git commit -m "初始化博客"
git push origin main
```

然后同样在 Settings → Pages 中开启部署即可。

## 如果仓库名是 `username.github.io`

这种情况下 GitHub Pages 会自动把站点部署到根路径。你需要编辑 `_config.yml`，把这一行：

```yaml
baseurl: "/myblog"
```

改成：

```yaml
baseurl: ""
```

## 写新文章

在 `_posts/` 目录下新建一个 Markdown 文件，文件名格式：

```
YYYY-MM-DD-标题.md
```

例如：`2026-07-01-又写了一篇.md`

文件开头加上 Front Matter：

```yaml
---
layout: post
title: "你的文章标题"
date: 2026-07-01 10:00:00 +0800
---
```

保存后 push 到 GitHub，文章就自动上线了。

## 本地预览（可选）

如果想在 push 之前预览效果：

```bash
# 安装 Ruby + Bundler（一次性）
gem install bundler jekyll

# 在仓库根目录执行
jekyll serve

# 打开浏览器访问 http://localhost:4000/myblog/
```

## 自定义

- **站点名称和作者**：修改 `_config.yml` 对应字段。
- **颜色和字体**：编辑 `assets/css/style.scss`，修改 CSS 变量即可。
- **添加页面**：新建 Markdown 文件（如 `about.md`），加上 Front Matter `layout: default`。

## 许可

MIT License — 随意使用和修改。
