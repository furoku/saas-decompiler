# SaaS Decompiler — 简体中文提示词集

这里所说的 SaaS 逆编译，是指从公开网站、实际可操作的产品界面、截图、URL、公开文档等可观察信息中，反推出该 SaaS 的设计思想与结构。

## 1. 通用 SaaS 逆编译

请完整逆编译这个 SaaS。

不要停留在表面的 UI 描述，而要把它结构化到可以从零重建该产品的程度。

请分析：

- SaaS 解决的问题
- 目标用户
- JTBD（用户想完成的工作）
- 核心价值
- 主要使用场景
- 页面结构
- 信息架构
- 导航
- 功能清单
- 用户流程
- 状态转换
- 数据结构
- 权限结构
- 业务规则
- UI 设计系统
- 组件结构
- 可能需要通过 API 提供的功能
- 外部服务集成
- 计费模型
- Onboarding
- 留存设计
- 错误处理
- 空状态
- 通知
- 搜索
- 筛选
- 管理后台
- 安全所需设计
- 非功能需求
- 实现优先级

最后请分离：

1. 可直接观察到的事实
2. 高置信度可推断的设计
3. 仅属于推测的部分
4. 重建时可以省略的部分
5. MVP 绝对必需的部分

## 2. 从截图逆编译 SaaS

请根据附加的 SaaS 截图逆编译这个产品的结构。

不要只是描述图中出现了什么，而要进一步推断：

“既然这个页面存在，那么背后必须有哪些功能、数据、状态和规则？”

分析对象：

- 页面目的
- 页面层级
- 全局导航
- 局部导航
- UI 组件
- 可交互元素
- CRUD 操作
- 列表 / 详情 / 编辑之间的关系
- 数据字段
- 数据类型
- 数据之间的关系
- 筛选
- 排序
- 搜索
- 分页
- 状态
- 权限
- Modal
- Drawer
- Toast
- 空状态
- Loading
- Error 状态
- 用户操作导致的状态变化

每个要素请使用：

**界面上的证据 → 推断出的规格**

这种格式输出。

## 3. 从 URL 逆编译整个 SaaS

请从这个 URL 出发，在可访问范围内探索整个站点并逆编译该 SaaS。

不要只看单一页面，尽可能横向检查：

- 首页
- 注册
- 登录
- Onboarding
- Dashboard
- 设置
- 计费
- 帮助
- 文档
- FAQ
- 服务条款
- 隐私政策
- 已公开的功能介绍

然后把：

**营销网站承诺的价值**

与

**产品实际提供的功能**

分开。

最终生成一个足以重建该 SaaS 的 Product Requirements Document 级别规格。

## 4. UI / UX 逆编译

请详细逆编译这个 SaaS 的 UI / UX 设计。

### 布局

- 最大宽度
- Grid
- Sidebar 宽度
- Header 高度
- 列结构
- 间距规则
- 内容密度

### Typography

- 字体类别
- 字号层级
- 字重
- 行高
- 标题层级
- 数字显示方式

### 颜色

- Primary
- Secondary
- Accent
- Background
- Surface
- Border
- Text
- Success
- Warning
- Error

### 组件

- Button
- Input
- Select
- Checkbox
- Radio
- Toggle
- Tabs
- Table
- Card
- Badge
- Avatar
- Tooltip
- Modal
- Drawer
- Dropdown
- Toast
- Date Picker

对每个组件推断：

- 外观
- 尺寸
- Variant
- State
- Hover
- Focus
- Disabled
- Loading
- Error

最后汇总成可用于重现的 Design Tokens。

## 5. 设计系统逆编译

请从这个 SaaS 中提取设计系统。

不要复制某一个页面，而是寻找多个页面共同遵守的规则。

提取：

- Color Token
- Typography Token
- Spacing Token
- Radius
- Border
- Shadow
- Z-index
- Icon
- Grid
- Breakpoint
- Motion
- Component Variant
- Interaction State

如果某个值无法直接确认，请明确标注为：

“根据视觉外观推测的值”。

如果可能，请整理为能够转换为 CSS Variables / Tailwind Theme / Design Tokens 的格式。

## 6. 前端结构逆编译

请以一名前端工程师的视角逆编译这个 SaaS。

假设使用 React / Next.js 等技术重建页面，请拆分为：

- Layout
- Page
- Feature
- Component
- UI Primitive

推断：

- Routing
- Nested Layout
- Shared Component
- Feature Component
- State Management
- Server State
- Local State
- Form State
- Optimistic Update
- Cache
- Pagination
- Infinite Scroll
- Search Params
- URL State

最后生成推荐目录结构。

不要断言目标 SaaS 实际使用了某种内部技术，而应作为：

“如果要合理重建，可以采用的结构”

来提出建议。

## 7. 数据模型逆编译

请从这个 SaaS 的 UI 反推出背后的数据模型。

从界面中可见的以下概念等提取 Entity：

- 名称
- ID
- 用户
- 团队
- Workspace
- Project
- Status
- Tag
- Date
- Owner
- Permission
- Relation

对每个 Entity 推断：

- Entity 名称
- 作用
- Field
- Data Type
- Required / Optional
- Relation
- Unique Constraint
- Index 候选
- Lifecycle

最终整理成可转换为：

- ER 图
- SQL Schema
- Prisma Schema 或同等结构

的形式。

所有推断部分必须标注置信度。

## 8. 用户流程逆编译

请逆编译用户在这个 SaaS 中实现目标的完整操作过程。

针对每个主要 JTBD，按以下格式写出流程：

Start
↓
Action
↓
System Response
↓
Decision
↓
Next Action
↓
Success

同时推断以下分支：

- Happy Path
- 首次用户
- 回访用户
- 数据 0 条
- 输入错误
- 权限不足
- 网络错误
- 取消
- 删除
- 恢复

## 9. 状态转换逆编译

请反推出这个 SaaS 中主要对象的 State Machine。

例如：

Draft
↓
Processing
↓
Completed

根据 UI 上的 Badge、Button、Menu、显示切换等信息推断状态。

对每个状态整理：

- State
- Entry Condition
- Allowed Action
- Forbidden Action
- Next State
- Rollback
- UI Representation

## 10. 业务逻辑逆编译

请从这个 SaaS 的 UI 推断背后的业务规则。

不要只看 CRUD，而要分析：

“为什么这个按钮只在这个条件下显示？”

“为什么这条数据不能编辑？”

“为什么会进入这个状态？”

按以下格式输出：

RULE-001

条件：
WHEN ...

处理：
THEN ...

例外：
EXCEPT ...

UI 上的证据：

置信度：
High / Medium / Low

## 11. 认证 / 权限逆编译

请逆编译这个 SaaS 的 Authentication / Authorization 设计。

推断：

- Sign up
- Login
- OAuth
- Magic Link
- Password Reset
- Email Verification
- MFA
- Session
- Organization
- Workspace
- Team
- Role
- Permission

判断 RBAC 或 ABAC 哪一种更适合。

角色示例：

- Owner
- Admin
- Member
- Viewer
- Guest

针对每个 Role，将 View / Create / Edit / Delete / Invite / Billing / Admin 权限做成矩阵。

## 12. Workspace / Team 结构逆编译

请逆编译这个 SaaS 的账户结构。

重点分析 User / Organization / Workspace / Team / Project 之间的关系。

确认：

- 一个用户是否可以属于多个 Workspace
- 是否存在 Workspace 切换
- 邀请功能
- Role
- Ownership
- Seat
- Billing 单位
- Data Isolation
- Workspace 删除
- Ownership Transfer

请生成推测 ER 图。

## 13. 计费系统逆编译

请根据这个 SaaS 的价格页、设置页面和功能限制逆编译 Billing 结构。

分析：

- Free / Trial
- Pro
- Team
- Enterprise
- Seat 计费
- Usage 计费
- Credit 制
- Monthly / Annual
- Trial 期限
- Upgrade
- Downgrade
- Cancel
- Refund
- Invoice
- Tax
- Coupon
- Overage

进一步识别：

**哪些 Feature / Limit 位于 Paywall 后面**

并整理成使用 Stripe 等服务重建时可采用的 Billing Model。

## 14. Onboarding 逆编译

请逆编译这个 SaaS 的首次使用体验。

分析：

- Sign up
- Welcome
- Persona 选择
- Use Case 选择
- Workspace 创建
- Import
- Integration
- Tutorial
- Checklist
- Sample Data
- Empty State
- First Success

特别说明：

**产品为了缩短 Time to Value 做了什么**

并进一步推断产品方希望通过 Onboarding 获取哪些用户信息。

## 15. Dashboard 逆编译

请逆编译这个 Dashboard 想让用户“理解什么，以及下一步做什么”。

分析：

- Primary KPI
- Secondary KPI
- Summary
- Trend
- Alert
- Recommendation
- Recent Activity
- Task
- CTA
- Filter
- Date Range

将信息优先级分成：

P0 / P1 / P2

## 16. Table / 列表页面逆编译

请完整规格化这个列表页面。

分析：

- Columns
- Column Type
- Sort
- Filter
- Search
- Pagination
- Bulk Action
- Selection
- Row Action
- Inline Edit
- Status
- Link
- Export
- Import
- Saved View
- Column Customization

同时设计以下状态的 UI：

0 条
1 条
大量数据
Loading
Error

## 17. Form 逆编译

请完整规格化这个表单。

针对每个 Field，提取：

- Label
- Field Type
- Placeholder
- Default
- Required
- Validation
- Error Message
- Help Text
- Dependency
- Conditional Display
- Submit Condition

并判断是否需要：

- Auto Save
- Draft
- Dirty State
- Unsaved Changes
- Confirm Dialog

## 18. 搜索功能逆编译

请逆编译这个 SaaS 的搜索 UX。

分析：

- Global Search
- Local Search
- Full Text
- Prefix
- Exact Match
- Fuzzy
- Filter
- Facet
- Sort
- Recent Search
- Search History
- Command Palette

同时推断键盘操作和搜索结果 UI。

## 19. AI SaaS 逆编译

请逆编译这个 AI SaaS。

除常规 SaaS 分析外，根据 UI 推断是否存在：

- Prompt
- System Prompt
- Context
- Memory
- Model
- Temperature
- Tool Calling
- RAG
- Vector Search
- Agent
- Workflow
- Streaming
- Regeneration
- Edit
- Retry
- Model Switching

重要：

不要假装知道内部 Prompt 或非公开实现。

请根据用户可观察到的行为描述：

“如果合理地独立重建，它可能需要怎样的 Architecture？”

## 20. AI Chat UI 逆编译

请逆编译这个 AI Chat 界面。

分析：

- Conversation
- Message
- Role
- Streaming
- Attachment
- Image
- File
- Citation
- Tool Call
- Retry
- Edit
- Branch
- Stop
- Copy
- Feedback
- Context Window
- History
- Delete
- Archive

并设计推测数据模型：

Conversation
Message
Attachment
ToolCall
Citation
Feedback

## 21. AI Agent SaaS 逆编译

请逆编译这个 Agent 型 SaaS 的执行模型。

判断是否存在以下循环：

User Request
↓
Planning
↓
Tool Selection
↓
Tool Execution
↓
Observation
↓
Replanning
↓
Result

同时将以下对象建模为 Entity：

- Task
- Run
- Step
- Tool
- Artifact
- Approval
- Error
- Retry
- Human in the Loop

## 22. API 逆编译

请根据这个 SaaS 的界面操作反推出所需 API。

把每个 UI 操作映射到：

GET
POST
PATCH
DELETE

例如：

显示用户列表
→ GET /users

创建用户
→ POST /users

更新用户
→ PATCH /users/:id

删除
→ DELETE /users/:id

同时生成包含以下内容的 API 规格：

- Request
- Response
- Error
- Pagination
- Filter
- Sort
- Authentication

不要尝试找出真实的私有 API，而是作为：

**实现同等产品体验所需要的 API 设计**

来编写。

## 23. Webhook / Integration 逆编译

请根据这个 SaaS 的 Integration 页面推断外部集成设计。

分析：

- OAuth
- API Key
- Webhook
- Import
- Export
- Sync
- Trigger
- Action
- Mapping

针对每个 Integration，设计：

Connection
↓
Authorization
↓
Configuration
↓
Sync
↓
Error Handling
↓
Disconnect

这一 Lifecycle。

## 24. 通知系统逆编译

请逆编译这个 SaaS 的 Notification System。

推断渠道：

- In-app
- Email
- Push
- Slack
- Webhook

针对每个事件整理：

Event
Recipient
Channel
Template
Trigger
Frequency
Preference

并设计 Notification Preference 页面。

## 25. Activity Log / Audit Log 逆编译

请逆编译这个 SaaS 的历史记录 / Activity 功能。

事件模型：

Actor
Action
Target
Timestamp
Metadata

推断生成类似：

Kai updated Project A

这种事件所需的数据结构。

同时考虑审计日志是否需要：

- IP
- Device
- Before
- After
- Admin Action

## 26. 管理后台逆编译

请根据这个 SaaS 的用户侧功能，反推出运营侧需要的 Admin Console。

可能需要的功能：

- User Management
- Workspace Management
- Billing
- Subscription
- Feature Flag
- Abuse
- Support
- Logs
- Jobs
- Integration
- Content
- Announcement
- Metrics

把普通用户功能与 Admin 专属功能分开。

## 27. 错误设计逆编译

请列出这个 SaaS 可能出现的 Failure State。

例如：

- 400
- 401
- 403
- 404
- 409
- 422
- 429
- 500
- Timeout
- Offline
- Integration Error
- Payment Error

对每个 Error 设计：

Cause
User Message
Recovery Action
Retry
Logging

## 28. Empty State 逆编译

请针对这个 SaaS 的每个相关页面设计“数据尚不存在”的状态。

将 Empty State 分为：

- First Use
- No Search Results
- No Permission
- Deleted
- Filter Result 0

针对每种状态设计：

Title
Description
Illustration
Primary CTA
Secondary CTA

## 29. Responsive / Mobile 逆编译

请从 Desktop 版本反推出 Mobile / Tablet 版本。

分析：

- Sidebar
- Navigation
- Table
- Modal
- Form
- Toolbar
- Card
- Chart

说明它们在：

Desktop → Tablet → Mobile

之间应如何变化。

不要简单缩小尺寸，而要根据优先级设计信息的删除 / 折叠 / 移动。

## 30. Accessibility 逆编译

假设要按 WCAG 意识重建这个 SaaS，请提取必要的 Accessibility 要求。

分析：

- Keyboard
- Focus
- Contrast
- Label
- ARIA
- Screen Reader
- Error
- Modal
- Dropdown
- Table
- Form
- Motion

同时提出在保持 UI 设计的前提下需要的改进。

## 31. Performance 逆编译

请推断为了实现与这个 SaaS 相同的体感速度，需要哪些 Performance 策略。

分析：

- SSR
- CSR
- Streaming
- Lazy Load
- Prefetch
- Cache
- Optimistic UI
- Skeleton
- Pagination
- Infinite Scroll
- Image Optimization
- Code Splitting

不要断言目标 SaaS 实际采用了这些技术，而应提出用于重现可观察 UX 的合理 Architecture。

## 32. Security 逆编译

请根据这个 SaaS 的功能反推出需要的 Security Requirements。

考虑：

- Authentication
- Authorization
- CSRF
- XSS
- SQL Injection
- Rate Limit
- Encryption
- Secrets
- Audit Log
- Session
- API Key
- Webhook Signature
- File Upload
- Tenant Isolation

尤其作为多租户 SaaS，请明确设计：

“绝不能让一个 Workspace 看到另一个 Workspace 的数据。”

## 33. SaaS 商业模式逆编译

请不要只把它当成产品，而是作为 SaaS 商业模式进行逆编译。

分析：

- ICP
- Persona
- JTBD
- Acquisition
- Activation
- Monetization
- Retention
- Expansion
- Referral
- Churn

进一步推断 Expansion Path：

Free → Paid
Individual → Team
Team → Enterprise

## 34. Growth 设计逆编译

请根据这个 SaaS 的 UI、定价、Onboarding、分享功能逆编译 Growth Loop。

寻找：

- Invite Loop
- Content Loop
- Collaboration Loop
- Sharing Loop
- Template Loop
- Integration Loop
- Data Network Effect

每个 Loop 使用：

Trigger
↓
User Action
↓
External Exposure
↓
New User
↓
Activation

来说明循环。

## 35. 营销网站逆编译

请逆编译这个 SaaS 的 LP。

不要只是提取文案，而要分析页面的说服结构。

例如：

Hero
↓
Problem
↓
Value Proposition
↓
Product Demonstration
↓
Use Case
↓
Social Proof
↓
Integration
↓
Pricing
↓
FAQ
↓
CTA

针对每个 Section 说明：

- 读者的心理状态
- 正在传达的 Message
- 使用的 Proof
- 推动用户进入下一 Section 的作用

## 36. 竞品 SaaS 对比逆编译

请用相同框架逆编译 SaaS A 和 SaaS B 并进行比较。

比较维度：

- Target User
- JTBD
- IA
- Core Feature
- Workflow
- UX
- Design
- Collaboration
- AI
- Integration
- Pricing
- Growth Loop
- Moat

最后不要停留在“功能差异”，而要比较：

**每个产品向用户提出了怎样的世界观和工作方式。**

## 37. MVP 逆编译

不要完整复制这个 SaaS，而是设计一个用 20% 功能复现 80% 价值的 MVP。

把所有功能分为：

- P0：没有它价值就不成立
- P1：重要，但可以之后补充
- P2：适合成熟 SaaS
- P3：本次不需要

然后定义：

- 最小数据模型
- 最小页面
- 最小 API
- 最小用户流程

## 38. 一周重建版本

假设需要在一周内重建这个 SaaS 的核心体验。

限制：

- 1～2 名工程师
- 仅 Web 版
- 不要求完美复刻
- 核心体验优先

制定 Day 1 到 Day 7 的实现计划。

能由外部 SaaS 替代的通用功能，请积极使用外部服务。

## 39. 面向 AI Coding Agent 的逆编译

请把这个 SaaS 转换成 AI Coding Agent 可以执行的实现规格。

禁止模糊描述。

生成：

1. Product Overview
2. User Stories
3. Routes
4. Screen Specification
5. Component Tree
6. Data Model
7. API
8. State
9. Permission
10. Validation
11. Error Handling
12. Responsive Behavior
13. Acceptance Criteria
14. Test Cases
15. Implementation Order

针对每个功能，用：

Given
When
Then

格式补充 Acceptance Criteria。

## 40. 完整重建 Master Prompt

请以“根据可观察的产品规格进行重建”为目标，彻底逆编译以下 SaaS。

对象：
[URL / 截图 / 视频 / 描述]

请同时扮演：

- Product Manager
- UX Researcher
- UI Designer
- Design System Designer
- Frontend Architect
- Backend Architect
- Database Designer
- Security Engineer
- Growth Product Manager
- QA Engineer

目标不是窃取目标服务的代码。

**目标是根据可观察 UX，生成能够独立实现同等用户价值的规格。**

请严格按以下顺序分析：

### A. Product

- Problem
- Target User
- JTBD
- Value Proposition
- Core Loop

### B. Information Architecture

- Sitemap
- Navigation
- Page Hierarchy

### C. Features

将全部功能按：

P0 / P1 / P2 / P3

分类。

### D. Screen Specification

针对每个页面记录：

- Purpose
- Input
- Output
- Action
- State
- Error
- Permission

### E. User Flow

主要 JTBD 的 End-to-End Flow。

### F. UI System

- Color
- Typography
- Spacing
- Grid
- Component
- State

### G. Data Model

- Entity
- Field
- Relation
- Constraint

### H. Business Logic

使用 Rule 格式描述。

### I. API

定义支撑 UI 所需的 API。

### J. Authentication / Authorization

- User
- Workspace
- Role
- Permission

### K. Billing

- Plan
- Limit
- Usage
- Upgrade
- Downgrade

### L. External Integration

- OAuth
- API
- Webhook

### M. Non-functional Requirement

- Security
- Performance
- Accessibility
- Reliability

### N. Analytics

定义主要事件，例如：

- Viewed
- Clicked
- Created
- Updated
- Deleted
- Invited
- Upgraded
- Completed

### O. MVP

提取最小可行结构。

### P. Implementation

提出推荐技术架构和实现顺序。

### Q. Test

定义 Acceptance Criteria 与 E2E Test。

---

# 最重要规则

在 SaaS 逆编译中，不要混淆以下三种类型。

## ① Observation

实际可以确认的事实。

例如：

“页面右上角存在 Invite 按钮。”

## ② Inference

可以从观察结果合理推断出的内容。

例如：

“很可能可以邀请其他用户加入 Workspace。”

## ③ Speculation

证据不足的假设。

例如：

“邀请 Token 的有效期可能是 24 小时。”

必须始终区分这三类。

# SaaS 逆编译的基本原则

优秀的逆编译会按以下顺序不断提升抽象层级：

**Pixel → Component → Screen → Flow → Feature → Data → Rule → System → Business**

不要只看图片本身。

存在 Button
↓
意味着存在 Action
↓
State 会变化
↓
Data 会变化
↓
存在 Business Rule
↓
用户的工作最终被完成

要一直追踪这条因果链。

最终目标不是复制“这个 SaaS 的按钮是什么颜色”，而是能够重建：

**为什么这个 SaaS 最终会形成现在这样的产品结构。**
