# Architecture

## Source of Truth Policy

`PRD.md` / `ARCH.md` / `Project.md` 是系统的单一真相源。

- 所有实现必须与这三份文档一致
- 任何重大改动都必须同步更新这三份文档
- 如代码与文档不一致，禁止合并

## Current Target

本项目当前采用 Phase 1 MVP 架构，目标是构建一个“可控发布系统”，而不是开放式自动发布系统。

## Tech Stack

- Frontend: Next.js + TypeScript
- Backend: NestJS
- Database: PostgreSQL
- ORM: Prisma
- Queue: Redis + BullMQ
- Storage: S3 / R2（通过 adapter 接入）
- AI: OpenAI / Claude（通过 adapter 接入）

## Layering

- Web Layer: `apps/web`
- API Layer: `apps/api`
- Core Layer: `packages/core`
- Adapter Layer: `packages/adapters`
- Worker Layer: `workers/content-jobs`
- DB Layer: `packages/db`

## Core Rules

- 前端只负责展示与输入
- 权限、状态机、SEO检查、发布逻辑全部在后端处理
- 业务层不允许直接调用第三方 API
- 所有外部服务必须通过 adapter 封装
- 不允许跳过文章状态机
- 最终发布入口固定为 JHHY CMS 后台

## Current State

- 已完成 monorepo 基础结构
- 已完成 Prisma 核心模型
- 已完成服务端文章状态机骨架
- 已完成 AI / CMS adapter 边界定义
- 发布系统仍是手动发布适配阶段，尚未完成真实 CMS 工作流对接

## Related Docs

- 架构细节：`docs/architecture/system-design.md`
- 架构决策：`docs/architecture/ADR-0001-monorepo-foundation.md`
- 项目状态：`Project.md`
- 产品需求：`PRD.md`
