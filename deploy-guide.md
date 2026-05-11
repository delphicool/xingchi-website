# 🚀 星驰无人机俱乐部 — GitHub Pages 部署指南

## 📋 文件清单检查

已确认以下文件完整存在于 `~/xingchi-website/` 目录：

| 文件 | 用途 |
|------|------|
| ✅ `index.html` | 首页 |
| ✅ `about.html` | 关于我们 |
| ✅ `services.html` | 服务项目 |
| ✅ `cases.html` | 客户案例 |
| ✅ `css/style.css` | 样式文件 |
| ✅ `js/main.js` | JavaScript 交互脚本 |

> 注：导航栏中有"联系我们"链接 (`contact.html`)，如需补充该页面可后续添加。

---

## 第一步：创建 GitHub 仓库并推送代码

### 1.1 登录 GitHub

访问 [https://github.com](https://github.com) 并登录你的账号。如无账号，请先注册。

### 1.2 创建新仓库

1. 点击右上角 **"+"** 号 → **"New repository"**
2. **Repository name** 填写：`xingchi-website`（或其他你喜欢的名称）
3. **Description**（可选）：`星驰无人机俱乐部官方网站`
4. **Visibility**：选择 **Public**（GitHub Pages 免费版需要公开仓库）
5. **不要勾选** "Add a README"、"Add .gitignore"、"Choose a license"
6. 点击 **"Create repository"**

### 1.3 在本地终端推送代码

创建仓库后，在本地终端执行以下命令（**替换 `<你的用户名>` 为你的 GitHub 用户名**）：

```bash
# 进入项目目录
cd ~/xingchi-website/

# 初始化 Git 仓库
git init

# 添加所有文件到暂存区
git add .

# 创建首次提交
git commit -m "🎉 首次提交：星驰无人机俱乐部官网"

# 添加远程仓库（将下方 URL 中的 your-username 替换为你的 GitHub 用户名）
git remote add origin https://github.com/你的用户名/xingchi-website.git

# 推送到 GitHub（默认分支为 main）
git branch -M main
git push -u origin main
```

> **如果推送时提示输入用户名和密码**：密码需要使用 **Personal Access Token (PAT)**，操作方式见下方"常见问题"。

---

## 第二步：配置 GitHub Pages

### 2.1 进入仓库设置

1. 在浏览器中打开你的仓库：`https://github.com/你的用户名/xingchi-website`
2. 点击顶部导航栏的 **"Settings"**（设置）标签

### 2.2 启用 GitHub Pages

1. 在左侧菜单找到 **"Pages"**（或展开后找到 Pages）
2. 在 **"Build and deployment"** 部分：
   - **Source**：选择 **"Deploy from a branch"**
   - **Branch**：选择 **`main`**，目录选择 **`/ (root)`**
3. 点击 **"Save"** 保存

### 2.3 等待部署完成

- 保存后，页面会显示一个黄色提示，表示正在部署
- 通常 1-2 分钟内部署完成，刷新页面后顶部会显示绿色提示：
  > ✅ Your site is live at `https://你的用户名.github.io/xingchi-website/`

---

## 第三步：最终访问网址

部署完成后，你的网站可通过以下地址访问：

```
https://你的用户名.github.io/xingchi-website/
```

> **例如**：如果你的 GitHub 用户名是 `zhangsan`，则网址为：
> `https://zhangsan.github.io/xingchi-website/`

---

## 🌟 可选优化：自定义域名

如果你拥有自己的域名（如 `xingchi-drones.com`），可以配置自定义域名：

1. 在仓库 **Settings → Pages** 的 **"Custom domain"** 中输入你的域名
2. 在你的域名 DNS 管理中添加一条 **CNAME 记录**，指向 `你的用户名.github.io`
3. 勾选 **"Enforce HTTPS"** 以启用 HTTPS

---

## ❓ 常见问题

### Q1: 推送代码时提示认证失败？

GitHub 从 2021 年起已不再支持使用密码进行 Git 操作，需要使用 **Personal Access Token (PAT)**：

1. 访问 GitHub → **Settings** → **Developer settings** → **Personal access tokens** → **Tokens (classic)**
2. 点击 **"Generate new token (classic)"**
3. 勾选 `repo` 权限范围
4. 生成后复制 token 字符串
5. 在终端推送时，用户名输入你的 GitHub 用户名，密码输入这个 token

### Q2: 网站部署后样式不对或图片不显示？

- 确认所有资源引用使用 **相对路径**（如 `css/style.css`），而不是绝对路径
- 按 `F12` 打开浏览器开发者工具 → **Console** 查看错误信息

### Q3: 想要修改网站内容？

修改本地文件后，依次执行：

```bash
cd ~/xingchi-website/
git add .
git commit -m "更新内容说明"
git push
```

GitHub Pages 会自动重新部署（通常 1-2 分钟生效）。

---

## 📞 技术支持

如有其他问题，请随时联系运维团队。
