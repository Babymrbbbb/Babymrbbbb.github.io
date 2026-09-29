# GitHub Pages 部署指南

## 方案一：直接推送到 GitHub Pages（推荐）

```bash
cd C:\Users\Administrator\.workbuddy\2026-09-29-10-26-32\portfolio\website

# 初始化 git
git init
git add .
git commit -m "init: portfolio website"

# 创建 GitHub 仓库（在 GitHub 网页上创建，仓库名必须是 Babymrbbbb.github.io）
# 注意：仓库名必须是 {你的用户名}.github.io，这样 GitHub Pages 才能自动部署

# 推送到 GitHub
git remote add origin https://github.com/Babymrbbbb/Babymrbbbb.github.io.git
git push -u origin main

# 在 GitHub 仓库设置里开启 GitHub Pages
# Settings → Pages → Source: Deploy from a branch → Branch: main
```

部署完成后，访问 `https://Babymrbbbb.github.io` 即可看到网站。

---

## 方案二：用已有的 GitHub 仓库

如果你不想新建 `Babymrbbbb.github.io` 仓库，可以把网站放在任意仓库的 `/docs` 或 `/gh-pages` 目录下：

```bash
cd C:\Users\Administrator\.workbuddy\2026-09-29-10-26-32\portfolio\website

git init
git add .
git commit -m "init: portfolio website"

# 推送到已有仓库的 gh-pages 分支
git remote add origin https://github.com/Babymrbbbb/你的仓库名.git
git push -u origin HEAD:gh-pages
```

然后在仓库设置里开启 GitHub Pages，选择 `gh-pages` 分支。

---

## 简历里怎么写

在简历的"个人项目"或"作品集"部分加一行：

```
个人作品集：https://Babymrbbbb.github.io
GitHub：https://github.com/Babymrbbbb
```



---

## 自定义域名（可选）

如果你有自己的域名（如 `Babymrbbbb.com`），可以在 GitHub Pages 设置里绑定：

```
Settings → Pages → Custom domain → 填入你的域名
```

然后在域名服务商那里配置 CNAME 记录指向 `Babymrbbbb.github.io`。

---

## 更新网站

以后想更新网站内容，直接改 HTML/CSS，然后：

```bash
git add .
git commit -m "update: xxx"
git push
```

GitHub Pages 会自动重新部署（通常 1-2 分钟）。
