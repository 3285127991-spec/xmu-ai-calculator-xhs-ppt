# 厦门大学本科生使用AI开发控制计算器

这是一个由 `guizang-ppt-skill` 生成的瑞士风网页 PPT，用于小红书展示。站点是纯静态文件，可以直接用浏览器打开 `index.html`，也可以部署到 GitHub Pages 或 Vercel。

## 文件结构

```text
.
├── index.html
├── images/
│   └── 06-calculator-control.svg
├── icons/
│   ├── icon-192.svg
│   └── icon-512.svg
├── manifest.webmanifest
├── sw.js
└── README.md
```

## 本地预览

直接双击 `index.html`，或在浏览器地址栏打开这个文件即可。翻页方式：

- 键盘左右方向键
- 触屏左右滑动
- 鼠标滚轮
- `ESC` 打开索引
- `B` 切换静态低功耗模式

## 替换 PPT 内容

1. 修改 `index.html` 中 `<div id="deck">` 内的 `<section class="slide ...">` 页面块。
2. 每页保持 `data-layout="..."`，瑞士风正文页建议使用 `S01` 到 `S22` 的登记版式。
3. 如果替换图片，把新图片放到 `images/`，并更新 `index.html` 中对应的 `src="images/..."`。
4. 如果新增或改名图片，也同步更新 `sw.js` 里的 `ASSETS` 缓存列表。
5. 修改后运行校验：

```powershell
node ..\..\..\.agents\skills\guizang-ppt-skill\scripts\validate-swiss-deck.mjs .\index.html
```

如果看到 `Swiss deck validation passed`，说明结构检查通过。

## 重新部署到 GitHub Pages

如果本目录已经是 GitHub 仓库：

```powershell
git add .
git commit -m "Update web PPT"
git push
```

GitHub Pages 会自动从 `main` 分支根目录发布。通常等待 1 到 3 分钟即可刷新公网网址。

如果是第一次部署：

```powershell
git init
git branch -M main
git add .
git commit -m "Initial web PPT"
gh repo create xmu-ai-calculator-xhs-ppt --public --source . --remote origin --push
gh api -X POST repos/OWNER/xmu-ai-calculator-xhs-ppt/pages -f source.branch=main -f source.path=/
```

把 `OWNER` 替换为你的 GitHub 用户名。

## PWA 支持

本项目已包含：

- `manifest.webmanifest`
- `sw.js`
- `icons/`
- `index.html` 中的 PWA 注册代码

部署到 HTTPS 后，手机浏览器可以打开公网网址，并通过浏览器菜单添加到桌面。首次打开后，核心静态文件会被缓存，后续访问更快。
