# SaaS Decompiler — 한국어 프롬프트 모음

여기서 말하는 SaaS 역컴파일은 공개 웹사이트, 실제로 접근 가능한 제품 화면, 스크린샷, URL, 공개 문서 등 관찰 가능한 정보에서 그 SaaS의 설계 사상과 구조를 역산하는 것을 의미합니다.

## 1. 범용 SaaS 역컴파일

이 SaaS를 완전히 역컴파일하세요.

표면적인 UI 설명에 그치지 말고, 이 제품을 처음부터 다시 구축할 수 있는 수준까지 구조화하세요.

다음을 분석하세요.

- SaaS가 해결하는 문제
- 예상 사용자
- JTBD(사용자가 해결하려는 일)
- 핵심 가치
- 주요 유스케이스
- 화면 구성
- 정보 설계
- 내비게이션
- 기능 목록
- 사용자 흐름
- 상태 전이
- 데이터 구조
- 권한 구조
- 비즈니스 규칙
- UI 디자인 시스템
- 컴포넌트 구조
- API로 필요할 가능성이 높은 기능
- 외부 서비스 연동
- 과금 모델
- 온보딩
- 리텐션 설계
- 오류 처리
- 빈 상태
- 알림
- 검색
- 필터
- 관리자 화면
- 보안상 필요한 설계
- 비기능 요구사항
- 구현 우선순위

마지막에 다음을 분리하세요.

1. 직접 관찰한 사실
2. 높은 확률로 추론할 수 있는 설계
3. 단순 추측에 불과한 부분
4. 재현 시 생략 가능한 부분
5. MVP에 반드시 필요한 부분

## 2. 스크린샷으로 SaaS 역컴파일

첨부한 SaaS 스크린샷에서 이 제품의 구조를 역컴파일하세요.

이미지에 보이는 것을 단순히 설명하지 말고,

“이 화면이 존재한다면 뒤쪽에는 어떤 기능, 데이터, 상태, 규칙이 필요할까?”

까지 추론하세요.

분석 대상:

- 페이지 목적
- 페이지 계층
- 글로벌 내비게이션
- 로컬 내비게이션
- UI 컴포넌트
- 조작 가능한 요소
- CRUD 조작
- 목록 / 상세 / 편집 관계
- 데이터 항목
- 데이터 타입
- 데이터 간 관계
- 필터
- 정렬
- 검색
- 페이지네이션
- 상태
- 권한
- 모달
- 드로어
- 토스트
- 빈 상태
- 로딩
- 오류 상태
- 사용자 조작에 따른 상태 변화

각 요소를 다음 형식으로 기록하세요.

**화면상의 증거 → 추론되는 사양**

## 3. URL에서 SaaS 전체 역컴파일

이 URL의 SaaS를 사이트 전체를 탐색하면서 역컴파일하세요.

한 페이지에 한정하지 말고 가능한 범위에서 다음을 확인하세요.

- 메인 페이지
- 회원가입
- 로그인
- 온보딩
- 대시보드
- 설정
- 과금
- 도움말
- 문서
- FAQ
- 이용약관
- 개인정보처리방침
- 공개된 기능 소개

그 후,

**마케팅 사이트가 약속하는 가치**

와

**실제 제품이 제공하는 기능**

을 분리하세요.

최종적으로 이 SaaS를 재구축하기 위한 Product Requirements Document 수준의 사양을 생성하세요.

## 4. UI / UX 역컴파일

이 SaaS의 UI / UX 설계를 상세히 역컴파일하세요.

### 레이아웃

- 최대 폭
- 그리드
- 사이드바 폭
- 헤더 높이
- 컬럼 구성
- 여백 규칙
- 콘텐츠 밀도

### 타이포그래피

- 폰트 계열
- 크기 계층
- 굵기
- 행간
- 제목 계층
- 숫자 표시

### 컬러

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

### 컴포넌트

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

각각에 대해 다음을 추론하세요.

- 외형
- 크기
- Variant
- State
- Hover
- Focus
- Disabled
- Loading
- Error

마지막에 재현용 Design Token으로 정리하세요.

## 5. 디자인 시스템 역컴파일

이 SaaS에서 디자인 시스템을 추출하세요.

개별 페이지를 복사하지 말고 여러 페이지에 공통되는 규칙을 찾으세요.

추출 대상:

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

값을 직접 확인할 수 없다면 “외형에서 추정한 값”이라고 명시하세요.

가능하면 CSS Variables / Tailwind Theme / Design Tokens로 변환 가능한 형식까지 정리하세요.

## 6. 프론트엔드 구조 역컴파일

이 SaaS를 프론트엔드 엔지니어 관점에서 역컴파일하세요.

React / Next.js 등으로 화면을 재구축한다고 가정하고 다음으로 분해하세요.

- Layout
- Page
- Feature
- Component
- UI Primitive

추론할 것:

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

마지막에 권장 디렉터리 구조를 생성하세요.

단, 대상 SaaS가 실제로 사용하는 내부 기술이라고 단정하지 말고 “재구축한다면 합리적인 구조”로 제안하세요.

## 7. 데이터 모델 역컴파일

이 SaaS의 UI에서 뒤에 존재하는 데이터 모델을 역산하세요.

화면에 보이는 다음 요소 등에서 Entity를 추출하세요.

- 이름
- ID
- 사용자
- 팀
- Workspace
- Project
- Status
- Tag
- Date
- Owner
- Permission
- Relation

각 Entity에 대해 다음을 추론하세요.

- Entity명
- 역할
- Field
- Data Type
- Required / Optional
- Relation
- Unique Constraint
- Index 후보
- Lifecycle

마지막에 ERD / SQL Schema / Prisma Schema 상당으로 변환 가능한 구조로 만드세요.

추론한 부분에는 반드시 확신도를 붙이세요.

## 8. 사용자 흐름 역컴파일

이 SaaS에서 사용자가 목적을 달성할 때까지의 조작을 역컴파일하세요.

주요 JTBD마다 다음 형식으로 작성하세요.

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

또한 다음 분기도 추론하세요.

- Happy Path
- 최초 사용자
- 리피터
- 데이터 0건
- 입력 오류
- 권한 부족
- 통신 오류
- 취소
- 삭제
- 복원

## 9. 상태 전이 역컴파일

이 SaaS에 존재하는 주요 객체의 State Machine을 역산하세요.

예:

Draft
↓
Processing
↓
Completed

UI의 Badge, Button, Menu, 표시 전환 등에서 상태를 추론하세요.

각 상태에 대해 다음을 정리하세요.

- State
- Entry Condition
- Allowed Action
- Forbidden Action
- Next State
- Rollback
- UI Representation

## 10. 비즈니스 로직 역컴파일

이 SaaS의 UI에서 그 뒤의 비즈니스 규칙을 추론하세요.

단순 CRUD가 아니라 다음을 분석하세요.

“왜 이 버튼은 이 조건에서만 보이는가?”

“왜 이 데이터는 편집할 수 없는가?”

“왜 이 상태가 되는가?”

다음 형식으로 출력하세요.

RULE-001

조건:
WHEN ...

처리:
THEN ...

예외:
EXCEPT ...

UI상의 증거:

확신도:
High / Medium / Low

## 11. 인증 / 권한 역컴파일

이 SaaS의 Authentication / Authorization 설계를 역컴파일하세요.

추론 대상:

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

RBAC와 ABAC 중 어느 쪽이 적합한지 추론하세요.

Role 예:

- Owner
- Admin
- Member
- Viewer
- Guest

각 Role에 대해 View / Create / Edit / Delete / Invite / Billing / Admin 권한을 매트릭스로 정리하세요.

## 12. Workspace / Team 구조 역컴파일

이 SaaS의 계정 구조를 역컴파일하세요.

특히 User / Organization / Workspace / Team / Project의 관계를 분석하세요.

확인 포인트:

- 한 사용자가 여러 Workspace에 속할 수 있는가
- Workspace 전환이 있는가
- 초대 기능
- Role
- Ownership
- Seat
- Billing 단위
- Data Isolation
- Workspace 삭제
- Ownership Transfer

추정 ERD를 작성하세요.

## 13. 과금 시스템 역컴파일

이 SaaS의 가격 페이지, 설정 화면, 기능 제한에서 Billing 구조를 역컴파일하세요.

분석:

- Free / Trial
- Pro
- Team
- Enterprise
- Seat 과금
- Usage 과금
- Credit제
- Monthly / Annual
- Trial 기간
- Upgrade
- Downgrade
- Cancel
- Refund
- Invoice
- Tax
- Coupon
- Overage

또한 **어떤 Feature / Limit가 Paywall인지** 특정하세요.

Stripe 등을 이용해 재구축할 경우의 Billing Model까지 설계하세요.

## 14. 온보딩 역컴파일

이 SaaS의 최초 사용자 경험을 역컴파일하세요.

분석:

- Sign up
- Welcome
- Persona 선택
- Use Case 선택
- Workspace 생성
- Import
- Integration
- Tutorial
- Checklist
- Sample Data
- Empty State
- First Success

특히 **Time to Value를 단축하기 위해 무엇을 하는지** 설명하세요.

또한 온보딩을 통해 제품 측이 얻고 싶어 하는 사용자 정보도 추론하세요.

## 15. 대시보드 역컴파일

이 대시보드가 “사용자에게 무엇을 이해시키고, 다음에 무엇을 하게 하려는지” 역컴파일하세요.

분석:

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

정보 우선순위를 P0 / P1 / P2로 분류하세요.

## 16. 테이블 / 목록 화면 역컴파일

이 목록 화면을 완전히 사양화하세요.

분석:

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

또한 0건 / 1건 / 대량 데이터 / Loading / Error 상황의 UI도 설계하세요.

## 17. 폼 역컴파일

이 폼을 완전히 사양화하세요.

각 Field에 대해 다음을 추출하세요.

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

또한 Auto Save / Draft / Dirty State / Unsaved Changes / Confirm Dialog가 필요한지 판단하세요.

## 18. 검색 기능 역컴파일

이 SaaS의 검색 UX를 역컴파일하세요.

분석:

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

키보드 조작과 검색 결과 UI도 추론하세요.

## 19. AI SaaS 역컴파일

이 AI SaaS를 역컴파일하세요.

일반 SaaS 분석에 더해 UI에서 다음 존재 여부를 추론하세요.

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

중요:

내부 Prompt나 비공개 구현을 알고 있는 것처럼 단정하지 말고, 사용자가 관찰할 수 있는 동작에서 “합리적으로 재구축한다면 어떤 Architecture가 될지” 기술하세요.

## 20. AI 채팅 UI 역컴파일

이 AI 채팅 화면을 역컴파일하세요.

분석:

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

추정 데이터 모델로 Conversation / Message / Attachment / ToolCall / Citation / Feedback까지 설계하세요.

## 21. AI Agent SaaS 역컴파일

이 Agent형 SaaS의 실행 모델을 역컴파일하세요.

다음 루프가 존재하는지 분석하세요.

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

또한 다음을 Entity로 모델링하세요.

- Task
- Run
- Step
- Tool
- Artifact
- Approval
- Error
- Retry
- Human in the Loop

## 22. API 역컴파일

이 SaaS의 화면 조작에서 필요한 API를 역산하세요.

UI 조작마다 GET / POST / PATCH / DELETE를 대응시키세요.

예:

사용자 목록 표시 → GET /users

사용자 생성 → POST /users

사용자 업데이트 → PATCH /users/:id

삭제 → DELETE /users/:id

또한 Request / Response / Error / Pagination / Filter / Sort / Authentication을 포함한 API 사양안을 생성하세요.

실제 비공개 API를 특정하는 것이 아니라, **동일한 제품 경험을 구현하는 데 필요한 API 설계**로 작성하세요.

## 23. Webhook / Integration 역컴파일

이 SaaS의 Integration 화면에서 외부 연동 설계를 추론하세요.

분석:

- OAuth
- API Key
- Webhook
- Import
- Export
- Sync
- Trigger
- Action
- Mapping

각 Integration에 대해 다음 Lifecycle을 설계하세요.

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

## 24. 알림 시스템 역컴파일

이 SaaS의 Notification System을 역컴파일하세요.

추론 채널:

- In-app
- Email
- Push
- Slack
- Webhook

이벤트마다 Event / Recipient / Channel / Template / Trigger / Frequency / Preference를 정리하세요.

Notification Preference 화면도 설계하세요.

## 25. Activity Log / Audit Log 역컴파일

이 SaaS의 이력 / 활동 기능을 역컴파일하세요.

이벤트 모델:

Actor
Action
Target
Timestamp
Metadata

“Kai updated Project A” 같은 이벤트를 생성하는 데 필요한 데이터 구조를 추론하세요.

감사 로그로 필요한 IP / Device / Before / After / Admin Action도 검토하세요.

## 26. 관리자 화면 역컴파일

이 SaaS의 사용자-facing 기능에서 운영 측에 필요한 Admin Console을 역산하세요.

필요할 수 있는 기능:

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

일반 사용자 기능과 Admin 전용 기능을 분리하세요.

## 27. 오류 설계 역컴파일

이 SaaS에서 예상되는 Failure State를 나열하세요.

예:

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

각 Error에 대해 Cause / User Message / Recovery Action / Retry / Logging을 설계하세요.

## 28. Empty State 역컴파일

이 SaaS의 각 페이지에서 “데이터가 아직 존재하지 않는 상태”를 설계하세요.

Empty State를 다음으로 나누세요.

- First Use
- No Search Results
- No Permission
- Deleted
- Filter Result 0

각각 Title / Description / Illustration / Primary CTA / Secondary CTA를 설계하세요.

## 29. 반응형 / 모바일 역컴파일

Desktop 버전에서 Mobile / Tablet 버전을 역산하세요.

분석:

- Sidebar
- Navigation
- Table
- Modal
- Form
- Toolbar
- Card
- Chart

Desktop → Tablet → Mobile에서 어떻게 변형되는지 정리하세요.

단순 축소가 아니라 우선순위에 따라 정보를 삭제 / 접기 / 이동하는 설계로 만드세요.

## 30. 접근성 역컴파일

이 SaaS를 WCAG를 고려해 재구축한다고 가정하고 필요한 Accessibility 요구사항을 추출하세요.

분석:

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

UI 디자인을 유지하면서 필요한 개선도 제시하세요.

## 31. 성능 역컴파일

이 SaaS와 동등한 체감 속도를 구현하기 위해 필요한 Performance 전략을 추론하세요.

분석:

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

원 SaaS가 실제로 이 기술을 사용한다고 단정하지 말고, 관찰된 UX를 재현하기 위한 합리적인 Architecture를 제안하세요.

## 32. 보안 역컴파일

이 SaaS의 기능에서 필요한 Security Requirement를 역산하세요.

검토:

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

특히 멀티테넌트 SaaS로서 “다른 Workspace의 데이터가 절대 보이지 않도록” 하기 위한 설계를 명시하세요.

## 33. SaaS 비즈니스 모델 역컴파일

이 서비스를 제품이 아니라 SaaS 비즈니스로 역컴파일하세요.

분석:

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

또한 Free → Paid / Individual → Team / Team → Enterprise의 Expansion Path를 추론하세요.

## 34. 그로스 설계 역컴파일

이 SaaS의 UI, 가격, 온보딩, 공유 기능에서 Growth Loop를 역컴파일하세요.

찾을 것:

- Invite Loop
- Content Loop
- Collaboration Loop
- Sharing Loop
- Template Loop
- Integration Loop
- Data Network Effect

각각 Trigger → User Action → External Exposure → New User → Activation의 순환으로 설명하세요.

## 35. 마케팅 사이트 역컴파일

이 SaaS의 LP를 역컴파일하세요.

문구를 단순 추출하지 말고 페이지의 설득 구조를 분석하세요.

예:

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

각 Section에 대해 다음을 설명하세요.

- 독자의 심리 상태
- 전달하는 Message
- 사용하는 Proof
- 다음 Section으로 이동시키는 역할

## 36. 경쟁 SaaS 비교 역컴파일

SaaS A와 SaaS B를 동일한 프레임워크로 역컴파일해 비교하세요.

비교축:

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

마지막에는 단순 기능 차이가 아니라 **각 제품이 사용자에게 어떤 세계관과 업무 방식을 제안하는지**까지 비교하세요.

## 37. MVP 역컴파일

이 SaaS를 완전히 복사하지 말고 20%의 기능으로 80%의 가치를 재현하는 MVP를 설계하세요.

모든 기능을 다음으로 분류하세요.

- P0: 없으면 가치가 성립하지 않음
- P1: 중요하지만 나중에 추가 가능
- P2: 성숙한 SaaS용
- P3: 이번에는 불필요

그 후 최소 데이터 모델 / 최소 화면 / 최소 API / 최소 사용자 흐름을 정의하세요.

## 38. 1주일 구축 버전

이 SaaS의 핵심 경험을 1주일 안에 재구축한다고 가정하세요.

제약:

- 엔지니어 1~2명
- Web 버전만
- 완벽한 재현 불필요
- 핵심 경험 최우선

Day 1~Day 7 구현 계획을 만드세요.

외부 SaaS로 대체 가능한 기능은 적극적으로 외부 서비스를 사용하세요.

## 39. AI 코딩 에이전트용 역컴파일

이 SaaS를 AI Coding Agent가 구현할 수 있는 사양으로 변환하세요.

모호한 설명은 금지합니다.

다음을 생성하세요.

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

각 기능에 대해 Given / When / Then 형식의 Acceptance Criteria를 붙이세요.

## 40. 완전 재구축용 마스터 프롬프트

다음 SaaS를 “관찰 가능한 제품 사양에서 재구축한다”는 목적으로 철저히 역컴파일하세요.

대상:
[URL / 스크린샷 / 동영상 / 설명]

동시에 다음 역할로 분석하세요.

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

목적은 대상 서비스의 코드를 훔치는 것이 아닙니다.

**관찰 가능한 UX에서 동등한 사용자 가치를 독립적으로 재구현하기 위한 사양을 만드는 것입니다.**

반드시 다음 순서로 분석하세요.

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
전체 기능을 P0 / P1 / P2 / P3로 분류하세요.

### D. Screen Specification
모든 화면에 대해 Purpose / Input / Output / Action / State / Error / Permission을 기록하세요.

### E. User Flow
주요 JTBD의 End-to-End Flow.

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
Rule 형식으로 기술하세요.

### I. API
UI를 성립시키는 데 필요한 API.

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
Viewed / Clicked / Created / Updated / Deleted / Invited / Upgraded / Completed 등의 주요 이벤트를 정의하세요.

### O. MVP
최소 구성을 추출하세요.

### P. Implementation
권장 기술 구성과 구현 순서를 제안하세요.

### Q. Test
Acceptance Criteria와 E2E Test를 정의하세요.

---

# 가장 중요한 규칙

SaaS 역컴파일에서는 다음 세 가지를 섞지 마세요.

## ① Observation

실제로 확인할 수 있는 것.

예:

“화면 오른쪽 위에 Invite 버튼이 존재한다.”

## ② Inference

관찰에서 합리적으로 추론할 수 있는 것.

예:

“Workspace에 다른 사용자를 초대할 수 있을 가능성이 높다.”

## ③ Speculation

증거가 부족한 가설.

예:

“초대 토큰의 유효기간이 24시간일 수 있다.”

반드시 이 세 종류를 구분하세요.

# SaaS 역컴파일의 기본 원칙

좋은 역컴파일은 다음 순서로 추상도를 높입니다.

**Pixel → Component → Screen → Flow → Feature → Data → Rule → System → Business**

이미지만 보지 마세요.

Button이 있다
↓
Action이 있다
↓
State가 바뀐다
↓
Data가 바뀐다
↓
Business Rule이 존재한다
↓
사용자의 일이 완료된다

라는 인과관계까지 따라가세요.

최종 목표는 “이 SaaS가 무슨 색 버튼을 쓰는지”를 복사하는 것이 아니라, **왜 이 SaaS가 이런 형태가 되었는지** 재구축할 수 있는 것입니다.
