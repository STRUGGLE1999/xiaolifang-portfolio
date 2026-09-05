# 肖丽芳个人网站 (Lifang Xiao Portfolio)

> 基于 [thesephist.com](https://thesephist.com/) 极简文人风格设计，专为技术型 AI 产品经理与研究者量身打造的个人官方展示网站。

---

## 目录结构

```
personal_website/
├── index.html        # 中文版主站 (收录 10 大严苛脱敏实战、9 大开源作品、21.7W+ 博客与学术专利)
├── styles.css        # 核心样式表 (思源宋体 + IBM Plex Serif 衬线字体、纯白底色、响应式排版)
├── en/
│   └── index.html    # 英文版镜像 (适合国际化/出海团队与英文学术交流)
└── README.md         # 本文档 (本地预览与 0 元免费上线部署指南)
```

---

## 一、本地极速预览

由于采用现代化原生纯静态架构，**无需任何 Node.js 或 npm 打包编译环境**：

- **方法 1（最简单）**：直接在电脑文件管理器中，**双击 `index.html`** 即可在浏览器中查看；
- **方法 2（推荐本地 HTTP 服务）**：
  在终端进入 `personal_website` 目录运行：
  ```bash
  python3 -m http.server 8080
  ```
  在浏览器打开：`http://localhost:8080`。

---

## 二、0 元免费上线部署指引（GitHub Pages + Cloudflare Pages）

你可以完全不花一分钱，将网站发布至全球互联网，并同时拥有两个永久免费、带 HTTPS 小绿锁的专属域名：
- `https://struggle1999.github.io`
- `https://xiaolifang.pages.dev`

### 1. 将网站代码推送到 GitHub
1. 在你的 GitHub 账号（`STRUGGLE1999`）新建一个公开仓库，例如命名为 `xiaolifang-portfolio`；
2. 在本地终端进入 `personal_website` 目录：
   ```bash
   cd /Users/work/code/Antigravity/AI-Product-Manager/personal_website
   git init
   git add .
   git commit -m "feat: initial release of personal portfolio"
   git branch -M main
   git remote add origin https://github.com/STRUGGLE1999/xiaolifang-portfolio.git
   git push -u origin main
   ```

---

### 2. 方案 A：启用 GitHub Pages（免费获得 `struggle1999.github.io`）
1. 打开刚刚新建的 GitHub 仓库页面；
2. 点击仓库顶部的 **Settings**（设置） $\rightarrow$ 左侧菜单 **Pages**；
3. 在 **Build and deployment** 下：
   - **Source** 选择 `Deploy from a branch`；
   - **Branch** 选择 `main` 分支，目录选择 `/ (root)`；
   - 点击 **Save**（保存）；
4. 等待约 1~2 分钟，页面顶部会显示绿色的部署成功提示：
   👉 你的专属访问地址为：`https://struggle1999.github.io/xiaolifang-portfolio/`  
   *(注：若将仓库名直接命名为 `STRUGGLE1999.github.io`，访问地址则为根域名 `https://struggle1999.github.io`)*。

---

### 3. 方案 B：启用 Cloudflare Pages（国内秒开，推荐！免费获得 `xiaolifang.pages.dev`）
1. 打开并登录 [Cloudflare Dashboard](https://dash.cloudflare.com/)；
2. 点击左侧导航栏的 **Workers & Pages** $\rightarrow$ 点击 **Create application** $\rightarrow$ 选择 **Pages**；
3. 点击 **Connect to Git**（连接到 Git），授权并选中刚刚的 `xiaolifang-portfolio` 仓库；
4. 进入构建设置：
   - **Project name（项目名称）**：填入 `xiaolifang`（若未被占用，生成的域名就是 `https://xiaolifang.pages.dev`）；
   - **Framework preset**：选择 `None`；
   - **Build command**：留空；
   - **Build output directory**：填入 `/` 或留空；
5. 点击 **Save and Deploy**（保存并部署）；
6. 约 10 秒后部署完成，即可直接通过 **`https://xiaolifang.pages.dev`** 全球高速访问！

---

## 三、内容更新与维护

- **添加新文章**：直接打开 `index.html`，在 `<section id="writing">` 区域仿照现有的 `.work-item` 复制一段，填入文章标题、CSDN 外链与更新日期即可；
- **添加新项目**：在 `<section id="enterprise">` 或 `<section id="software">` 中添加对应条目；
- 更新后执行 `git commit -am "update"` 与 `git push`，Cloudflare Pages 会在 10 秒内自动构建生效！
