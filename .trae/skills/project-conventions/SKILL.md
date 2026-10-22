---
name: project-conventions
description: 前端练习作品集项目的强制开发规范。在创建或修改 HTML/CSS/JS 文件、新增练习页、编辑 index.html 链接或卡片之前使用。涵盖 zhang_ 前缀命名、提示词追加写入 zhang_prompt.md、页面自包含与 work-list 卡片同步规则。
---

# 项目规范 —— 前端练习作品集

本项目是纯静态 HTML/CSS 课程作业作品集：无构建步骤、无包管理器、无依赖、无测试，直接在浏览器打开 `index.html`。执行任何任务前必须遵守以下规范。

## 1. 命名规范（强制）

- 所有 CSS 类名、ID 名必须以 `zhang_` 开头，例如 `zhang_hero`、`zhang_work-card`
- 所有 JS 变量名必须以 `zhang_` 开头，例如 `zhang_box`

## 2. 提示词记录流程（每次执行前）

先将用户提示词**追加**写入 `zhang_prompt.md`（不覆盖已有内容），写入内容包括：时间、使用的模型、提示词原文。格式与文件中已有条目保持一致：

```markdown
---

## 2026-10-22 15:30:00

**Model:** 模型名

**Prompt:**
提示词内容
```

## 3. 页面规范

- 仅使用原生 HTML/CSS/JS：不引入 CDN、框架或任何外部资源
- 每个练习页（`N-M.html`）自包含，样式写在内联 `<style>` 块中
- `index.html` 使用 `lang="zh-CN"`；练习页使用 `lang="en"`，编辑已有页面时保持其 lang 不变
- `css.css` 是独立的样式表练习，不与任何 HTML 文件链接
- 含中文的文件名在 `index.html` 链接中必须使用 URL 编码路径（如 `5-1%E5%B1%82%E5%8F%A0%E4%B8%8E%E7%BB%A7%E6%89%BF.html`），编辑链接时保留该编码

## 4. 新增练习页流程

1. 文件命名为 `N-M.html`（N 为章节号，M 为序号，如 `14-1.html`）
2. 页面自包含：内联 `<style>` 块，所有类名/ID/JS 变量带 `zhang_` 前缀
3. 在 `index.html` 的 `work-list` 网格中添加对应卡片，链接指向新页面（中文文件名需 URL 编码）

## 5. 完成前检查

- [ ] 新写代码的类名/ID/JS 变量均以 `zhang_` 开头
- [ ] 提示词已按格式追加到 `zhang_prompt.md`
- [ ] 新增练习页已在 `index.html` 添加对应卡片
- [ ] `index.html` 中所有链接都能解析到实际文件（注意 URL 编码是否匹配）
