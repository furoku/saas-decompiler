# SaaS Decompiler — 한국어 프롬프트 모음

> 공개 페이지, 스크린샷, 실제 접근 가능한 제품 화면, 공개 문서 등 관찰 가능한 정보에서 SaaS의 구조를 독립 구현 가능한 수준까지 추론하기 위한 프롬프트 모음입니다. 비공개 소스 코드, 비밀정보, 인증 우회를 목적으로 하지 않습니다.

## 1. 범용 SaaS 역컴파일
이 SaaS를 깊이 역컴파일하세요. UI 묘사에 그치지 말고 문제, 대상 사용자, JTBD, 가치 제안, 주요 유스케이스, 화면, 정보 구조, 기능, 사용자 흐름, 상태 전이, 데이터 모델, 권한, 비즈니스 규칙, 디자인 시스템, API, 연동, 과금, 온보딩, 알림, 검색, 관리자 기능, 보안, 비기능 요구사항, 구현 우선순위를 재구성하세요. 마지막에 관찰 / 높은 확률의 추론 / 낮은 확률의 추측 / MVP 필수 / 생략 가능으로 구분하세요.

## 2. 스크린샷 기반 역컴파일
첨부 스크린샷에서 페이지 목적, 계층, 내비게이션, UI 컴포넌트, 액션, CRUD, 목록/상세/편집 관계, 데이터 필드, 필터, 정렬, 검색, 페이지네이션, 상태, 권한, 모달, 빈 상태, 로딩, 오류, 상태 변화를 추론하세요. `화면상의 근거 → 추론 사양 → 확신도` 형식으로 출력하세요.

## 3. URL 기반 전체 SaaS 역컴파일
이 URL을 시작점으로 공개 범위의 홈, 회원가입, 로그인, 온보딩, 대시보드, 설정, 과금, 도움말, 문서, FAQ, 약관, 개인정보, 기능 소개를 분석하세요. 마케팅 사이트가 약속하는 가치와 실제로 관찰되는 제품 기능을 분리하고 PRD 수준의 재구축 사양을 작성하세요.

## 4. UI / UX 역컴파일
레이아웃, 최대 폭, 그리드, 사이드바, 헤더, 여백, 정보 밀도, 타이포그래피, 색상 시스템, Button/Input/Select/Table/Card/Badge/Modal/Drawer/Toast 등의 컴포넌트와 상태를 분석하고 재현용 Design Token으로 정리하세요.

## 5. 디자인 시스템 역컴파일
여러 화면에서 공통 규칙을 추출해 Color, Typography, Spacing, Radius, Border, Shadow, Z-index, Icon, Grid, Breakpoint, Motion, Component Variant, Interaction State를 정리하세요. 직접 확인할 수 없는 값은 추정값으로 표시하고 CSS Variables 또는 Tailwind Theme로 변환 가능한 형태로 만드세요.

## 6. 프론트엔드 구조 역컴파일
독립 재구현을 가정하고 Layout / Page / Feature / Component / UI Primitive로 분해하세요. Routing, Nested Layout, Shared Component, State Management, Server/Local/Form State, Optimistic Update, Cache, Pagination, Search Params, URL State를 설계하고 권장 디렉터리 구조를 제시하세요.

## 7. 데이터 모델 역컴파일
화면의 이름, ID, User, Team, Workspace, Project, Status, Tag, Date, Owner, Permission, Relation 등에서 Entity를 추출하세요. 각 Entity의 Field, Type, Required/Optional, Relation, Unique Constraint, Index 후보, Lifecycle을 설계하고 ERD/SQL/Prisma로 옮길 수 있게 정리하세요.

## 8. 사용자 흐름 역컴파일
주요 JTBD마다 Start → Action → System Response → Decision → Next Action → Success 흐름을 작성하세요. Happy Path, 최초 사용자, 재방문 사용자, 데이터 0건, 입력 오류, 권한 부족, 네트워크 오류, 취소, 삭제, 복구 분기도 포함하세요.

## 9. 상태 전이 역컴파일
주요 객체의 State Machine을 추론하세요. 각 State마다 Entry Condition, Allowed Action, Forbidden Action, Next State, Rollback, UI Representation을 정리하세요.

## 10. 비즈니스 로직 역컴파일
왜 특정 조건에서 버튼이 나타나는지, 왜 일부 데이터가 수정 불가인지, 왜 상태가 바뀌는지 UI에서 추론하세요. RULE-001 형식으로 WHEN / THEN / EXCEPT / UI 근거 / 확신도를 작성하세요.

## 11. 인증·권한 역컴파일
Signup, Login, OAuth, Magic Link, Password Reset, Email Verification, MFA, Session, Organization, Workspace, Team, Role, Permission을 추론하세요. RBAC/ABAC 적합성을 판단하고 Owner/Admin/Member/Viewer/Guest 등의 권한 매트릭스를 만드세요.

## 12. Workspace / Team 구조 역컴파일
User / Organization / Workspace / Team / Project 관계를 분석하세요. 다중 Workspace 소속, 전환, 초대, Role, Ownership, Seat, 과금 단위, Data Isolation, 삭제, Ownership Transfer를 포함한 추정 ERD를 작성하세요.

## 13. 과금 시스템 역컴파일
가격 페이지, 설정, 기능 제한에서 Free/Trial/Pro/Team/Enterprise, Seat/Usage/Credit 과금, Monthly/Annual, Trial, Upgrade, Downgrade, Cancel, Invoice, Tax, Coupon, Overage를 추론하세요. Paywall 기능/한도를 찾아 독립 구현용 Billing Model을 설계하세요.

## 14. 온보딩 역컴파일
Signup, Welcome, Persona/Use Case 선택, Workspace 생성, Import, Integration, Tutorial, Checklist, Sample Data, Empty State, First Success를 분석하세요. Time to Value를 어떻게 줄이는지와 제품이 수집하려는 사용자 정보도 추론하세요.

## 15. 대시보드 역컴파일
이 대시보드가 사용자가 무엇을 이해하고 다음에 무엇을 하게 만드는지 분석하세요. Primary KPI, Secondary KPI, Summary, Trend, Alert, Recommendation, Recent Activity, Task, CTA, Filter, Date Range를 P0/P1/P2로 분류하세요.

## 16. 테이블 / 목록 화면 역컴파일
Columns, Type, Sort, Filter, Search, Pagination, Bulk Action, Selection, Row Action, Inline Edit, Status, Link, Export/Import, Saved View, Column Customization을 사양화하세요. 0건/1건/대량/Loading/Error 상태도 설계하세요.

## 17. 폼 역컴파일
각 Field의 Label, Type, Placeholder, Default, Required, Validation, Error Message, Help Text, Dependency, Conditional Display, Submit Condition을 추론하세요. Auto Save, Draft, Dirty State, Unsaved Changes, Confirm Dialog 필요성도 판단하세요.

## 18. 검색 기능 역컴파일
Global/Local Search, Full Text, Prefix, Exact Match, Fuzzy, Filter, Facet, Sort, Recent Search, History, Command Palette를 분석하고 키보드 동작과 검색 결과 UI까지 설계하세요.

## 19. AI SaaS 역컴파일
일반 분석에 더해 Prompt, System Prompt, Context, Memory, Model, Temperature, Tool Calling, RAG, Vector Search, Agent, Workflow, Streaming, Regeneration, Edit, Retry, Model Switching 존재를 관찰 가능한 행동에서 추론하세요. 숨은 구현을 안다고 단정하지 말고 합리적인 독립 Architecture로 설명하세요.

## 20. AI 채팅 UI 역컴파일
Conversation, Message, Role, Streaming, Attachment, Image, File, Citation, Tool Call, Retry, Edit, Branch, Stop, Copy, Feedback, History, Delete, Archive를 분석하고 Conversation/Message/Attachment/ToolCall/Citation/Feedback 데이터 모델을 설계하세요.

## 21. AI Agent SaaS 역컴파일
User Request → Planning → Tool Selection → Tool Execution → Observation → Replanning → Result 루프가 있는지 분석하세요. Task, Run, Step, Tool, Artifact, Approval, Error, Retry, Human in the Loop를 Entity로 모델링하세요.

## 22. API 역컴파일
관찰된 UX를 재현하는 데 필요한 API를 설계하세요. 각 작업을 GET/POST/PATCH/DELETE에 연결하고 Request, Response, Error, Pagination, Filter, Sort, Authentication을 정의하세요. 비공개 실제 엔드포인트가 아니라 독립 구현용 API 사양으로 작성하세요.

## 23. Webhook / Integration 역컴파일
연동 화면에서 OAuth, API Key, Webhook, Import, Export, Sync, Trigger, Action, Mapping을 추론하세요. Connection → Authorization → Configuration → Sync → Error Handling → Disconnect Lifecycle을 설계하세요.

## 24. 알림 시스템 역컴파일
In-app, Email, Push, Slack, Webhook 등의 채널을 추론하고 Event, Recipient, Channel, Template, Trigger, Frequency, Preference를 정리하세요. Notification Preference 화면도 설계하세요.

## 25. Activity Log / Audit Log 역컴파일
Actor, Action, Target, Timestamp, Metadata 이벤트 모델을 설계하세요. 감사 목적의 IP, Device, Before, After, Admin Action 필요성도 검토하세요.

## 26. 관리자 화면 역컴파일
표면 기능에서 내부 Admin Console을 역산하세요. User, Workspace, Billing, Subscription, Feature Flag, Abuse, Support, Logs, Jobs, Integration, Content, Announcement, Metrics를 검토하고 일반 사용자 기능과 분리하세요.

## 27. 오류 설계 역컴파일
400/401/403/404/409/422/429/500, Timeout, Offline, Integration Error, Payment Error 등을 정리하고 각 오류의 Cause, User Message, Recovery Action, Retry, Logging을 설계하세요.

## 28. Empty State 역컴파일
각 페이지의 First Use, No Search Results, No Permission, Deleted, Filter Result 0 상태를 설계하고 Title, Description, Illustration, Primary CTA, Secondary CTA를 정의하세요.

## 29. 반응형 / 모바일 역컴파일
Desktop에서 Tablet/Mobile 동작을 추론하세요. Sidebar, Navigation, Table, Modal, Form, Toolbar, Card, Chart를 단순 축소하지 말고 정보 우선순위에 따라 숨김/접기/이동을 설계하세요.

## 30. 접근성 역컴파일
Keyboard, Focus, Contrast, Label, ARIA, Screen Reader, Error, Modal, Dropdown, Table, Form, Motion을 점검하고 WCAG를 고려한 독립 구현 요구사항을 제시하세요.

## 31. 성능 역컴파일
동등한 체감 속도를 위해 SSR, CSR, Streaming, Lazy Load, Prefetch, Cache, Optimistic UI, Skeleton, Pagination, Infinite Scroll, Image Optimization, Code Splitting을 검토하세요. 원 제품이 실제로 이 기술을 쓴다고 단정하지 마세요.

## 32. 보안 역컴파일
Authentication, Authorization, CSRF, XSS, SQL Injection, Rate Limit, Encryption, Secrets, Audit Log, Session, API Key, Webhook Signature, File Upload, Tenant Isolation 요구사항을 설계하세요. 특히 멀티테넌트 데이터 격리를 명확히 정의하세요.

## 33. SaaS 비즈니스 모델 역컴파일
ICP, Persona, JTBD, Acquisition, Activation, Monetization, Retention, Expansion, Referral, Churn을 분석하세요. Free → Paid → Team → Enterprise의 Expansion Path도 추론하세요.

## 34. 그로스 설계 역컴파일
Invite, Content, Collaboration, Sharing, Template, Integration, Data Network Effect 등의 Growth Loop를 찾고 Trigger → User Action → External Exposure → New User → Activation으로 설명하세요.

## 35. 마케팅 사이트 역컴파일
Hero → Problem → Value Proposition → Product Demonstration → Use Case → Social Proof → Integration → Pricing → FAQ → CTA의 설득 구조를 분석하세요. 각 Section의 독자 심리, Message, Proof, 다음 Section으로 넘기는 역할을 설명하세요.

## 36. 경쟁 SaaS 비교 역컴파일
SaaS A/B를 Target User, JTBD, IA, Core Feature, Workflow, UX, Design, Collaboration, AI, Integration, Pricing, Growth Loop, Moat로 비교하세요. 마지막에 각 제품이 제안하는 업무 방식과 세계관의 차이까지 정리하세요.

## 37. MVP 역컴파일
기능 약 20%로 사용자 가치 약 80%를 재현하는 MVP를 설계하세요. 모든 기능을 P0/P1/P2/P3로 분류하고 최소 Data Model, Screens, APIs, User Flows를 정의하세요.

## 38. 1주일 구축 버전
엔지니어 1~2명, Web only, 1주일, 완벽한 복제 불필요를 가정하고 Day 1~Day 7 구현 계획을 작성하세요. 범용 기능은 적절한 외부 SaaS로 대체하고 핵심 경험에 집중하세요.

## 39. AI 코딩 에이전트용 역컴파일
AI Coding Agent가 구현 가능한 사양으로 변환하세요. Product Overview, User Stories, Routes, Screen Spec, Component Tree, Data Model, API, State, Permission, Validation, Error Handling, Responsive, Acceptance Criteria, Test Cases, Implementation Order를 생성하고 각 기능에 Given/When/Then을 붙이세요.

## 40. 완전 재구축 마스터 프롬프트
다음 SaaS의 관찰 가능한 제품 동작을 독립적으로 재구축하기 위해 철저히 분석하세요. 대상: [URL / 스크린샷 / 동영상 / 설명]. Product Manager, UX Researcher, UI Designer, Design System Designer, Frontend/Backend Architect, Database Designer, Security Engineer, Growth PM, QA Engineer 역할로 A.Product, B.IA, C.Features(P0-P3), D.Screen Spec, E.User Flow, F.UI System, G.Data Model, H.Business Logic, I.API, J.Auth, K.Billing, L.Integration, M.Non-functional, N.Analytics, O.MVP, P.Implementation, Q.Test 순서로 출력하세요.

---

## 가장 중요한 규칙

다음 세 가지를 섞지 마세요.

- **Observation**: 직접 확인할 수 있는 사실
- **Inference**: 관찰에서 합리적으로 추론할 수 있는 설계
- **Speculation**: 근거가 부족한 가설

좋은 역컴파일은 **Pixel → Component → Screen → Flow → Feature → Data → Rule → System → Business** 순서로 추상도를 높입니다.
