---
title: furry 博客
date: 2026-09-22 09:21:39
tags:
  - Hexo
  - 博客
  - furry
  - 福瑞
categories:
  - 教程
---

## 你好 Hexo

这是我的第一篇文章. 
让一个 *furry控* 写文章, 好奇怪啊. 
先这样吧

### 我咋做这个页面的

很简单, 
首先, 下载 **node**, 然后依次运行

```bash
npm install -g hexo-cli
hexo init furry
cd furry
pnpm install
hexo server
hexo new "furry 博客"
```

然后就有这个页面了

---

### 常用命令
```bash
hexo new "文章标题"      # 新建文章
hexo new draft "草稿"    # 新建草稿，在 source/_drafts
hexo publish "草稿"      # 把草稿发布成正式文章
hexo new page "about"    # 新建独立页面，如关于页
hexo server              # 本地预览
hexo clean               # 清理缓存和 public
hexo generate            # 生成静态文件到 public
hexo deploy              # 部署
```

简写：

```bash
hexo n "标题"
hexo s
hexo g
hexo d
```

---

### 写图片
最简单：把图片放到：

```text
source/images/example.png
```

文章里引用：

```markdown
![示例图片](/images/example.png)
```

也可以开启文章资源文件夹。在根目录 `_config.yml` 里：

```yaml
post_asset_folder: true
```

以后 `hexo new "文章"` 会同时生成一个同名文件夹，图片放进去，然后用：

```markdown
{% asset_img example.png 示例图片 %}
```

---

### 摘要、标签、分类
在正文里加：

```markdown
<!-- more -->
```

首页就只显示这行之前的内容。

标签和分类写在 Front-matter：

```yaml
tags:
  - Hexo
  - 教程
categories:
  - 博客搭建
```

主题会自动显示。

---

### 独立页面
比如做“关于”页：

```bash
hexo new page "about"
```

生成：

```text
source/about/index.md
```

编辑它，然后在主题配置里把 `about` 加到菜单。

---

### 注意
- 不要直接改 `public`，那是生成结果，`hexo clean` 后会没。
- 写文章只改 `source/_posts`。
- 修改后浏览器没变化，就刷新；还不行就：

```bash
hexo clean
hexo server
```

---

### 写完以后部署到 GitHub Pages
安装部署插件：

```bash
npm install hexo-deployer-git --save
```

编辑根目录 `_config.yml`：

```yaml
deploy:
  type: git
  repo: https://github.com/你的用户名/你的用户名.github.io.git
  branch: main
```

然后：

```bash
hexo clean
hexo generate
hexo deploy
```

GitHub 仓库 `Settings → Pages` 选择 `main` 分支、`/root` 目录即可。

总结：**`hexo new "标题"` → 编辑 `source/_posts/标题.md` → 刷新 `localhost:4000` 预览 → `hexo generate && hexo deploy` 发布。**