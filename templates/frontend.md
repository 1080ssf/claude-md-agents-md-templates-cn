# 前端项目说明（React / Vue + TypeScript）

<!-- 复制为 CLAUDE.md 或 AGENTS.md，按项目实际情况改。 -->

## 技术栈

- 框架：<React 18 / Vue 3>，语言：TypeScript（strict）
- 构建：<Vite>，包管理：<pnpm>
- 样式：<Tailwind / CSS Modules>，组件库：<无 / Element Plus / shadcn>
- 状态：<Pinia / Zustand>，请求：<封装在 src/api/>

## 常用命令

- `pnpm dev` 本地开发，`pnpm build` 构建，`pnpm test` 单测，`pnpm lint` 检查
- 改完至少跑一遍 `pnpm build` 和 `pnpm lint`，有类型错误不算完成

## 约定

1. 组件放 `src/components/`，页面放 `src/pages/`（或 `views/`），接口请求统一走 `src/api/`，不要在组件里直接 fetch。
2. 不用 `any`；接口返回值写类型。
3. 新增依赖前先问我；能用现有工具函数就不要新写。
4. 文案、颜色、间距沿用现有组件的写法，不自创一套。
5. 涉及布局的改动，说明在手机宽度（375px）下是否正常。
6. 不要改 `src/api/` 的基础地址和鉴权逻辑，除非需求就是这个。

## 完成标准

- 构建、lint、相关测试都通过；
- 说明改了哪些文件、怎么手动验证（打开哪个页面、点什么）。
