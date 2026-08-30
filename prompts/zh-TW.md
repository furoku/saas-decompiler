# SaaS Decompiler — 繁體中文提示詞集

> 用於從公開頁面、截圖、可實際操作的產品畫面與公開文件等可觀察資訊，反推出 SaaS 結構並整理成可獨立實作規格的提示詞集。目的不是取得非公開原始碼、秘密資訊或繞過驗證。

## 1. 通用 SaaS 逆編譯
完整逆編譯這個 SaaS。不要只描述 UI，請重建它解決的問題、目標使用者、JTBD、價值主張、主要使用情境、畫面、資訊架構、功能、使用者流程、狀態轉換、資料模型、權限、商業規則、設計系統、API、外部整合、計費、Onboarding、通知、搜尋、管理後台、安全性、非功能需求與實作優先順序。最後分成「觀察事實 / 高可信推論 / 低可信假設 / MVP 必要 / 可省略」。

## 2. 從截圖逆編譯
根據附加截圖，推論頁面目的、層級、導覽、UI 元件、操作、CRUD、列表/詳細/編輯關係、資料欄位、篩選、排序、搜尋、分頁、狀態、權限、Modal、空狀態、Loading、錯誤與狀態變化。使用「畫面證據 → 推論規格 → 可信度」輸出。

## 3. 從 URL 逆編譯整個 SaaS
從這個 URL 開始，在公開可存取範圍內檢查首頁、註冊、登入、Onboarding、Dashboard、設定、計費、說明、文件、FAQ、條款、隱私與功能介紹。分離「行銷網站承諾的價值」與「實際可觀察的產品功能」，最後整理成 PRD 等級的重建規格。

## 4. UI / UX 逆編譯
分析 Layout、最大寬度、Grid、Sidebar、Header、Spacing、資訊密度、Typography、Color，以及 Button/Input/Select/Table/Card/Badge/Modal/Drawer/Toast 等元件與各種 State，整理為可重用的 Design Tokens。

## 5. 設計系統逆編譯
從多個畫面抽出共通規則：Color、Typography、Spacing、Radius、Border、Shadow、Z-index、Icon、Grid、Breakpoint、Motion、Component Variant、Interaction State。無法直接確認的值標示為推估值，並整理成可轉為 CSS Variables 或 Tailwind Theme 的格式。

## 6. 前端架構逆編譯
假設要獨立重建此 SaaS，將其拆成 Layout / Page / Feature / Component / UI Primitive。設計 Routing、Nested Layout、Shared Components、State Management、Server/Local/Form State、Optimistic Update、Cache、Pagination、Search Params、URL State，並提出建議目錄結構。

## 7. 資料模型逆編譯
從畫面上的名稱、ID、User、Team、Workspace、Project、Status、Tag、Date、Owner、Permission、Relation 等抽出 Entity。為每個 Entity 定義 Field、Type、Required/Optional、Relation、Unique Constraint、Index 候選、Lifecycle，並整理成可轉為 ERD、SQL 或 Prisma Schema 的形式。

## 8. 使用者流程逆編譯
針對主要 JTBD 建立 Start → Action → System Response → Decision → Next Action → Success 流程。包含 Happy Path、首次使用者、回訪使用者、0 筆資料、輸入錯誤、權限不足、網路錯誤、取消、刪除、還原等分支。

## 9. 狀態機逆編譯
反推出主要物件的 State Machine。每個 State 都記錄 Entry Condition、Allowed Action、Forbidden Action、Next State、Rollback、UI Representation。

## 10. 商業邏輯逆編譯
從 UI 推論「為何按鈕只在特定條件出現」「為何某些資料不可編輯」「為何會變成這個狀態」。使用 RULE-001 格式記錄 WHEN / THEN / EXCEPT / UI 證據 / 可信度。

## 11. 驗證與權限逆編譯
推論 Signup、Login、OAuth、Magic Link、Password Reset、Email Verification、MFA、Session、Organization、Workspace、Team、Role、Permission。判斷 RBAC 或 ABAC 哪個更適合，並建立 Owner/Admin/Member/Viewer/Guest 等角色權限矩陣。

## 12. Workspace / Team 結構逆編譯
分析 User / Organization / Workspace / Team / Project 的關係。包含多 Workspace 成員資格、切換、邀請、Role、Ownership、Seat、計費單位、Data Isolation、刪除、Ownership Transfer，並產出推估 ERD。

## 13. 計費系統逆編譯
從價格頁、設定與功能限制推論 Free/Trial/Pro/Team/Enterprise、Seat/Usage/Credit 計費、Monthly/Annual、Trial、Upgrade、Downgrade、Cancel、Invoice、Tax、Coupon、Overage。找出 Paywall 的功能/限制並設計獨立實作的 Billing Model。

## 14. Onboarding 逆編譯
分析 Signup、Welcome、Persona/Use Case 選擇、Workspace 建立、Import、Integration、Tutorial、Checklist、Sample Data、Empty State、First Success。說明如何縮短 Time to Value，並推論產品想蒐集哪些使用者資訊。

## 15. Dashboard 逆編譯
分析這個 Dashboard 想讓使用者理解什麼、接下來做什麼。將 Primary KPI、Secondary KPI、Summary、Trend、Alert、Recommendation、Recent Activity、Task、CTA、Filter、Date Range 分成 P0/P1/P2。

## 16. Table / 列表逆編譯
規格化 Columns、Type、Sort、Filter、Search、Pagination、Bulk Action、Selection、Row Action、Inline Edit、Status、Link、Export/Import、Saved View、Column Customization，並設計 0 筆/1 筆/大量/Loading/Error 狀態。

## 17. Form 逆編譯
針對每個 Field 推論 Label、Type、Placeholder、Default、Required、Validation、Error Message、Help Text、Dependency、Conditional Display、Submit Condition。判斷 Auto Save、Draft、Dirty State、Unsaved Changes、Confirm Dialog 是否需要。

## 18. 搜尋逆編譯
分析 Global/Local Search、Full Text、Prefix、Exact Match、Fuzzy、Filter、Facet、Sort、Recent Search、History、Command Palette，並設計鍵盤操作與搜尋結果 UI。

## 19. AI SaaS 逆編譯
除了標準 SaaS 分析，從可觀察行為推論 Prompt、System Prompt、Context、Memory、Model、Temperature、Tool Calling、RAG、Vector Search、Agent、Workflow、Streaming、Regeneration、Edit、Retry、Model Switching。不要假裝知道隱藏實作，請描述合理的獨立 Architecture。

## 20. AI Chat UI 逆編譯
分析 Conversation、Message、Role、Streaming、Attachment、Image、File、Citation、Tool Call、Retry、Edit、Branch、Stop、Copy、Feedback、History、Delete、Archive，並設計 Conversation/Message/Attachment/ToolCall/Citation/Feedback 的推估資料模型。

## 21. AI Agent SaaS 逆編譯
判斷是否存在 User Request → Planning → Tool Selection → Tool Execution → Observation → Replanning → Result 的迴圈。將 Task、Run、Step、Tool、Artifact、Approval、Error、Retry、Human in the Loop 建模為 Entity。

## 22. API 逆編譯
設計重現可觀察 UX 所需要的 API。將操作映射到 GET/POST/PATCH/DELETE，並定義 Request、Response、Error、Pagination、Filter、Sort、Authentication。不要找實際私有 Endpoint，而是做獨立實作的 API 規格。

## 23. Webhook / Integration 逆編譯
從整合畫面推論 OAuth、API Key、Webhook、Import、Export、Sync、Trigger、Action、Mapping。設計 Connection → Authorization → Configuration → Sync → Error Handling → Disconnect 的 Lifecycle。

## 24. 通知系統逆編譯
推論 In-app、Email、Push、Slack、Webhook 等管道，整理 Event、Recipient、Channel、Template、Trigger、Frequency、Preference，並設計 Notification Preference 畫面。

## 25. Activity Log / Audit Log 逆編譯
設計 Actor、Action、Target、Timestamp、Metadata 的事件模型，並評估稽核用途是否需要 IP、Device、Before、After、Admin Action。

## 26. 管理後台逆編譯
從前台功能反推出內部 Admin Console。考慮 User、Workspace、Billing、Subscription、Feature Flag、Abuse、Support、Logs、Jobs、Integration、Content、Announcement、Metrics，並與一般使用者功能分離。

## 27. 錯誤設計逆編譯
列出 400/401/403/404/409/422/429/500、Timeout、Offline、Integration Error、Payment Error 等可能失敗狀態。為每一種定義 Cause、User Message、Recovery Action、Retry、Logging。

## 28. Empty State 逆編譯
為各相關頁面設計 First Use、No Search Results、No Permission、Deleted、Filter Result 0，並定義 Title、Description、Illustration、Primary CTA、Secondary CTA。

## 29. Responsive / Mobile 逆編譯
從 Desktop 推論 Tablet/Mobile。針對 Sidebar、Navigation、Table、Modal、Form、Toolbar、Card、Chart，不要只縮小尺寸，而是依資訊優先級設計隱藏、折疊、移動。

## 30. Accessibility 逆編譯
檢查 Keyboard、Focus、Contrast、Label、ARIA、Screen Reader、Error、Modal、Dropdown、Table、Form、Motion，提出符合 WCAG 思維的獨立實作需求。

## 31. Performance 逆編譯
為重現相同體感速度，評估 SSR、CSR、Streaming、Lazy Load、Prefetch、Cache、Optimistic UI、Skeleton、Pagination、Infinite Scroll、Image Optimization、Code Splitting。不要斷言原產品實際使用這些技術。

## 32. Security 逆編譯
設計 Authentication、Authorization、CSRF、XSS、SQL Injection、Rate Limit、Encryption、Secrets、Audit Log、Session、API Key、Webhook Signature、File Upload、Tenant Isolation 等需求，特別明確定義多租戶資料隔離。

## 33. SaaS 商業模式逆編譯
分析 ICP、Persona、JTBD、Acquisition、Activation、Monetization、Retention、Expansion、Referral、Churn，並推論 Free → Paid → Team → Enterprise 的 Expansion Path。

## 34. Growth 設計逆編譯
尋找 Invite、Content、Collaboration、Sharing、Template、Integration、Data Network Effect 等 Growth Loop，並用 Trigger → User Action → External Exposure → New User → Activation 說明。

## 35. 行銷網站逆編譯
分析 Hero → Problem → Value Proposition → Product Demonstration → Use Case → Social Proof → Integration → Pricing → FAQ → CTA 的說服結構。說明每個 Section 的讀者心理、Message、Proof 與推進作用。

## 36. 競品 SaaS 比較逆編譯
用同一框架比較 SaaS A/B 的 Target User、JTBD、IA、Core Feature、Workflow、UX、Design、Collaboration、AI、Integration、Pricing、Growth Loop、Moat。最後比較兩者提出的工作方式與產品世界觀。

## 37. MVP 逆編譯
設計用約 20% 功能重現約 80% 使用者價值的 MVP。將所有功能分類成 P0/P1/P2/P3，再定義最小 Data Model、Screens、APIs、User Flows。

## 38. 一週完成版本
假設 1–2 位工程師、Web only、1 週、不需要完美還原，規劃 Day 1–Day 7。可安全交給外部 SaaS 的通用功能就外包，集中在核心體驗。

## 39. 給 AI Coding Agent 的逆編譯
轉換成 AI Coding Agent 可直接實作的規格：Product Overview、User Stories、Routes、Screen Spec、Component Tree、Data Model、API、State、Permission、Validation、Error Handling、Responsive、Acceptance Criteria、Test Cases、Implementation Order。每個功能加入 Given/When/Then。

## 40. 完整重建 Master Prompt
為了獨立重建以下 SaaS 的可觀察產品行為，進行完整分析。對象：[URL / 截圖 / 影片 / 說明]。同時扮演 Product Manager、UX Researcher、UI Designer、Design System Designer、Frontend/Backend Architect、Database Designer、Security Engineer、Growth PM、QA Engineer，依序輸出 A.Product、B.IA、C.Features(P0-P3)、D.Screen Spec、E.User Flow、F.UI System、G.Data Model、H.Business Logic、I.API、J.Auth、K.Billing、L.Integration、M.Non-functional、N.Analytics、O.MVP、P.Implementation、Q.Test。

---

## 最重要規則

不要混淆以下三類：

- **Observation**：直接可確認的事實
- **Inference**：從證據合理推論出的設計
- **Speculation**：證據不足的假設

好的逆編譯會依 **Pixel → Component → Screen → Flow → Feature → Data → Rule → System → Business** 的順序提高抽象層級。
