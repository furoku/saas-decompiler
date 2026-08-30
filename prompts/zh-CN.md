# SaaS Decompiler — 简体中文提示词集

> 用于从公开页面、截图、可实际操作的产品界面与公开文档等可观察信息，反推出 SaaS 结构并整理成可独立实现规格的提示词集。目的不是取得非公开源代码、秘密信息或绕过验证。

## 1. 通用 SaaS 逆编译
完整逆编译这个 SaaS。不要只描述 UI，请重建它解决的问题、目标用户、JTBD、价值主张、主要使用场景、界面、信息架构、功能、用户流程、状态转换、数据模型、权限、业务规则、设计系统、API、外部集成、计费、Onboarding、通知、搜索、管理后台、安全性、非功能需求与实现优先级。最后分成「观察事实 / 高可信推断 / 低可信假设 / MVP 必要 / 可省略」。

## 2. 从截图逆编译
根据附加截图，推断页面目的、层级、导航、UI 组件、操作、CRUD、列表/详细/编辑关系、数据字段、筛选、排序、搜索、分页、状态、权限、Modal、空状态、Loading、错误与状态变化。使用「界面证据 → 推断规格 → 可信度」输出。

## 3. 从 URL 逆编译整个 SaaS
从这个 URL 开始，在公开可访问范围内检查首页、注册、登录、Onboarding、Dashboard、设置、计费、说明、文档、FAQ、条款、隐私与功能介绍。分离「营销网站承诺的价值」与「实际可观察的产品功能」，最后整理成 PRD 级别的重建规格。

## 4. UI / UX 逆编译
分析 Layout、最大宽度、Grid、Sidebar、Header、Spacing、信息密度、Typography、Color，以及 Button/Input/Select/Table/Card/Badge/Modal/Drawer/Toast 等组件与各种 State，整理为可复用的 Design Tokens。

## 5. 设计系统逆编译
从多个界面提取共同规则：Color、Typography、Spacing、Radius、Border、Shadow、Z-index、Icon、Grid、Breakpoint、Motion、Component Variant、Interaction State。无法直接确认的值标记为估算值，并整理成可转换为 CSS Variables 或 Tailwind Theme 的格式。

## 6. 前端架构逆编译
假设要独立重建此 SaaS，将其拆成 Layout / Page / Feature / Component / UI Primitive。设计 Routing、Nested Layout、Shared Components、State Management、Server/Local/Form State、Optimistic Update、Cache、Pagination、Search Params、URL State，并提出建议目录结构。

## 7. 数据模型逆编译
从界面上的名称、ID、User、Team、Workspace、Project、Status、Tag、Date、Owner、Permission、Relation 等提取 Entity。为每个 Entity 定义 Field、Type、Required/Optional、Relation、Unique Constraint、Index 候选、Lifecycle，并整理成可转换为 ERD、SQL 或 Prisma Schema 的形式。

## 8. 用户流程逆编译
针对主要 JTBD 建立 Start → Action → System Response → Decision → Next Action → Success 流程。包含 Happy Path、首次用户、回访用户、0 笔数据、输入错误、权限不足、网络错误、取消、删除、恢复等分支。

## 9. 状态机逆编译
反推出主要对象的 State Machine。每个 State 都记录 Entry Condition、Allowed Action、Forbidden Action、Next State、Rollback、UI Representation。

## 10. 业务逻辑逆编译
从 UI 推断「为何按钮只在特定条件出现」「为何某些数据不可编辑」「为何会变成这个状态」。使用 RULE-001 格式记录 WHEN / THEN / EXCEPT / UI 证据 / 可信度。

## 11. 认证与权限逆编译
推断 Signup、Login、OAuth、Magic Link、Password Reset、Email Verification、MFA、Session、Organization、Workspace、Team、Role、Permission。判断 RBAC 或 ABAC 哪个更适合，并建立 Owner/Admin/Member/Viewer/Guest 等角色权限矩阵。

## 12. Workspace / Team 结构逆编译
分析 User / Organization / Workspace / Team / Project 的关系。包含多 Workspace 成员关系、切换、邀请、Role、Ownership、Seat、计费单位、Data Isolation、删除、Ownership Transfer，并输出推测 ERD。

## 13. 计费系统逆编译
从价格页、设置与功能限制推断 Free/Trial/Pro/Team/Enterprise、Seat/Usage/Credit 计费、Monthly/Annual、Trial、Upgrade、Downgrade、Cancel、Invoice、Tax、Coupon、Overage。找出 Paywall 的功能/限制并设计独立实现的 Billing Model。

## 14. Onboarding 逆编译
分析 Signup、Welcome、Persona/Use Case 选择、Workspace 建立、Import、Integration、Tutorial、Checklist、Sample Data、Empty State、First Success。说明如何缩短 Time to Value，并推断产品想收集哪些用户信息。

## 15. Dashboard 逆编译
分析这个 Dashboard 想让用户理解什么、接下来做什么。将 Primary KPI、Secondary KPI、Summary、Trend、Alert、Recommendation、Recent Activity、Task、CTA、Filter、Date Range 分成 P0/P1/P2。

## 16. Table / 列表逆编译
规格化 Columns、Type、Sort、Filter、Search、Pagination、Bulk Action、Selection、Row Action、Inline Edit、Status、Link、Export/Import、Saved View、Column Customization，并设计 0 笔/1 笔/大量/Loading/Error 状态。

## 17. Form 逆编译
针对每个 Field 推断 Label、Type、Placeholder、Default、Required、Validation、Error Message、Help Text、Dependency、Conditional Display、Submit Condition。判断 Auto Save、Draft、Dirty State、Unsaved Changes、Confirm Dialog 是否需要。

## 18. 搜索逆编译
分析 Global/Local Search、Full Text、Prefix、Exact Match、Fuzzy、Filter、Facet、Sort、Recent Search、History、Command Palette，并设计键盘操作与搜索结果 UI。

## 19. AI SaaS 逆编译
除了标准 SaaS 分析，从可观察行为推断 Prompt、System Prompt、Context、Memory、Model、Temperature、Tool Calling、RAG、Vector Search、Agent、Workflow、Streaming、Regeneration、Edit、Retry、Model Switching。不要假装知道隐藏实现，请描述合理的独立 Architecture。

## 20. AI Chat UI 逆编译
分析 Conversation、Message、Role、Streaming、Attachment、Image、File、Citation、Tool Call、Retry、Edit、Branch、Stop、Copy、Feedback、History、Delete、Archive，并设计 Conversation/Message/Attachment/ToolCall/Citation/Feedback 的推测数据模型。

## 21. AI Agent SaaS 逆编译
判断是否存在 User Request → Planning → Tool Selection → Tool Execution → Observation → Replanning → Result 的循环。将 Task、Run、Step、Tool、Artifact、Approval、Error、Retry、Human in the Loop 建模为 Entity。

## 22. API 逆编译
设计复现可观察 UX 所需要的 API。将操作映射到 GET/POST/PATCH/DELETE，并定义 Request、Response、Error、Pagination、Filter、Sort、Authentication。不要找实际私有 Endpoint，而是做独立实现的 API 规格。

## 23. Webhook / Integration 逆编译
从集成界面推断 OAuth、API Key、Webhook、Import、Export、Sync、Trigger、Action、Mapping。设计 Connection → Authorization → Configuration → Sync → Error Handling → Disconnect 的 Lifecycle。

## 24. 通知系统逆编译
推断 In-app、Email、Push、Slack、Webhook 等渠道，整理 Event、Recipient、Channel、Template、Trigger、Frequency、Preference，并设计 Notification Preference 界面。

## 25. Activity Log / Audit Log 逆编译
设计 Actor、Action、Target、Timestamp、Metadata 的事件模型，并评估审计用途是否需要 IP、Device、Before、After、Admin Action。

## 26. 管理后台逆编译
从前台功能反推出内部 Admin Console。考虑 User、Workspace、Billing、Subscription、Feature Flag、Abuse、Support、Logs、Jobs、Integration、Content、Announcement、Metrics，并与普通用户功能分离。

## 27. 错误设计逆编译
列出 400/401/403/404/409/422/429/500、Timeout、Offline、Integration Error、Payment Error 等可能失败状态。为每一种定义 Cause、User Message、Recovery Action、Retry、Logging。

## 28. Empty State 逆编译
为各相关页面设计 First Use、No Search Results、No Permission、Deleted、Filter Result 0，并定义 Title、Description、Illustration、Primary CTA、Secondary CTA。

## 29. Responsive / Mobile 逆编译
从 Desktop 推断 Tablet/Mobile。针对 Sidebar、Navigation、Table、Modal、Form、Toolbar、Card、Chart，不要只缩小尺寸，而是按信息优先级设计隐藏、折叠、移动。

## 30. Accessibility 逆编译
检查 Keyboard、Focus、Contrast、Label、ARIA、Screen Reader、Error、Modal、Dropdown、Table、Form、Motion，提出符合 WCAG 思路的独立实现需求。

## 31. Performance 逆编译
为复现相同体感速度，评估 SSR、CSR、Streaming、Lazy Load、Prefetch、Cache、Optimistic UI、Skeleton、Pagination、Infinite Scroll、Image Optimization、Code Splitting。不要断言原产品实际使用这些技术。

## 32. Security 逆编译
设计 Authentication、Authorization、CSRF、XSS、SQL Injection、Rate Limit、Encryption、Secrets、Audit Log、Session、API Key、Webhook Signature、File Upload、Tenant Isolation 等需求，特别明确定义多租户数据隔离。

## 33. SaaS 商业模式逆编译
分析 ICP、Persona、JTBD、Acquisition、Activation、Monetization、Retention、Expansion、Referral、Churn，并推断 Free → Paid → Team → Enterprise 的 Expansion Path。

## 34. Growth 设计逆编译
寻找 Invite、Content、Collaboration、Sharing、Template、Integration、Data Network Effect 等 Growth Loop，并用 Trigger → User Action → External Exposure → New User → Activation 说明。

## 35. 营销网站逆编译
分析 Hero → Problem → Value Proposition → Product Demonstration → Use Case → Social Proof → Integration → Pricing → FAQ → CTA 的说服结构。说明每个 Section 的读者心理、Message、Proof 与推进作用。

## 36. 竞品 SaaS 比较逆编译
用同一框架比较 SaaS A/B 的 Target User、JTBD、IA、Core Feature、Workflow、UX、Design、Collaboration、AI、Integration、Pricing、Growth Loop、Moat。最后比较两者提出的工作方式与产品世界观。

## 37. MVP 逆编译
设计用约 20% 功能复现约 80% 用户价值的 MVP。将所有功能分类成 P0/P1/P2/P3，再定义最小 Data Model、Screens、APIs、User Flows。

## 38. 一周完成版本
假设 1–2 位工程师、Web only、1 周、不需要完美还原，规划 Day 1–Day 7。可安全交给外部 SaaS 的通用功能就外包，聚焦核心体验。

## 39. 给 AI Coding Agent 的逆编译
转换成 AI Coding Agent 可直接实现的规格：Product Overview、User Stories、Routes、Screen Spec、Component Tree、Data Model、API、State、Permission、Validation、Error Handling、Responsive、Acceptance Criteria、Test Cases、Implementation Order。每个功能加入 Given/When/Then。

## 40. 完整重建 Master Prompt
为了独立重建以下 SaaS 的可观察产品行为，进行完整分析。对象：[URL / 截图 / 视频 / 说明]。同时扮演 Product Manager、UX Researcher、UI Designer、Design System Designer、Frontend/Backend Architect、Database Designer、Security Engineer、Growth PM、QA Engineer，按顺序输出 A.Product、B.IA、C.Features(P0-P3)、D.Screen Spec、E.User Flow、F.UI System、G.Data Model、H.Business Logic、I.API、J.Auth、K.Billing、L.Integration、M.Non-functional、N.Analytics、O.MVP、P.Implementation、Q.Test。

---

## 最重要规则

不要混淆以下三类：

- **Observation**：可直接确认的事实
- **Inference**：从证据合理推断出的设计
- **Speculation**：证据不足的假设

优秀的逆编译会按 **Pixel → Component → Screen → Flow → Feature → Data → Rule → System → Business** 的顺序提高抽象层级。
