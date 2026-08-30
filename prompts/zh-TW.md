# SaaS Decompiler — 繁體中文提示詞集

這裡所說的 SaaS 逆編譯，是指從公開網站、實際可操作的產品畫面、截圖、URL、公開文件等可觀察資訊中，反推出該 SaaS 的設計思想與結構。

## 1. 通用 SaaS 逆編譯

請完整逆編譯這個 SaaS。

不要停留在表面的 UI 描述，而要將它結構化到可以從零重建該產品的程度。

請分析：

- SaaS 解決的問題
- 目標使用者
- JTBD（使用者想完成的工作）
- 核心價值
- 主要使用情境
- 畫面結構
- 資訊架構
- 導覽
- 功能清單
- 使用者流程
- 狀態轉換
- 資料結構
- 權限結構
- 商業規則
- UI 設計系統
- 元件結構
- 可能需要透過 API 提供的功能
- 外部服務整合
- 計費模型
- Onboarding
- 留存設計
- 錯誤處理
- 空狀態
- 通知
- 搜尋
- 篩選
- 管理後台
- 安全所需設計
- 非功能需求
- 實作優先順序

最後請分離：

1. 可直接觀察到的事實
2. 高可信度可推論的設計
3. 僅屬於推測的部分
4. 重建時可以省略的部分
5. MVP 絕對必需的部分

## 2. 從截圖逆編譯 SaaS

請根據附加的 SaaS 截圖逆編譯這個產品的結構。

不要只是描述圖中出現了什麼，而要進一步推論：

「既然這個畫面存在，那麼背後必須有哪些功能、資料、狀態與規則？」

分析對象：

- 頁面目的
- 頁面層級
- 全域導覽
- 區域導覽
- UI 元件
- 可互動元素
- CRUD 操作
- 列表 / 詳細 / 編輯之間的關係
- 資料欄位
- 資料型別
- 資料之間的關係
- 篩選
- 排序
- 搜尋
- 分頁
- 狀態
- 權限
- Modal
- Drawer
- Toast
- 空狀態
- Loading
- Error 狀態
- 使用者操作造成的狀態變化

每個要素請使用：

**畫面上的證據 → 推論出的規格**

這種格式輸出。

## 3. 從 URL 逆編譯整個 SaaS

請從這個 URL 出發，在可存取範圍內探索整個網站並逆編譯該 SaaS。

不要只看單一頁面，盡可能橫向檢查：

- 首頁
- 註冊
- 登入
- Onboarding
- Dashboard
- 設定
- 計費
- 說明
- 文件
- FAQ
- 服務條款
- 隱私權政策
- 已公開的功能介紹

然後把：

**行銷網站承諾的價值**

與

**產品實際提供的功能**

分開。

最終生成一份足以重建該 SaaS 的 Product Requirements Document 等級規格。

## 4. UI / UX 逆編譯

請詳細逆編譯這個 SaaS 的 UI / UX 設計。

### 版面配置

- 最大寬度
- Grid
- Sidebar 寬度
- Header 高度
- 欄結構
- 間距規則
- 內容密度

### Typography

- 字體類別
- 字級層級
- 字重
- 行高
- 標題層級
- 數字顯示方式

### 顏色

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

### 元件

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

對每個元件推論：

- 外觀
- 尺寸
- Variant
- State
- Hover
- Focus
- Disabled
- Loading
- Error

最後彙整成可用於重現的 Design Tokens。

## 5. 設計系統逆編譯

請從這個 SaaS 中提取設計系統。

不要複製某一個頁面，而是尋找多個頁面共同遵守的規則。

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

如果某個值無法直接確認，請明確標註為：

「根據視覺外觀推測的值」。

如果可能，請整理成能夠轉換為 CSS Variables / Tailwind Theme / Design Tokens 的格式。

## 6. 前端結構逆編譯

請以前端工程師的視角逆編譯這個 SaaS。

假設使用 React / Next.js 等技術重建畫面，請拆分為：

- Layout
- Page
- Feature
- Component
- UI Primitive

推論：

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

最後生成建議目錄結構。

不要斷言目標 SaaS 實際使用了某種內部技術，而應作為：

「如果要合理重建，可以採用的結構」

來提出建議。

## 7. 資料模型逆編譯

請從這個 SaaS 的 UI 反推出背後的資料模型。

從畫面中可見的以下概念等提取 Entity：

- 名稱
- ID
- 使用者
- 團隊
- Workspace
- Project
- Status
- Tag
- Date
- Owner
- Permission
- Relation

對每個 Entity 推論：

- Entity 名稱
- 作用
- Field
- Data Type
- Required / Optional
- Relation
- Unique Constraint
- Index 候選
- Lifecycle

最終整理成可轉換為：

- ER 圖
- SQL Schema
- Prisma Schema 或同等結構

的形式。

所有推論部分都必須標註可信度。

## 8. 使用者流程逆編譯

請逆編譯使用者在這個 SaaS 中實現目標的完整操作過程。

針對每個主要 JTBD，按以下格式寫出流程：

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

同時推論以下分支：

- Happy Path
- 首次使用者
- 回訪使用者
- 資料 0 筆
- 輸入錯誤
- 權限不足
- 網路錯誤
- 取消
- 刪除
- 復原

## 9. 狀態轉換逆編譯

請反推出這個 SaaS 中主要物件的 State Machine。

例如：

Draft
↓
Processing
↓
Completed

根據 UI 上的 Badge、Button、Menu、顯示切換等資訊推論狀態。

對每個狀態整理：

- State
- Entry Condition
- Allowed Action
- Forbidden Action
- Next State
- Rollback
- UI Representation

## 10. 商業邏輯逆編譯

請從這個 SaaS 的 UI 推論背後的商業規則。

不要只看 CRUD，而要分析：

「為什麼這個按鈕只在這個條件下顯示？」

「為什麼這筆資料不能編輯？」

「為什麼會進入這個狀態？」

按以下格式輸出：

RULE-001

條件：
WHEN ...

處理：
THEN ...

例外：
EXCEPT ...

UI 上的證據：

可信度：
High / Medium / Low

## 11. 驗證 / 權限逆編譯

請逆編譯這個 SaaS 的 Authentication / Authorization 設計。

推論：

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

判斷 RBAC 或 ABAC 哪一種更適合。

角色範例：

- Owner
- Admin
- Member
- Viewer
- Guest

針對每個 Role，將 View / Create / Edit / Delete / Invite / Billing / Admin 權限做成矩陣。

## 12. Workspace / Team 結構逆編譯

請逆編譯這個 SaaS 的帳戶結構。

重點分析 User / Organization / Workspace / Team / Project 之間的關係。

確認：

- 一個使用者是否可以屬於多個 Workspace
- 是否存在 Workspace 切換
- 邀請功能
- Role
- Ownership
- Seat
- Billing 單位
- Data Isolation
- Workspace 刪除
- Ownership Transfer

請生成推測 ER 圖。

## 13. 計費系統逆編譯

請根據這個 SaaS 的價格頁、設定頁面與功能限制逆編譯 Billing 結構。

分析：

- Free / Trial
- Pro
- Team
- Enterprise
- Seat 計費
- Usage 計費
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

進一步識別：

**哪些 Feature / Limit 位於 Paywall 後面**

並整理成使用 Stripe 等服務重建時可採用的 Billing Model。

## 14. Onboarding 逆編譯

請逆編譯這個 SaaS 的首次使用體驗。

分析：

- Sign up
- Welcome
- Persona 選擇
- Use Case 選擇
- Workspace 建立
- Import
- Integration
- Tutorial
- Checklist
- Sample Data
- Empty State
- First Success

特別說明：

**產品為了縮短 Time to Value 做了什麼**

並進一步推論產品方希望透過 Onboarding 取得哪些使用者資訊。

## 15. Dashboard 逆編譯

請逆編譯這個 Dashboard 想讓使用者「理解什麼，以及下一步做什麼」。

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

將資訊優先順序分成：

P0 / P1 / P2

## 16. Table / 列表頁面逆編譯

請完整規格化這個列表頁面。

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

同時設計以下狀態的 UI：

0 筆
1 筆
大量資料
Loading
Error

## 17. Form 逆編譯

請完整規格化這個表單。

針對每個 Field，提取：

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

並判斷是否需要：

- Auto Save
- Draft
- Dirty State
- Unsaved Changes
- Confirm Dialog

## 18. 搜尋功能逆編譯

請逆編譯這個 SaaS 的搜尋 UX。

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

同時推論鍵盤操作與搜尋結果 UI。

## 19. AI SaaS 逆編譯

請逆編譯這個 AI SaaS。

除了一般 SaaS 分析外，根據 UI 推論是否存在：

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

不要假裝知道內部 Prompt 或非公開實作。

請根據使用者可觀察到的行為描述：

「如果合理地獨立重建，它可能需要怎樣的 Architecture？」

## 20. AI Chat UI 逆編譯

請逆編譯這個 AI Chat 畫面。

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

並設計推測資料模型：

Conversation
Message
Attachment
ToolCall
Citation
Feedback

## 21. AI Agent SaaS 逆編譯

請逆編譯這個 Agent 型 SaaS 的執行模型。

判斷是否存在以下循環：

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

同時將以下物件建模為 Entity：

- Task
- Run
- Step
- Tool
- Artifact
- Approval
- Error
- Retry
- Human in the Loop

## 22. API 逆編譯

請根據這個 SaaS 的畫面操作反推出所需 API。

把每個 UI 操作對應到：

GET
POST
PATCH
DELETE

例如：

顯示使用者列表
→ GET /users

建立使用者
→ POST /users

更新使用者
→ PATCH /users/:id

刪除
→ DELETE /users/:id

同時生成包含以下內容的 API 規格：

- Request
- Response
- Error
- Pagination
- Filter
- Sort
- Authentication

不要嘗試找出真實的私有 API，而是作為：

**實現同等產品體驗所需要的 API 設計**

來撰寫。

## 23. Webhook / Integration 逆編譯

請根據這個 SaaS 的 Integration 畫面推論外部整合設計。

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

針對每個 Integration，設計：

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

這個 Lifecycle。

## 24. 通知系統逆編譯

請逆編譯這個 SaaS 的 Notification System。

推論渠道：

- In-app
- Email
- Push
- Slack
- Webhook

針對每個事件整理：

Event
Recipient
Channel
Template
Trigger
Frequency
Preference

並設計 Notification Preference 畫面。

## 25. Activity Log / Audit Log 逆編譯

請逆編譯這個 SaaS 的歷史記錄 / Activity 功能。

事件模型：

Actor
Action
Target
Timestamp
Metadata

推論產生例如：

Kai updated Project A

這種事件所需的資料結構。

同時考慮稽核日誌是否需要：

- IP
- Device
- Before
- After
- Admin Action

## 26. 管理後台逆編譯

請根據這個 SaaS 的使用者端功能，反推出營運側需要的 Admin Console。

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

把一般使用者功能與 Admin 專屬功能分開。

## 27. 錯誤設計逆編譯

請列出這個 SaaS 可能出現的 Failure State。

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

對每個 Error 設計：

Cause
User Message
Recovery Action
Retry
Logging

## 28. Empty State 逆編譯

請針對這個 SaaS 的每個相關頁面設計「資料尚不存在」的狀態。

將 Empty State 分為：

- First Use
- No Search Results
- No Permission
- Deleted
- Filter Result 0

針對每種狀態設計：

Title
Description
Illustration
Primary CTA
Secondary CTA

## 29. Responsive / Mobile 逆編譯

請從 Desktop 版本反推出 Mobile / Tablet 版本。

分析：

- Sidebar
- Navigation
- Table
- Modal
- Form
- Toolbar
- Card
- Chart

說明它們在：

Desktop → Tablet → Mobile

之間應如何變化。

不要只是縮小尺寸，而要根據優先順序設計資訊的刪除 / 折疊 / 移動。

## 30. Accessibility 逆編譯

假設要依照 WCAG 意識重建這個 SaaS，請提取必要的 Accessibility 要求。

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

同時提出在維持 UI 設計前提下需要的改善。

## 31. Performance 逆編譯

請推論為了實現與這個 SaaS 相同的體感速度，需要哪些 Performance 策略。

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

不要斷言目標 SaaS 實際採用了這些技術，而應提出用於重現可觀察 UX 的合理 Architecture。

## 32. Security 逆編譯

請根據這個 SaaS 的功能反推出所需 Security Requirements。

考慮：

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

尤其作為多租戶 SaaS，請明確設計：

「絕不能讓一個 Workspace 看到另一個 Workspace 的資料。」

## 33. SaaS 商業模式逆編譯

請不要只把它當成產品，而是作為 SaaS 商業模式進行逆編譯。

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

進一步推論 Expansion Path：

Free → Paid
Individual → Team
Team → Enterprise

## 34. Growth 設計逆編譯

請根據這個 SaaS 的 UI、定價、Onboarding、分享功能逆編譯 Growth Loop。

尋找：

- Invite Loop
- Content Loop
- Collaboration Loop
- Sharing Loop
- Template Loop
- Integration Loop
- Data Network Effect

每個 Loop 使用：

Trigger
↓
User Action
↓
External Exposure
↓
New User
↓
Activation

來說明循環。

## 35. 行銷網站逆編譯

請逆編譯這個 SaaS 的 LP。

不要只是提取文案，而要分析頁面的說服結構。

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

針對每個 Section 說明：

- 讀者的心理狀態
- 正在傳達的 Message
- 使用的 Proof
- 推動使用者進入下一 Section 的作用

## 36. 競品 SaaS 對比逆編譯

請用相同框架逆編譯 SaaS A 和 SaaS B 並進行比較。

比較維度：

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

最後不要停留在「功能差異」，而要比較：

**每個產品向使用者提出了怎樣的世界觀與工作方式。**

## 37. MVP 逆編譯

不要完整複製這個 SaaS，而是設計一個用 20% 功能重現 80% 價值的 MVP。

把所有功能分為：

- P0：沒有它價值就不成立
- P1：重要，但可以之後補充
- P2：適合成熟 SaaS
- P3：本次不需要

然後定義：

- 最小資料模型
- 最小頁面
- 最小 API
- 最小使用者流程

## 38. 一週重建版本

假設需要在一週內重建這個 SaaS 的核心體驗。

限制：

- 1～2 名工程師
- 僅 Web 版
- 不要求完美重現
- 核心體驗優先

制定 Day 1 到 Day 7 的實作計畫。

能由外部 SaaS 替代的通用功能，請積極使用外部服務。

## 39. 面向 AI Coding Agent 的逆編譯

請把這個 SaaS 轉換成 AI Coding Agent 可以執行的實作規格。

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

針對每個功能，用：

Given
When
Then

格式補充 Acceptance Criteria。

## 40. 完整重建 Master Prompt

請以「根據可觀察的產品規格進行重建」為目標，徹底逆編譯以下 SaaS。

對象：
[URL / 截圖 / 影片 / 描述]

請同時扮演：

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

目標不是竊取目標服務的程式碼。

**目標是根據可觀察 UX，生成能夠獨立實現同等使用者價值的規格。**

請嚴格按以下順序分析：

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

將全部功能按：

P0 / P1 / P2 / P3

分類。

### D. Screen Specification

針對每個畫面記錄：

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

定義支撐 UI 所需的 API。

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

定義主要事件，例如：

- Viewed
- Clicked
- Created
- Updated
- Deleted
- Invited
- Upgraded
- Completed

### O. MVP

提取最小可行結構。

### P. Implementation

提出建議技術架構與實作順序。

### Q. Test

定義 Acceptance Criteria 與 E2E Test。

---

# 最重要規則

在 SaaS 逆編譯中，不要混淆以下三種類型。

## ① Observation

實際可以確認的事實。

例如：

「畫面右上角存在 Invite 按鈕。」

## ② Inference

可以從觀察結果合理推論出的內容。

例如：

「很可能可以邀請其他使用者加入 Workspace。」

## ③ Speculation

證據不足的假設。

例如：

「邀請 Token 的有效期可能是 24 小時。」

必須始終區分這三類。

# SaaS 逆編譯的基本原則

優秀的逆編譯會按以下順序不斷提高抽象層級：

**Pixel → Component → Screen → Flow → Feature → Data → Rule → System → Business**

不要只看圖片本身。

存在 Button
↓
意味著存在 Action
↓
State 會變化
↓
Data 會變化
↓
存在 Business Rule
↓
使用者的工作最終被完成

要一路追蹤這條因果鏈。

最終目標不是複製「這個 SaaS 的按鈕是什麼顏色」，而是能夠重建：

**為什麼這個 SaaS 最終會形成現在這樣的產品結構。**
