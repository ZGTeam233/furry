---
title: Hexo 部署到 GitHub Pages 没样式
date: 2026-09-22 11:10:34
tags:
  - Hexo
  - 科技
  - web
categories:
  - 教程
---

## Hexo 部署到 GitHub Pages 没样式 (AI 生成)

对，这就是典型的 **GitHub Pages 构建延迟 + 浏览器缓存**。你改完 `root` 重新部署后，Pages 那边要重新构建，浏览器又缓存了旧的 404，等它俩都刷过来，就“自己好了”。

以后遇到类似情况，记住三步：

1. **部署完等 1～2 分钟**，别急着下结论
2. **无痕窗口 / Ctrl + F5** 验证，排除缓存
3. **F12 → Console / Network** 看有没有 404，比瞎猜快

顺手可以把这次的经验记一篇：

```powershell
hexo new "Hexo 部署到 GitHub Pages 没样式"
```

把「`url` + `root` 要配对」「项目站点 root 要带仓库名」「部署有延迟」「先查缓存」写进去，以后不用再翻聊天记录。

接下来可以搞的：

- 换主题（`theme: landscape` 改成别的，比如 `hexo-theme-butterfly`、`next`）
- 绑自定义域名
- 加 `hexo-generator-search`、评论系统（Twikoo / Waline）
- 给 `_config.yml` 顶部把 `title`、`author` 从默认的 `Hexo` / `John Doe` 改掉

有需要继续问。