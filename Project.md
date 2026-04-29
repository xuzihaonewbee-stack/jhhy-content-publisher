# Project Status

## 0. Source of Truth Policy

`PRD.md` / `ARCH.md` / `Project.md` 是系统的单一真相源。

- 任何代码实现必须与这三份文档一致
- 任何重大改动必须同步更新这三份文档
- 如果代码与文档不一致，禁止合并代码

## 1. Current Phase

Phase 1 - MVP（可控发布系统）

## 2. Completed

- [x] 项目初始化
- [x] 数据库设计
- [x] 关键词模块
- [x] 内容生成模块
- [x] 内链模块
- [x] SEO检查模块

## 3. In Progress

- [ ] 图片生成模块
- [ ] 发布系统
- [ ] 管理后台UI

## 4. Blockers

- AI内容稳定性
- 图片生成一致性
- CMS接口限制

## 5. Next Steps

- 完成发布系统
- 接入GA4
- 完成审核流程

## 6. Tech Debt

- 未优化SEO评分逻辑
- 图片prompt不稳定
- 内链匹配规则较简单

## 7. Recent Changes（必须写原因）

### 2026-04-29

变更：完成 TypeScript monorepo 初始化，建立 `apps/`、`packages/`、`workers/`、`docs/`、`reference/` 目录  
原因：让项目结构与目标架构一致，便于后续扩展 API、Worker、管理后台  
影响：repository structure / build setup / docs

### 2026-04-29

变更：新增 Prisma 数据模型，覆盖 `User`、`Keyword`、`ProductPage`、`Article`、`ArticleVersion`、`InternalLink`、`ArticleImage`、`SeoCheck`、`PublishLog`、`AuditLog`、`ADR`  
原因：先固化可审计、可回滚、可追踪的数据基础  
影响：database / API contracts / worker inputs

### 2026-04-29

变更：新增关键词、内容、内链、SEO 检查的 MVP 业务骨架，并把发布状态机放到服务端核心层  
原因：满足 Phase 1 对“可控发布系统”的基本要求，同时避免前端绕过审核和 SEO 校验  
影响：core layer / article flow / publishing rules

### 2026-04-29

变更：新增 JHHY CMS adapter 骨架，明确最终发布入口为 `https://www.jhhycontainerhouse.com/nosay/dashboard`  
原因：独立站后台是唯一发布入口，需要先锁定适配边界，避免业务层直接耦合 CMS  
影响：publishing system / adapter layer / integration plan

## 8. Rules（强约束）

- 每次功能变更必须更新本文件
- 每次架构变更必须同步 `ARCH.md`
- 每次需求变更必须同步 `PRD.md`
- `PRD.md` / `ARCH.md` / `Project.md` 必须保持一致
- 如未同步更新三份文档，禁止合并代码
