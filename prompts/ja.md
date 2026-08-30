# SaaS Decompiler — 日本語プロンプト集

公開Webサイト、実際に操作できる画面、スクリーンショット、URL、公開ドキュメントなど観察可能な情報から、そのSaaSの設計思想と構造を逆算することを意味する。

## 1. 汎用SaaS逆コンパイル

このSaaSを完全に逆コンパイルしてください。

表面的なUIの説明ではなく、このプロダクトをゼロから再構築できるレベルまで構造化してください。

以下を分析してください。

- SaaSが解決している問題
- 想定ユーザー
- JTBD（ユーザーが片付けたい仕事）
- コアバリュー
- 主要ユースケース
- 画面構成
- 情報設計
- ナビゲーション
- 機能一覧
- ユーザーフロー
- 状態遷移
- データ構造
- 権限構造
- ビジネスルール
- UIデザインシステム
- コンポーネント構造
- APIとして必要になりそうな機能
- 外部サービス連携
- 課金モデル
- オンボーディング
- リテンション設計
- エラー処理
- 空状態
- 通知
- 検索
- フィルター
- 管理画面
- セキュリティ上必要な設計
- 非機能要件
- 実装優先順位

最後に、

1. 観察できた事実
2. 高確度で推測できる設計
3. 推測にすぎない部分
4. 再現する場合に省略可能な部分
5. MVPに絶対必要な部分

を分離してください。

## 2. スクリーンショットからSaaSを逆コンパイル

添付したSaaSのスクリーンショットから、このプロダクトの構造を逆コンパイルしてください。

画像に写っているものを単に説明するのではなく、

「この画面が存在するということは、裏側にどのような機能・データ・状態・ルールが必要なのか」

まで推論してください。

分析対象：

- ページの目的
- ページ階層
- グローバルナビゲーション
- ローカルナビゲーション
- UIコンポーネント
- 操作可能要素
- CRUD操作
- 一覧 / 詳細 / 編集の関係
- データ項目
- データ型
- データ間の関係
- フィルター
- ソート
- 検索
- ページネーション
- ステータス
- 権限
- モーダル
- ドロワー
- トースト
- 空状態
- ローディング
- エラー状態
- ユーザー操作による状態変化

各要素について、

**画面上の証拠 → 推測される仕様**

の形式で記述してください。

## 3. URLからSaaS全体を逆コンパイル

このURLのSaaSを、サイト全体を探索しながら逆コンパイルしてください。

単一ページではなく、可能な範囲で、

- トップページ
- サインアップ
- ログイン
- オンボーディング
- ダッシュボード
- 設定
- 課金
- ヘルプ
- ドキュメント
- FAQ
- 利用規約
- プライバシーポリシー
- 公開されている機能紹介

を横断的に確認してください。

そのうえで、

**マーケティングサイトが約束している価値**

と

**実際のプロダクトが提供している機能**

を分離してください。

最終的に、このSaaSを再構築するためのProduct Requirement Document相当の仕様を生成してください。

## 4. UI / UX逆コンパイル

このSaaSのUI / UX設計を詳細に逆コンパイルしてください。

分析：

### レイアウト

- 最大幅
- グリッド
- サイドバー幅
- ヘッダー高さ
- カラム構成
- 余白ルール
- コンテンツ密度

### タイポグラフィ

- フォント系統
- サイズ階層
- ウェイト
- 行間
- 見出し階層
- 数値表示

### カラー

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

### コンポーネント

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

それぞれについて、

- 見た目
- サイズ
- Variant
- State
- Hover
- Focus
- Disabled
- Loading
- Error

を推測してください。

最後に、再現用のDesign Tokenとしてまとめてください。

## 5. デザインシステム逆コンパイル

このSaaSからデザインシステムを抽出してください。

個別ページをコピーするのではなく、複数ページに共通する規則を発見してください。

抽出対象：

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

値が直接確認できない場合は、

「見た目から推定した値」

として明示してください。

可能なら、

CSS Variables / Tailwind Theme / Design Tokens

に落とし込める形式まで整理してください。

## 6. フロントエンド構造逆コンパイル

このSaaSをフロントエンドエンジニアとして逆コンパイルしてください。

画面をReact / Next.js等で再構築すると仮定し、

ページを

- Layout
- Page
- Feature
- Component
- UI Primitive

へ分解してください。

推定してください：

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

最終的に推奨ディレクトリ構造を生成してください。

ただし、対象SaaSが実際に使用している内部技術については断定せず、

「再構築するなら合理的な構造」

として提案してください。

## 7. データモデル逆コンパイル

このSaaSのUIから、背後に存在するデータモデルを逆算してください。

画面に表示される、

- 名称
- ID
- ユーザー
- チーム
- Workspace
- Project
- Status
- Tag
- Date
- Owner
- Permission
- Relation

などからEntityを抽出してください。

各Entityについて、

- Entity名
- 役割
- Field
- Data Type
- Required / Optional
- Relation
- Unique Constraint
- Index候補
- Lifecycle

を推測してください。

最後に、

- ER図
- SQL Schema
- Prisma Schema相当

へ変換可能な構造にしてください。

推測部分には必ず確度を付けてください。

## 8. ユーザーフロー逆コンパイル

このSaaSでユーザーが目的を達成するまでの操作を逆コンパイルしてください。

主要なJTBDごとに、

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

の形式でフローを書いてください。

さらに、

- Happy Path
- 初回ユーザー
- リピーター
- データ0件
- 入力エラー
- 権限不足
- 通信エラー
- キャンセル
- 削除
- 復元

の分岐も推測してください。

## 9. 状態遷移逆コンパイル

このSaaSに存在する主要オブジェクトのState Machineを逆算してください。

例：

Draft
↓
Processing
↓
Completed

のように、UI上のBadge、Button、Menu、表示切替などから状態を推測してください。

各状態について、

- State
- Entry Condition
- Allowed Action
- Forbidden Action
- Next State
- Rollback
- UI Representation

を整理してください。

## 10. ビジネスロジック逆コンパイル

このSaaSのUIから、その背後にあるビジネスルールを推測してください。

単純なCRUDではなく、

「なぜこのボタンはこの条件で表示されるのか」

「なぜこのデータは編集できないのか」

「なぜこのステータスになるのか」

を分析してください。

以下の形式で出力：

RULE-001

条件：
WHEN ...

処理：
THEN ...

例外：
EXCEPT ...

UI上の証拠：

確度：
High / Medium / Low

## 11. 認証・権限逆コンパイル

このSaaSのAuthentication / Authorization設計を逆コンパイルしてください。

推測対象：

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

RBACまたはABACのどちらが適しているか推測してください。

Role例：

- Owner
- Admin
- Member
- Viewer
- Guest

各Roleについて、

View / Create / Edit / Delete / Invite / Billing / Admin

権限をマトリクス化してください。

## 12. Workspace / Team構造逆コンパイル

このSaaSのアカウント構造を逆コンパイルしてください。

特に、

User
Organization
Workspace
Team
Project

の関係を分析してください。

確認ポイント：

- 1ユーザーが複数Workspaceへ所属可能か
- Workspace切替があるか
- 招待機能
- Role
- Ownership
- Seat
- Billing単位
- Data Isolation
- Workspace削除
- Ownership Transfer

推定ER図を作成してください。

## 13. 課金システム逆コンパイル

このSaaSの料金ページ・設定画面・機能制限からBilling構造を逆コンパイルしてください。

分析：

- Free / Trial
- Pro
- Team
- Enterprise
- Seat課金
- Usage課金
- Credit制
- Monthly / Annual
- Trial期間
- Upgrade
- Downgrade
- Cancel
- Refund
- Invoice
- Tax
- Coupon
- Overage

さらに、

**どのFeature / LimitがPaywallになっているか**

を特定してください。

Stripe等を利用して再構築する場合のBilling Modelまで落とし込んでください。

## 14. オンボーディング逆コンパイル

このSaaSの初回体験を逆コンパイルしてください。

分析：

- Sign up
- Welcome
- Persona選択
- Use Case選択
- Workspace作成
- Import
- Integration
- Tutorial
- Checklist
- Sample Data
- Empty State
- First Success

特に、

**Time to Valueを短縮するために何をしているか**

を説明してください。

さらに、このオンボーディングからプロダクト側が取得したいユーザー情報も推測してください。

## 15. ダッシュボード逆コンパイル

このダッシュボードが、

「ユーザーに何を理解させ、次に何をさせたいのか」

を逆コンパイルしてください。

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

情報の優先順位を、

P0 / P1 / P2

で分類してください。

## 16. テーブル / 一覧画面逆コンパイル

この一覧画面を完全に仕様化してください。

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

さらに、

0件
1件
大量データ
Loading
Error

の場合のUIも設計してください。

## 17. フォーム逆コンパイル

このフォームを完全に仕様化してください。

各Fieldについて、

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

を抽出してください。

さらに、

- Auto Save
- Draft
- Dirty State
- Unsaved Changes
- Confirm Dialog

が必要か判断してください。

## 18. 検索機能逆コンパイル

このSaaSの検索UXを逆コンパイルしてください。

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

キーボード操作や検索結果UIも推測してください。

## 19. AI SaaS逆コンパイル

このAI SaaSを逆コンパイルしてください。

通常のSaaS分析に加え、

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

の存在をUIから推測してください。

重要：

内部Promptや非公開実装を知っているかのように断定せず、

ユーザーから観察できる挙動から、

「合理的に再構築するとしたらどういうArchitectureになるか」

を記述してください。

## 20. AIチャットUI逆コンパイル

このAIチャット画面を逆コンパイルしてください。

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

推定データモデル：

Conversation
Message
Attachment
ToolCall
Citation
Feedback

まで設計してください。

## 21. AI Agent SaaS逆コンパイル

このAgent型SaaSの実行モデルを逆コンパイルしてください。

分析対象：

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

というループが存在するか。

さらに、

- Task
- Run
- Step
- Tool
- Artifact
- Approval
- Error
- Retry
- Human in the Loop

をEntityとしてモデル化してください。

## 22. API逆コンパイル

このSaaSの画面操作から必要なAPIを逆算してください。

UI操作ごとに、

GET
POST
PATCH
DELETE

を対応づけてください。

例：

ユーザー一覧表示
→ GET /users

ユーザー作成
→ POST /users

ユーザー更新
→ PATCH /users/:id

削除
→ DELETE /users/:id

さらに、

- Request
- Response
- Error
- Pagination
- Filter
- Sort
- Authentication

を含むAPI仕様案を生成してください。

これは実際の非公開APIを特定するのではなく、

**同じプロダクト体験を実現するために必要なAPI設計**

として作成してください。

## 23. Webhook / Integration逆コンパイル

このSaaSのIntegration画面から外部連携設計を推測してください。

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

各Integrationについて、

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

のLifecycleを設計してください。

## 24. 通知システム逆コンパイル

このSaaSのNotification Systemを逆コンパイルしてください。

推測：

- In-app
- Email
- Push
- Slack
- Webhook

イベントごとに、

Event
Recipient
Channel
Template
Trigger
Frequency
Preference

を整理してください。

Notification Preference画面も設計してください。

## 25. Activity Log / Audit Log逆コンパイル

このSaaSの履歴・アクティビティ機能を逆コンパイルしてください。

イベントモデル：

Actor
Action
Target
Timestamp
Metadata

例：

Kai updated Project A

のようなイベントを生成するために必要なデータ構造を推測してください。

監査ログとして必要な、

- IP
- Device
- Before
- After
- Admin Action

も検討してください。

## 26. 管理画面逆コンパイル

このSaaSの表側の機能から、運営側に必要なAdmin Consoleを逆算してください。

運営側で必要になりそうな機能：

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

通常ユーザー向け機能とAdmin専用機能を分離してください。

## 27. エラー設計逆コンパイル

このSaaSについて想定されるFailure Stateを洗い出してください。

例：

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

各Errorについて、

Cause
User Message
Recovery Action
Retry
Logging

を設計してください。

## 28. Empty State逆コンパイル

このSaaSの各ページについて、

「データがまだ存在しない状態」

を設計してください。

Empty Stateを、

- First Use
- No Search Results
- No Permission
- Deleted
- Filter Result 0

に分けてください。

それぞれ、

Title
Description
Illustration
Primary CTA
Secondary CTA

を設計してください。

## 29. レスポンシブ / モバイル逆コンパイル

Desktop版からMobile / Tablet版を逆算してください。

分析：

- Sidebar
- Navigation
- Table
- Modal
- Form
- Toolbar
- Card
- Chart

について、

Desktop → Tablet → Mobile

でどのように変形すべきかを整理してください。

単純縮小ではなく、

優先順位に基づいて情報を削る / 折り畳む / 移動する

設計にしてください。

## 30. アクセシビリティ逆コンパイル

このSaaSをWCAGを意識して再構築すると仮定し、

必要なAccessibility要件を抽出してください。

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

UIデザインを維持しながら必要な改善も提示してください。

## 31. パフォーマンス逆コンパイル

このSaaSを同等の体感速度で実装するために必要なPerformance戦略を推測してください。

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

対象SaaSが実際に採用している技術だとは断定せず、

観察されたUXを再現するために合理的なArchitectureを提案してください。

## 32. セキュリティ逆コンパイル

このSaaSの機能から必要なSecurity Requirementを逆算してください。

検討：

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

特にマルチテナントSaaSとして、

「別Workspaceのデータが絶対に見えない」

ために必要な設計を明示してください。

## 33. SaaSビジネスモデル逆コンパイル

このサービスをプロダクトではなくSaaSビジネスとして逆コンパイルしてください。

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

さらに、

Free → Paid
Individual → Team
Team → Enterprise

のExpansion Pathを推測してください。

## 34. グロース設計逆コンパイル

このSaaSのUI・料金・オンボーディング・共有機能からGrowth Loopを逆コンパイルしてください。

探してください：

- Invite Loop
- Content Loop
- Collaboration Loop
- Sharing Loop
- Template Loop
- Integration Loop
- Data Network Effect

それぞれについて、

Trigger

↓

User Action

↓

External Exposure

↓

New User

↓

Activation

の循環として説明してください。

## 35. マーケティングサイト逆コンパイル

このSaaSのLPを逆コンパイルしてください。

単に文章を抽出するのではなく、

ページの説得構造を分析してください。

例：

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

各Sectionについて、

- 読者の心理状態
- 伝えているMessage
- 使用しているProof
- 次のSectionへ進ませる役割

を説明してください。

## 36. 競合SaaS比較逆コンパイル

SaaS AとSaaS Bを同じフレームワークで逆コンパイルして比較してください。

比較軸：

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

最後に、

「単なる機能差」

ではなく、

**それぞれがユーザーにどのような世界観・仕事の仕方を提案しているか**

まで比較してください。

## 37. MVP逆コンパイル

このSaaSを完全コピーするのではなく、

80%の価値を20%の機能で再現するMVPを設計してください。

すべての機能を、

- P0：これがないと価値が成立しない
- P1：重要だが後から追加可能
- P2：成熟したSaaS向け
- P3：今回は不要

に分類してください。

その後、

- 最小データモデル
- 最小画面
- 最小API
- 最小ユーザーフロー

を定義してください。

## 38. 1週間で作る版

このSaaSのコア体験を1週間で再構築すると仮定してください。

制約：

- エンジニア1〜2人
- Web版のみ
- 完璧な再現不要
- コア体験最優先

Day 1〜Day 7の実装計画を作ってください。

外部SaaSで代替できる機能は積極的に外部サービスを使ってください。

## 39. AIコーディングエージェント向け逆コンパイル

このSaaSをAI Coding Agentが実装できる仕様へ変換してください。

曖昧な説明は禁止。

以下を生成：

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

各機能について、

Given
When
Then

形式のAcceptance Criteriaを付けてください。

## 40. 完全再構築用マスタープロンプト

以下のSaaSを「観察可能なプロダクト仕様から再構築する」という目的で徹底的に逆コンパイルしてください。

対象：
［URL / スクリーンショット / 動画 / 説明をここに入力］

あなたは同時に、

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

として分析してください。

目的は対象サービスのコードを盗むことではありません。

**観察可能なUXから、同等のユーザー価値を独立して再実装するための仕様を作ることです。**

必ず次の順番で分析してください。

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

全機能一覧を、

P0 / P1 / P2 / P3

で分類。

### D. Screen Specification

全画面について、

- Purpose
- Input
- Output
- Action
- State
- Error
- Permission

を記述。

### E. User Flow

主要JTBDのEnd-to-End Flow。

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

Rule形式で記述。

### I. API

UIを成立させるために必要なAPI。

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

主要イベント：

- Viewed
- Clicked
- Created
- Updated
- Deleted
- Invited
- Upgraded
- Completed

などを定義。

### O. MVP

最小構成を抽出。

### P. Implementation

推奨技術構成と実装順。

### Q. Test

Acceptance CriteriaとE2E Test。

---

# 最重要ルール

SaaS逆コンパイルでは、次の3つを混同しない。

## ① Observation

実際に確認できたもの。

例：

「画面右上にInviteボタンが存在する」

## ② Inference

観察から合理的に推論できるもの。

例：

「Workspaceへ別ユーザーを招待できる可能性が高い」

## ③ Speculation

証拠が足りない仮説。

例：

「招待トークンの有効期限は24時間かもしれない」

必ずこの3種類を区別する。

# SaaS逆コンパイルの基本原則

優れた逆コンパイルは、

**Pixel → Component → Screen → Flow → Feature → Data → Rule → System → Business**

の順番で抽象度を上げていく。

画像だけを見るのではない。

Buttonがある
↓
Actionがある
↓
Stateが変化する
↓
Dataが変化する
↓
Business Ruleが存在する
↓
ユーザーの仕事が完了する

という因果関係まで追う。

最終目標は、

**「このSaaSは何色のボタンを使っているか」をコピーすることではなく、「なぜこのSaaSがこの形になったのか」を再構築できること。**
