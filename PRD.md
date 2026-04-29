# PRD - B2B Content SEO System

## 0. Source of Truth Policy

`PRD.md` / `ARCH.md` / `Project.md` 是系统的单一真相源。

- 所有代码实现必须与这三份文档一致
- 任何重大改动必须同步更新这三份文档
- 如未同步更新，禁止合并代码

## 1. Product Goal

构建一个可控的 B2B 内容生产与发布系统，实现：

- 每周稳定发布 ≥ 200 篇文章
- 每篇文章具备 SEO + GEO + AEO 结构
- 每篇文章具备明确转化路径（CTA + 产品内链）
- 所有内容可审核、可回滚、可追踪

## 2. Current Delivery Scope

当前处于 `Phase 1 - MVP（可控发布系统）`，本阶段重点是：

- 建立内容生产、审核、SEO检查、发布门禁的闭环
- 固化人工审核与回滚能力
- 接通独立站 CMS 发布流程

## 3. Core Modules

- Keyword Engine
- Content Engine
- Product Link Engine
- Image Generation
- SEO / AEO Checker
- Publishing System
- Analytics & Feedback

## 4. Functional Requirements

### 4.1 Keyword Engine

- 输入种子关键词
- 自动扩展长尾关键词
- 分类关键词（cost / scenario / comparison / geo）

完成标准：

- 每个种子词 ≥ 100 关键词
- 每个关键词必须有 `category + intent`
- 不允许重复关键词

### 4.2 Content Engine

- 生成文章（1500–2500字）
- 自动生成 FAQ / Meta / CTA

完成标准：

- ≥ 1500 字
- ≥ 3 个 H2
- ≥ 5 FAQ
- ≥ 2 CTA

### 4.3 Product Link Engine

- 根据文章内容匹配产品页
- 自动插入内链

完成标准：

- 每篇 ≥ 3 内链
- ≥ 1 产品页链接
- 所有链接 HTTP 200

### 4.4 Image Generation

- 根据文章上下文生成图片
- 自动生成 alt text

完成标准：

- 每篇 ≥ 1 封面图
- 图片必须通过人工审核
- 图片不得包含错误信息

### 4.5 SEO / AEO Checker

- 检查 SEO 结构
- 检查 FAQ / Meta / 内链

完成标准：

- 所有检查项 100% 通过才允许发布

### 4.6 Publishing System

- 定时发布
- 发布日志
- 回滚

完成标准：

- 发布成功率 ≥ 99%
- 发布后 URL 可访问（HTTP 200）

### 4.7 Analytics

- 追踪流量 / 点击 / 转化

完成标准：

- 每篇文章有独立数据
- 数据延迟 ≤ 24h

## 5. Non-Functional Requirements

- 可扩展（支持多国家 GEO）
- 可回滚（版本控制）
- 可审计（所有操作有日志）
- 高可用（发布成功率 ≥ 99%）

## 6. Constraints（强约束）

- 不允许 AI 直接发布文章
- 不允许跳过 `human_review`
- 不允许无 SEO 检查发布
- 不允许生成虚假产品信息

## 7. Publishing Target

- 独立站后台：`https://www.jhhycontainerhouse.com/nosay/dashboard`
- 当前规则：最终发布动作必须围绕该后台设计

## 8. Linked Docs

- 架构说明：`ARCH.md`
- 项目状态：`Project.md`
