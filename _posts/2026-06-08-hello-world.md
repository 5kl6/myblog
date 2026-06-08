---
layout: post
title: "你好，世界——我的零成本静态博客"
date: 2026-06-08 15:30:00 +0800
categories: 随笔
excerpt: 用 Jekyll + GitHub Pages 搭建一个完全免费的静态博客，以及为什么你不需要数据库、服务器和域名也能开始写字。
---
这大概是我第 N 次搭建博客了。WordPress、Hugo、Hexo、Notion + 中转服务……每一种都踩过一遍。这次不一样——目标很明确：**零成本、零维护、纯静态**。

## 为什么选这个方案

其实 Java 里面根本没有指针这个概念，Java 是自己用自己的。我们用 Jekyll 是因为：

- **GitHub Pages 原生支持**：push 即发布，不需要配 CI。
- **Markdown 写作**：不绑后台编辑器，任何地方都能写。
- **完全免费**：没有域名费用（用 `username.github.io` 子域名）、没有托管费、没有数据库。

## 目录结构一览

项目根目录放的是这几个文件：

```
myblog/
├── _config.yml          # Jekyll 配置
├── index.md             # 首页
├── _layouts/
│   ├── default.html     # 全局布局
│   └── post.html        # 文章布局
├── assets/
│   └── css/
│       └── style.scss   # 样式表
├── _posts/
│   └── 2026-06-08-hello-world.md   # 示例文章
└── README.md            # 说明文档
```

整个仓库不超过 10 个文件，清晰到一眼看完。

## 一点 CSS 代码

行内代码是这么写的：

```css
.post-content {
  font-size: 1.05rem;
  line-height: 1.85;
  color: var(--color-text);
}
```

而一段 Python 长这样：

```python
def greet(name: str) -> str:
    """简单打个招呼。"""
    return f"你好，{name}！欢迎来到我的博客。"

if __name__ == "__main__":
    print(greet("世界"))
```

## 写作工具链

日常写文章的流程也很简单：

| 环节 | 工具 | 说明 |
|------|------|------|
| 写作 | VS Code / Typora | Markdown 即时预览 |
| 图片 | 本地截图 | 放到仓库 `images/` 目录 |
| 发布 | `git push` | 或 GitHub 网页直接上传 |

> **一个提醒**：图片文件不要太大。每张控制在 200KB 以内，阅读体验会好很多。如果需要压缩，`squoosh.app` 是个不错的选择——纯浏览器端，不上传任何东西。

## 下一步

1. 修改 `_config.yml` 里的站点名和作者名。
2. 在 `_posts/` 目录下新建 Markdown 文件，命名格式 `YYYY-MM-DD-标题.md`。
3. Push 到 GitHub，等几秒钟刷新页面——新文章就在线了。

没有数据库备份、没有服务器宕机、没有 SSL 证书过期。这些东西 GitHub 都替你做了。

写过这么多博客工具之后，我越来越相信一个道理：**工具越轻，写得越多。** 你不需要一个花哨的 CMS 来开始——一段文字、一个 Markdown 文件、一次 git push，就够了。

---

*如果你也在找零成本的写作方案，不妨试试这套——它已经在这里等着你了。*
