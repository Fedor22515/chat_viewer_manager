# ChatGPT 对话查看器（V3.2）

> 一个**纯前端、离线优先**的对话与笔记浏览器：把你的 ChatGPT 聊天记录（JSON/Markdown 等）拖进来/载入后，即可在本地以列表 + 气泡样式**快速查看、整理与美化**。所有数据仅在你的浏览器内处理，不上传服务器。

<p align="center">
  <img alt="status" src="https://img.shields.io/badge/status-active-4caf50">
  <img alt="license" src="https://img.shields.io/badge/license-TBD-blue">
  <img alt="tech" src="https://img.shields.io/badge/stack-HTML%2FCSS%2FJS-informational">
</p>

---

## 目录
- [功能亮点](#功能亮点)
- [快速开始](#快速开始)
- [使用方法](#使用方法)
- [外观与主题](#外观与主题)
- [移动端优化](#移动端优化)
- [笔记本视图](#笔记本视图)
- [数据与隐私](#数据与隐私)
- [在 GitHub Pages 部署](#在-github-pages-部署)
- [常见问题（FAQ）](#常见问题faq)
- [开发与二次定制](#开发与二次定制)
- [致谢与许可](#致谢与许可)
- [English Summary](#english-summary)

---

## 功能亮点
- **左右分栏 + 工具栏**：左侧会话列表，右侧正文聊天视图，顶部工具栏提供显示模式、书签、外观设置等常用控件。  
- **聊天视图**：贴近即时通讯的气泡布局（含头像、时间等元信息），代码块、列表、引用等 Markdown 元素都有良好样式。  
- **书签 / 批量选择 / 视图模式**：提升大体量对话的浏览与筛选效率。  
- **外观设置（Appearance）面板**：支持 Light / Dark / 自定义主题；可调 UI/正文字号、气泡圆角/阴影、配色、头像、导航透明度、页面背景图等。  
- **笔记本视图（Notebook）**：用于沉淀与整理要点，默认隐藏页级按钮以减少干扰，“新建笔记本”输入行的尺寸与排列做了便捷优化。  
- **移动端友好**：≤900px 启用抽屉式侧栏与紧凑工具栏，气泡/头像等尺寸随屏幕自适应。  
- **顶端轻提示**：内置 `window.toast('消息')`，可用于显示轻量反馈。  

> 说明：本工具为单文件前端应用（`index.html`），开箱即用。

---

## 快速开始
1. **打开方式**  
   - 直接用现代浏览器（Chrome / Edge / Firefox / Safari）打开 `index.html`。  
   - 若浏览器阻止本地文件访问，建议在项目文件夹运行本地静态服务器：  
     ```bash
     # Python 3
     python -m http.server 8080
     # or
     python -m http.server
     ```
     然后访问 `http://localhost:8080`。

2. **导入会话**  
   - 在顶部工具栏选择你的对话数据文件（如从 ChatGPT 导出的 JSON/Markdown）。  
   - 文件会在**本地**解析并渲染，整个过程不经任何后端。

3. **浏览与整理**  
   - 左侧为会话列表，支持勾选、定位。  
   - 右侧为聊天视图，支持代码高亮、引用与列表等富文本展示。  
   - 使用工具栏的**显示模式 / 书签 / 批量选择**进行快速筛选与定位。

---

## 使用方法
- **会话列表**：点击任意会话可在右侧打开；当前项会高亮。  
- **消息气泡**：左/右两列分别表示角色；支持不同类型消息（例如自定义内容、系统提示、记忆更新等）。  
- **工具栏**：包含显示模式切换、书签、批量选择、外观设置入口等；在移动端默认折叠，点击展开后可见全部控件。

---

## 外观与主题
- **主题模式**：在外观面板选择 Light / Dark / 自定义。  
- **可调参数**（通过外观面板或 CSS 变量）：
  - UI/正文字号、行高
  - 气泡圆角、阴影、最大宽度
  - 头像显示与尺寸
  - 导航透明度
  - 页面背景图（`--page-bg-image`）
- **可读性保护**：不同主题下的前景/背景对比度已做优化，保证主要文本可读。

> 进阶：也可直接在 `index.html` 的 `:root` 段落覆盖 CSS 变量以定制主题。

---

## 移动端优化
- **抽屉式侧栏**：在窄屏下，左侧会话列表以抽屉形式出现，点击按钮呼出/收起。  
- **紧凑工具栏**：移动端默认折叠，展开后显示完整控件。  
- **自适应气泡**：气泡最大宽度、头像尺寸、间距等随屏幕变化自动调整，保证阅读舒适。

---

## 笔记本视图
- **干净编辑区**：默认隐藏页级 UI（新增/删除页按钮等），聚焦内容创作与浏览。  
- **“新建笔记本”输入区**：统一高度、单行排列，便于快速创建与命名。  

> 提示：笔记与会话浏览互不干扰，便于一边读一边记。

---

## 数据与隐私
- **离线本地处理**：导入的对话文件会在浏览器内存中解析，不会上传到任何服务器。  
- **权限与缓存**：如需清理缓存，可在浏览器设置中清除站点数据。  
- **安全建议**：请勿导入含有敏感个人信息的文件至公共电脑；必要时对数据做匿名化处理。

---

## 在 GitHub Pages 部署
将此项目托管到 GitHub 并开启 Pages，即可获得一个所有人都能在浏览器打开的在线版本：
1. **创建仓库**：在 GitHub 新建一个仓库（例如 `chatlog-viewer`）。  
2. **推送代码**：把 `index.html`（以及其他资源，如图标/预设）提交并推送到 `main` 分支。  
3. **启用 Pages**：进入仓库 **Settings → Pages**，将 **Source** 设为 `Deploy from a branch`，分支选择 `main / root`。  
4. **访问链接**：稍等片刻后，GitHub 会生成一个 `https://<你的用户名>.github.io/<仓库名>/` 的访问地址。

> 若需自定义域名，可在 Pages 设置中绑定 CNAME。

---

## 常见问题（FAQ）
**Q：为什么看不到“页”相关按钮？**  
A：笔记本视图默认隐藏页级 UI，以减少干扰、聚焦单页内容。

**Q：移动端没有看到“书签”等控件？**  
A：移动端工具栏默认折叠，请点击展开按钮。

**Q：怎样自定义颜色/背景？**  
A：打开外观设置面板；或在 `index.html` 中覆盖 `:root` 的 CSS 变量（如 `--page-bg-image`、颜色与字号等）。

**Q：我的数据会被上传吗？**  
A：不会。所有解析与渲染均在浏览器本地完成。

---

## 开发与二次定制
- **快速换肤**：在 `index.html` 的 `:root` 中覆盖 CSS 变量；或扩展外观面板的控件。  
- **轻提示**：`window.toast('消息')` 可显示顶部轻量提示。  
- **代码组织**：本项目为**单文件**实现，便于 fork 和小范围修改；如需模块化，可进一步拆分 CSS/JS。

欢迎 PR / Issue 提出改进建议与新特性需求。

---

## 致谢与许可
- 本工具强调**离线、本地、可定制**的体验：把内容的整理权交还给你，并以主题、移动端与笔记优化降低使用摩擦。  
- 许可证（License）：当前未指定，请根据你的项目需求添加 `LICENSE` 文件。

---

## English Summary

**ChatGPT Conversation Viewer (V1.9.2)** — a **client‑only**, offline‑first viewer for ChatGPT exports (JSON/Markdown). Drop a file to render chats with a clean **sidebar + chat bubbles** layout, plus a **Notebook** for highlights. Everything runs **locally** in your browser, no server involved.

**Highlights**
- Split layout with toolbar (view modes, bookmarks, appearance panel).  
- Chat bubbles with avatars/timestamps, nice Markdown & code blocks.  
- Notebook view optimized for focused writing (page‑level UI hidden by default).  
- Appearance panel with **Light/Dark/Custom** themes; adjustable typography, bubble radius/shadows, colors, avatar, nav opacity, page background image.  
- Mobile‑friendly: drawer sidebar & compact toolbar on ≤900px.

**Quick Start**
- Open `index.html` directly, or serve locally:  
  ```bash
  python -m http.server 8080
  ```
- Import your exported chat file; parsing & rendering happen locally.

**Deploy to GitHub Pages**
- Create a repo, push `index.html`, enable **Settings → Pages** (`main / root`), then visit the generated URL.

**Privacy**
- Files are parsed **in‑browser** and never uploaded.

**Customize**
- Tweak CSS variables in `:root` or extend the appearance panel.  
- Use `window.toast('message')` for lightweight notifications.

**License**
- TBD. Please add a `LICENSE` file according to your project needs.
