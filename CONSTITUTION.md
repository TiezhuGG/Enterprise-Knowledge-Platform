---
title: 项目宪法（Project Constitution）
version: 1.0.0
status: Approved
owner: Product Owner
architect: Chief Architect
effective_date: 2026-07-06
review_cycle: 每个 Milestone Review 一次
---

# 项目宪法（Project Constitution）

## 前言

本文件是 Enterprise AI Knowledge Platform（EAKP）的最高工程规范。

所有文档、所有代码、所有数据库设计、所有 AI 开发行为，均必须遵守本文件。

若其他文档与本文件发生冲突，以本文件为准。

---

# 第一章 项目核心价值观

整个项目遵循以下原则：

1. Architecture First（架构优先）
2. Documentation First（文档优先）
3. Specification First（规格优先）
4. Security By Design（安全内建）
5. AI Assisted Development（AI辅助开发）
6. Domain Driven Design（DDD）
7. Event Driven Architecture（EDA）
8. Enterprise Quality（企业级质量）
9. Testability（可测试）
10. Maintainability（可维护）

任何实现不得违反以上原则。

---

# 第二章 单一事实来源（SSOT）

项目中只有以下内容可以作为事实来源：

- Project Charter
- Constitution
- Architecture
- Specification
- ADR
- Database Design

代码不得作为业务规则的唯一来源。

所有业务规则必须有对应文档。

---

# 第三章 文档优先原则

任何功能开发之前，必须完成：

需求

↓

架构设计

↓

规格说明

↓

任务拆分

↓

编码实现

↓

Review

↓

Merge

禁止直接进入编码。

---

# 第四章 架构优先原则

未经 ADR 批准，禁止：

- 修改系统架构
- 修改模块边界
- 修改数据库核心设计
- 引入新的基础设施
- 修改目录结构

任何重大修改必须新增 ADR。

---

# 第五章 模块边界

模块之间只能通过公开接口通信。

禁止：

- Controller 调用 Repository
- Module 直接访问其他 Module 数据库
- Domain 依赖 Infrastructure
- Infrastructure 依赖 Presentation

模块必须保持低耦合。

---

# 第六章 DDD 原则

所有业务能力必须归属于明确领域。

例如：

IAM

Document

Knowledge

Search

AI

Workflow

System

禁止：

God Service

God Module

God Controller

---

# 第七章 AI 开发原则

AI 是开发助手。

不是架构师。

AI 可以：

✅ 编写代码

✅ 修复 Bug

✅ 编写测试

✅ 重构局部代码

AI 不可以：

❌ 修改架构

❌ 修改数据库设计

❌ 修改目录结构

❌ 引入第三方依赖

❌ 修改 ADR

除非收到明确任务。

---

# 第八章 AI 行为规范

AI 每次开发之前必须：

1.

阅读：

PROJECT_CHARTER

2.

阅读：

CONSTITUTION

3.

阅读：

Architecture

4.

阅读：

Specification

5.

阅读：

Coding Standard

6.

开始开发

禁止：

直接开始写代码。

---

# 第九章 Repository 原则

所有业务模块必须拥有：

README

API

DATABASE

FLOW

CHECKLIST

TEST

缺一不可。

---

# 第十章 命名规范

所有：

代码

数据库

API

使用英文。

所有：

需求

文档

规格

设计

使用中文。

---

# 第十一章 Git 原则

禁止：

直接提交 main。

采用：

feature/*

↓

Pull Request

↓

Review

↓

Merge

Commit Message 使用 Conventional Commits。

例如：

feat:

fix:

docs:

refactor:

test:

chore:

---

# 第十二章 编码原则

必须遵循：

SOLID

DRY

KISS

YAGNI

Clean Code

禁止：

重复代码

超长函数

魔法数字

硬编码

---

# 第十三章 数据库原则

数据库修改：

必须：

Migration

禁止：

直接修改数据库。

数据库设计必须来源于：

Specification。

---

# 第十四章 API 原则

所有接口：

必须：

RESTful

统一响应格式

统一错误码

统一分页

统一鉴权

统一日志

---

# 第十五章 安全原则

默认：

所有接口需要认证。

默认：

所有操作记录 Audit Log。

默认：

所有密码 BCrypt。

默认：

所有 Token JWT。

默认：

所有上传文件病毒扫描。

默认：

所有输入校验。

---

# 第十六章 测试原则

每个模块必须拥有：

单元测试

集成测试

API测试

关键业务必须拥有：

E2E。

---

# 第十七章 Review 原则

所有代码：

必须：

Review。

AI 生成代码：

必须：

人工 Review。

禁止：

AI 直接 Merge。

---

# 第十八章 文档原则

文档是代码的一部分。

任何：

架构修改

数据库修改

API修改

必须同步修改文档。

禁止：

代码更新。

文档未更新。

---

# 第十九章 Prompt 原则

Prompt 属于工程资产。

必须：

版本管理。

禁止：

聊天记录成为唯一 Prompt。

所有 Prompt 必须进入：

prompts/

目录。

---

# 第二十章 持续演进原则

项目允许持续优化。

但是：

不得推翻已有规范。

任何重大调整：

必须新增：

ADR。

而不是修改历史。

---

# 最终原则

所有参与本项目的人（包括 AI）都必须遵守本宪法。

任何违反本宪法的实现，都应被视为缺陷，而不是功能。
