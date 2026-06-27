# 人格测试工具 - 深度人格特质探索工具

一个优雅、交互式的人格测试单页应用，基于情境选择探索 6 大人格维度。纯前端，无需后端，PWA 支持安装到手机桌面，可直接部署到 GitHub Pages。

## 功能特性

- 🧭 **6 大人格维度**：探索者、思考者、守护者、创造者、领袖、和事佬
- 🎯 **12 道情境题**：贴近生活的场景，帮助你发现自己的特质倾向
- 📊 **可视化结果**：百分比进度条展示各维度得分
- 📱 **响应式设计**：桌面和移动端都获得良好体验
- 🌙 **深色主题**：护眼且现代的暗色 UI
- 🔗 **一键分享**：支持 Web Share API 和剪贴板复制
- ⌨️ **键盘导航**：方向键左右切换题目
   - 🔒 **完全匿名**：无需注册，无数据收集
   - 📲 **PWA 支持**：可安装到手机桌面，像原生 App 一样使用
   - 🌐 **离线可用**：断网也能正常使用

## 在线体验

👉 [人格测试工具](https://litao-code.github.io/personality-test)

## 本地运行

直接用浏览器打开 `index.html` 即可，无需安装任何依赖：

```bash
# 克隆仓库
git clone https://github.com/Litao-Code/personality-test.git
cd personality-test

# 直接在浏览器打开
start index.html    # Windows
open index.html     # macOS
```

## 部署到 GitHub Pages

### 方式一：手动部署（推荐新手）

1. 在 GitHub 上创建一个新仓库，命名为 `personality-test`
2. 将本地代码推送到该仓库：
   ```bash
   git init
   git add .
   git commit -m "初始化人格测试工具"
   git branch -M main
   git remote add origin https://github.com/Litao-Code/personality-test.git
   git push -u origin main
   ```
3. 在 GitHub 仓库页面进入 **Settings → Pages**
4. 在 "Source" 下拉菜单中选择 **Deploy from a branch**
5. 选择 `main` 分支，文件夹选 `/ (root)`
6. 点击 **Save**
7. 等待 1-2 分钟后，你的站点将在 `https://litao-code.github.io/personality-test` 上线

### 方式二：自动部署（GitHub Actions）

本项目已包含 GitHub Actions 工作流（`.github/workflows/deploy.yml`），当你推送代码到 `main` 分支时自动部署到 GitHub Pages。

启用步骤：

1. 将代码推送到 GitHub 仓库
2. 进入仓库 **Settings → Pages**
3. 在 "Source" 下拉菜单中选择 **GitHub Actions**
4. 推送任意提交到 `main` 分支，Actions 将自动构建并部署

### 方式三：使用 gh-pages 分支

```bash
# 安装 gh-pages 工具（如需要）
npx gh-pages -d .
```

## 自定义测试内容

想修改题目或人格类型？编辑 `index.html` 中的 JavaScript 数据部分：

- `TYPES` 数组：定义 6 个人格维度的名称、描述、优势和成长建议
- `QUESTIONS` 数组：定义题目、选项及每题选项对各维度的权重分值

权重分值范围 0-3，分值越高代表该选项越倾向对应维度。

## 技术栈

- 纯 HTML5 + CSS3 + JavaScript（ES6+）
- Google Fonts (Inter)
- PWA（manifest.json + Service Worker）
- 无任何第三方依赖或框架
- 完全静态可部署

## 项目结构

```
personality-test/
├── index.html                  # 主应用（单页，含全部样式和逻辑）
├── manifest.json               # PWA 配置（应用名、图标、主题色）
├── sw.js                       # Service Worker（离线缓存）
├── icon.svg                    # 应用图标源文件
├── icon-192.png                # 应用图标 192x192
├── icon-512.png                # 应用图标 512x512
├── README.md                   # 项目说明和部署指南
└── .github/
    └── workflows/
        └── deploy.yml          # GitHub Actions 自动部署配置
```

## License

MIT

## 安装到手机（PWA）

部署到 GitHub Pages 后用手机浏览器访问，即可安装到桌面。

### Android (Chrome)
1. 用 Chrome 打开你的部署网址
2. 点击地址栏下方的 **"添加到主屏幕"** 或菜单中的 **"安装应用"**
3. 点击 **安装**，图标出现在桌面

### iPhone / iPad (Safari)
1. 用 Safari 打开你的部署网址
2. 点击底部分享按钮（方框+箭头）
3. 向下滑动，选择 **"添加到主屏幕"**
4. 点击 **"添加"**

安装后全屏运行，没有浏览器地址栏，和原生 App 体验一致。
