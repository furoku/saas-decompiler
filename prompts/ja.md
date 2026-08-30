# SaaS Decompiler — 日本語プロンプト集

> 公開ページ、スクリーンショット、実際に利用できる画面、公開ドキュメントなどの観察可能な情報から、SaaSの構造を独立実装できる粒度まで逆算するためのプロンプト集です。非公開コード、秘密情報、認証回避を目的にしません。

## 1. 汎用SaaS逆コンパイル
このSaaSを完全に逆コンパイルしてください。表面的なUI説明ではなく、問題、想定ユーザー、JTBD、価値提案、主要ユースケース、画面構成、情報設計、機能、ユーザーフロー、状態遷移、データ構造、権限、ビジネスルール、デザインシステム、API、外部連携、課金、オンボーディング、通知、検索、管理画面、セキュリティ、非機能要件、実装優先順位まで整理してください。最後に「観察事実 / 高確度の推論 / 低確度の仮説 / MVP必須 / 省略可能」を分離してください。

## 2. スクリーンショットから逆コンパイル
添付スクリーンショットから、ページ目的、階層、ナビゲーション、UIコンポーネント、操作、CRUD、一覧/詳細/編集関係、データ項目、フィルター、ソート、検索、ページネーション、ステータス、権限、モーダル、空状態、ローディング、エラー、状態変化を推論してください。「画面上の証拠 → 推測される仕様 → 確度」で出力してください。

## 3. URLからSaaS全体を逆コンパイル
このURLを起点に、公開範囲でトップ、サインアップ、ログイン、オンボーディング、ダッシュボード、設定、課金、ヘルプ、ドキュメント、FAQ、規約、プライバシー、機能紹介を横断して分析してください。「マーケティングサイトが約束する価値」と「実際に観察できるプロダクト機能」を分離し、最終的にPRD相当の再構築仕様を作ってください。

## 4. UI / UX逆コンパイル
レイアウト、最大幅、グリッド、サイドバー、ヘッダー、余白、情報密度、タイポグラフィ、カラー、Button/Input/Select/Table/Card/Badge/Modal/Drawer/Toast等のコンポーネントと各Stateを分析し、再現用Design Tokenとしてまとめてください。

## 5. デザインシステム逆コンパイル
複数画面から共通ルールを抽出し、Color、Typography、Spacing、Radius、Border、Shadow、Z-index、Icon、Grid、Breakpoint、Motion、Component Variant、Interaction Stateを整理してください。直接確認できない値は推定値として明示し、CSS Variables / Tailwind Themeへ変換可能な形式にしてください。

## 6. フロントエンド構造逆コンパイル
このSaaSを独立再実装すると仮定し、Layout / Page / Feature / Component / UI Primitiveへ分解してください。Routing、Nested Layout、Shared Component、State Management、Server State、Local State、Form State、Optimistic Update、Cache、Pagination、Search Params、URL Stateを設計し、推奨ディレクトリ構造を出してください。

## 7. データモデル逆コンパイル
UIに現れる名称、ID、User、Team、Workspace、Project、Status、Tag、Date、Owner、Permission、Relation等からEntityを抽出してください。EntityごとにField、型、Required/Optional、Relation、Unique Constraint、Index候補、Lifecycleを設計し、ER図/SQL/Prismaへ落とせる形にしてください。

## 8. ユーザーフロー逆コンパイル
主要JTBDごとに Start → Action → System Response → Decision → Next Action → Success のフローを作ってください。Happy Path、初回、リピーター、0件、入力エラー、権限不足、通信エラー、キャンセル、削除、復元の分岐も含めてください。

## 9. 状態遷移逆コンパイル
主要オブジェクトのState Machineを逆算してください。各Stateについて Entry Condition、Allowed Action、Forbidden Action、Next State、Rollback、UI Representationを整理してください。

## 10. ビジネスロジック逆コンパイル
「なぜこのボタンはこの条件で出るのか」「なぜ編集不可なのか」「なぜこのステータスになるのか」をUIから推論してください。RULE-001形式で WHEN / THEN / EXCEPT / UI上の証拠 / 確度 を記述してください。

## 11. 認証・権限逆コンパイル
Sign up、Login、OAuth、Magic Link、Password Reset、Email Verification、MFA、Session、Organization、Workspace、Team、Role、Permissionを推測してください。RBAC/ABACの適性を判断し、Owner/Admin/Member/Viewer/Guest等の権限マトリクスを作ってください。

## 12. Workspace / Team構造逆コンパイル
User / Organization / Workspace / Team / Projectの関係を分析してください。複数Workspace所属、切替、招待、Role、Ownership、Seat、Billing単位、Data Isolation、削除、Ownership Transferを含め、推定ER図を作ってください。

## 13. 課金システム逆コンパイル
料金ページ、設定画面、機能制限からFree/Trial/Pro/Team/Enterprise、Seat課金、Usage課金、Credit制、Monthly/Annual、Trial、Upgrade/Downgrade/Cancel/Invoice/Tax/Coupon/Overageを推測してください。PaywallになっているFeature/Limitを特定し、再実装用Billing Modelを設計してください。

## 14. オンボーディング逆コンパイル
Sign up、Welcome、Persona/Use Case選択、Workspace作成、Import、Integration、Tutorial、Checklist、Sample Data、Empty State、First Successを分析してください。Time to Value短縮施策と、プロダクト側が取得したい情報も推測してください。

## 15. ダッシュボード逆コンパイル
このダッシュボードが「何を理解させ、次に何をさせたいか」を分析してください。Primary KPI、Secondary KPI、Summary、Trend、Alert、Recommendation、Recent Activity、Task、CTA、Filter、Date RangeをP0/P1/P2で分類してください。

## 16. テーブル / 一覧画面逆コンパイル
Columns、型、Sort、Filter、Search、Pagination、Bulk Action、Selection、Row Action、Inline Edit、Status、Link、Export/Import、Saved View、Column Customizationを仕様化してください。0件/1件/大量/Loading/Errorも設計してください。

## 17. フォーム逆コンパイル
各FieldのLabel、Type、Placeholder、Default、Required、Validation、Error Message、Help Text、Dependency、Conditional Display、Submit Conditionを抽出してください。Auto Save、Draft、Dirty State、Unsaved Changes、Confirm Dialogの要否も判断してください。

## 18. 検索機能逆コンパイル
Global/Local Search、Full Text、Prefix、Exact、Fuzzy、Filter、Facet、Sort、Recent Search、History、Command Paletteを分析し、キーボード操作と検索結果UIまで設計してください。

## 19. AI SaaS逆コンパイル
通常分析に加え、Prompt、System Prompt、Context、Memory、Model、Temperature、Tool Calling、RAG、Vector Search、Agent、Workflow、Streaming、Regeneration、Edit、Retry、Model Switchingの存在をUI挙動から推測してください。内部実装を知っているように断定せず、合理的な再構築Architectureとして記述してください。

## 20. AIチャットUI逆コンパイル
Conversation、Message、Role、Streaming、Attachment、Image、File、Citation、Tool Call、Retry、Edit、Branch、Stop、Copy、Feedback、History、Delete、Archiveを分析し、Conversation/Message/Attachment/ToolCall/Citation/Feedbackの推定データモデルを設計してください。

## 21. AI Agent SaaS逆コンパイル
User Request → Planning → Tool Selection → Tool Execution → Observation → Replanning → Result のループがあるか分析してください。Task、Run、Step、Tool、Artifact、Approval、Error、Retry、Human in the LoopをEntityとしてモデル化してください。

## 22. API逆コンパイル
画面操作から同等UXに必要なAPIを設計してください。各操作をGET/POST/PATCH/DELETEへ対応づけ、Request、Response、Error、Pagination、Filter、Sort、Authenticationを含めてください。実際の非公開APIの特定ではなく、独立実装用のAPI仕様にしてください。

## 23. Webhook / Integration逆コンパイル
Integration画面からOAuth、API Key、Webhook、Import、Export、Sync、Trigger、Action、Mappingを推測してください。Connection → Authorization → Configuration → Sync → Error Handling → Disconnect のLifecycleを設計してください。

## 24. 通知システム逆コンパイル
In-app、Email、Push、Slack、Webhook等の通知を推測し、Event、Recipient、Channel、Template、Trigger、Frequency、Preferenceを整理してください。Notification Preference画面も設計してください。

## 25. Activity Log / Audit Log逆コンパイル
Actor、Action、Target、Timestamp、Metadataのイベントモデルを設計してください。監査用途としてIP、Device、Before、After、Admin Actionが必要かも検討してください。

## 26. 管理画面逆コンパイル
表側の機能から運営用Admin Consoleを逆算してください。User/Workspace/Billing/Subscription/Feature Flag/Abuse/Support/Logs/Jobs/Integration/Content/Announcement/Metricsを検討し、通常ユーザー機能と分離してください。

## 27. エラー設計逆コンパイル
400/401/403/404/409/422/429/500、Timeout、Offline、Integration Error、Payment Error等を洗い出し、Cause、User Message、Recovery Action、Retry、Loggingを設計してください。

## 28. Empty State逆コンパイル
各ページのFirst Use、No Search Results、No Permission、Deleted、Filter Result 0を設計し、それぞれTitle、Description、Illustration、Primary CTA、Secondary CTAを定義してください。

## 29. レスポンシブ / モバイル逆コンパイル
DesktopからTablet/Mobileを逆算してください。Sidebar、Navigation、Table、Modal、Form、Toolbar、Card、Chartについて、単純縮小ではなく情報優先度に応じた削除/折り畳み/移動を設計してください。

## 30. アクセシビリティ逆コンパイル
Keyboard、Focus、Contrast、Label、ARIA、Screen Reader、Error、Modal、Dropdown、Table、Form、Motionを点検し、WCAGを意識した独立実装要件を提示してください。

## 31. パフォーマンス逆コンパイル
同等の体感速度を実現するため、SSR、CSR、Streaming、Lazy Load、Prefetch、Cache、Optimistic UI、Skeleton、Pagination、Infinite Scroll、Image Optimization、Code Splittingを検討してください。対象が実際に使う技術とは断定しないでください。

## 32. セキュリティ逆コンパイル
Authentication、Authorization、CSRF、XSS、SQL Injection、Rate Limit、Encryption、Secrets、Audit Log、Session、API Key、Webhook Signature、File Upload、Tenant Isolationを検討してください。特にマルチテナントのデータ分離要件を明示してください。

## 33. SaaSビジネスモデル逆コンパイル
ICP、Persona、JTBD、Acquisition、Activation、Monetization、Retention、Expansion、Referral、Churnを分析してください。Free → Paid → Team → EnterpriseのExpansion Pathも推測してください。

## 34. グロース設計逆コンパイル
Invite、Content、Collaboration、Sharing、Template、Integration、Data Network Effect等のGrowth Loopを探し、Trigger → User Action → External Exposure → New User → Activation の循環として説明してください。

## 35. マーケティングサイト逆コンパイル
Hero → Problem → Value Proposition → Product Demonstration → Use Case → Social Proof → Integration → Pricing → FAQ → CTAの説得構造を分析してください。各Sectionの読者心理、Message、Proof、次のSectionへ進ませる役割を説明してください。

## 36. 競合SaaS比較逆コンパイル
SaaS A/BをTarget User、JTBD、IA、Core Feature、Workflow、UX、Design、Collaboration、AI、Integration、Pricing、Growth Loop、Moatで比較してください。最後に、各社が提案している「仕事の仕方・世界観」の違いまでまとめてください。

## 37. MVP逆コンパイル
対象SaaSの80%の価値を20%の機能で再現するMVPを設計してください。全機能をP0/P1/P2/P3へ分類し、最小データモデル、最小画面、最小API、最小ユーザーフローを定義してください。

## 38. 1週間で作る版
コア体験を1週間、エンジニア1〜2人、Web版のみで独立再実装すると仮定し、Day 1〜Day 7の実装計画を作ってください。外部SaaSで安全に代替できる部分は代替し、コア価値に集中してください。

## 39. AIコーディングエージェント向け逆コンパイル
AI Coding Agentが実装できる仕様に変換してください。Product Overview、User Stories、Routes、Screen Spec、Component Tree、Data Model、API、State、Permission、Validation、Error Handling、Responsive、Acceptance Criteria、Test Cases、Implementation Orderを生成し、各機能にGiven/When/Thenを付けてください。

## 40. 完全再構築用マスタープロンプト
以下のSaaSを、観察可能なプロダクト仕様から独立再実装する目的で徹底分析してください。対象：[URL / スクリーンショット / 動画 / 説明]。Product Manager、UX Researcher、UI Designer、Design System Designer、Frontend/Backend Architect、Database Designer、Security Engineer、Growth PM、QA Engineerとして、A.Product、B.IA、C.Features(P0-P3)、D.Screen Spec、E.User Flow、F.UI System、G.Data Model、H.Business Logic、I.API、J.Auth、K.Billing、L.Integration、M.Non-functional、N.Analytics、O.MVP、P.Implementation、Q.Testの順で出力してください。

---

## 最重要ルール

必ず次の3つを混同しないでください。

- **Observation**: 実際に確認できた事実
- **Inference**: 観察から合理的に推論できる設計
- **Speculation**: 証拠が足りない仮説

優れた逆コンパイルは、**Pixel → Component → Screen → Flow → Feature → Data → Rule → System → Business** の順で抽象度を上げます。
