# SaaS Decompiler — English Prompt Library

> A prompt library for inferring SaaS structure from observable information such as public pages, screenshots, accessible product screens, and public documentation. It is not intended to obtain private source code, secrets, or bypass authentication.

## 1. General SaaS Decompilation
Decompile this SaaS in depth. Go beyond describing the UI: reconstruct the problem, target users, JTBD, value proposition, key use cases, screens, information architecture, features, user flows, state transitions, data model, permissions, business rules, design system, APIs, integrations, billing, onboarding, notifications, search, admin capabilities, security, non-functional requirements, and implementation priorities. End by separating Observations / High-confidence Inferences / Low-confidence Speculation / MVP essentials / Optional parts.

## 2. Decompile from Screenshots
From the attached screenshots, infer page purpose, hierarchy, navigation, UI components, actions, CRUD behavior, list/detail/edit relationships, data fields, filters, sorting, search, pagination, statuses, permissions, modals, empty states, loading, errors, and state changes. Output each finding as: Visible evidence → Inferred specification → Confidence.

## 3. Decompile an Entire SaaS from a URL
Starting from this URL, inspect the publicly accessible home page, signup, login, onboarding, dashboard, settings, billing, help, docs, FAQ, terms, privacy, and feature pages. Separate what the marketing site promises from what the product visibly provides, then produce a PRD-level reconstruction specification.

## 4. UI / UX Decompilation
Analyze layout, max width, grid, sidebar, header, spacing, information density, typography, color system, and components such as Button/Input/Select/Table/Card/Badge/Modal/Drawer/Toast including their states. Summarize the result as reusable design tokens.

## 5. Design System Decompilation
Extract cross-screen rules for Color, Typography, Spacing, Radius, Border, Shadow, Z-index, Icons, Grid, Breakpoints, Motion, Component Variants, and Interaction States. Clearly mark estimated values and format the result so it can be converted into CSS Variables or a Tailwind theme.

## 6. Frontend Architecture Decompilation
Assume you are rebuilding this SaaS independently. Decompose it into Layout / Page / Feature / Component / UI Primitive. Design Routing, Nested Layouts, Shared Components, State Management, Server State, Local State, Form State, Optimistic Updates, Cache, Pagination, Search Params, and URL State. Produce a recommended directory structure.

## 7. Data Model Decompilation
Infer entities from visible concepts such as names, IDs, Users, Teams, Workspaces, Projects, Statuses, Tags, Dates, Owners, Permissions, and Relations. For each entity define Fields, Types, Required/Optional, Relations, Unique Constraints, Candidate Indexes, and Lifecycle. Make it convertible into an ERD, SQL schema, or Prisma schema.

## 8. User Flow Decompilation
For each major JTBD, build a Start → Action → System Response → Decision → Next Action → Success flow. Include branches for happy path, first-time users, returning users, zero-data states, input errors, insufficient permissions, network errors, cancel, delete, and restore.

## 9. State Machine Decompilation
Infer state machines for major objects. For each state document Entry Condition, Allowed Actions, Forbidden Actions, Next States, Rollback, and UI Representation.

## 10. Business Logic Decompilation
Infer why controls appear only under certain conditions, why some data is not editable, and why statuses change. Write rules as RULE-001 with WHEN / THEN / EXCEPT / UI evidence / Confidence.

## 11. Authentication & Authorization Decompilation
Infer Signup, Login, OAuth, Magic Link, Password Reset, Email Verification, MFA, Session, Organization, Workspace, Team, Roles, and Permissions. Decide whether RBAC or ABAC fits better and create a role matrix for Owner/Admin/Member/Viewer/Guest or equivalent roles.

## 12. Workspace / Team Structure Decompilation
Analyze relations among User / Organization / Workspace / Team / Project. Include multi-workspace membership, switching, invitations, roles, ownership, seats, billing unit, data isolation, deletion, and ownership transfer. Produce an inferred ERD.

## 13. Billing System Decompilation
Infer Free/Trial/Pro/Team/Enterprise, seat-based pricing, usage pricing, credits, monthly/annual plans, trial, upgrade, downgrade, cancel, invoices, tax, coupons, and overage from pricing and product limits. Identify paywalled features/limits and design a billing model for independent implementation.

## 14. Onboarding Decompilation
Analyze Signup, Welcome, Persona/Use Case selection, Workspace creation, Import, Integrations, Tutorial, Checklist, Sample Data, Empty States, and First Success. Explain how the product reduces Time to Value and what user data it is likely trying to collect.

## 15. Dashboard Decompilation
Analyze what the dashboard wants users to understand and do next. Classify Primary KPI, Secondary KPI, Summary, Trend, Alert, Recommendation, Recent Activity, Task, CTA, Filter, and Date Range as P0/P1/P2.

## 16. Table / List View Decompilation
Specify Columns, Types, Sort, Filter, Search, Pagination, Bulk Actions, Selection, Row Actions, Inline Edit, Status, Links, Export/Import, Saved Views, and Column Customization. Also design states for zero rows, one row, large datasets, loading, and errors.

## 17. Form Decompilation
For each field infer Label, Type, Placeholder, Default, Required, Validation, Error Message, Help Text, Dependencies, Conditional Display, and Submit Conditions. Decide whether Auto Save, Draft, Dirty State, Unsaved Changes, and Confirm Dialog are needed.

## 18. Search Decompilation
Analyze Global/Local Search, Full Text, Prefix, Exact Match, Fuzzy Search, Filters, Facets, Sort, Recent Search, History, and Command Palette. Design keyboard behavior and search-result UI.

## 19. AI SaaS Decompilation
In addition to normal SaaS analysis, infer from observable behavior whether the product uses Prompt, System Prompt, Context, Memory, Model selection, Temperature, Tool Calling, RAG, Vector Search, Agents, Workflows, Streaming, Regeneration, Editing, Retry, and Model Switching. Do not claim hidden implementation details; describe a reasonable independent architecture.

## 20. AI Chat UI Decompilation
Analyze Conversation, Message, Role, Streaming, Attachments, Images, Files, Citations, Tool Calls, Retry, Edit, Branching, Stop, Copy, Feedback, History, Delete, and Archive. Design inferred entities for Conversation/Message/Attachment/ToolCall/Citation/Feedback.

## 21. AI Agent SaaS Decompilation
Determine whether the product follows User Request → Planning → Tool Selection → Tool Execution → Observation → Replanning → Result. Model Task, Run, Step, Tool, Artifact, Approval, Error, Retry, and Human-in-the-Loop as entities.

## 22. API Decompilation
Design the APIs required to reproduce the observed UX. Map operations to GET/POST/PATCH/DELETE and specify Request, Response, Errors, Pagination, Filters, Sort, and Authentication. Do not identify private endpoints; produce an independent API specification.

## 23. Webhook / Integration Decompilation
Infer OAuth, API Keys, Webhooks, Import, Export, Sync, Trigger, Action, and Mapping from the integration UX. Design the lifecycle Connection → Authorization → Configuration → Sync → Error Handling → Disconnect.

## 24. Notification System Decompilation
Infer In-app, Email, Push, Slack, Webhook, or similar channels. Define Event, Recipient, Channel, Template, Trigger, Frequency, and Preference. Design a Notification Preferences screen.

## 25. Activity Log / Audit Log Decompilation
Design an event model with Actor, Action, Target, Timestamp, and Metadata. Consider whether IP, Device, Before, After, and Admin Action are needed for auditability.

## 26. Admin Console Decompilation
Infer the internal Admin Console required by the public product: User, Workspace, Billing, Subscription, Feature Flags, Abuse, Support, Logs, Jobs, Integrations, Content, Announcements, and Metrics. Separate admin-only functions from normal user functions.

## 27. Error Design Decompilation
Enumerate 400/401/403/404/409/422/429/500, Timeout, Offline, Integration Error, Payment Error, and other likely failures. For each define Cause, User Message, Recovery Action, Retry behavior, and Logging.

## 28. Empty State Decompilation
Design First Use, No Search Results, No Permission, Deleted, and Filter Result 0 states for each relevant page. Define Title, Description, Illustration, Primary CTA, and Secondary CTA.

## 29. Responsive / Mobile Decompilation
Infer Tablet and Mobile behavior from Desktop. For Sidebar, Navigation, Table, Modal, Form, Toolbar, Card, and Chart, design priority-based hiding, collapsing, or relocation instead of simple scaling.

## 30. Accessibility Decompilation
Review Keyboard, Focus, Contrast, Labels, ARIA, Screen Reader support, Error handling, Modal, Dropdown, Table, Form, and Motion. Produce requirements for a WCAG-aware independent implementation.

## 31. Performance Decompilation
To reproduce perceived speed, evaluate SSR, CSR, Streaming, Lazy Load, Prefetch, Cache, Optimistic UI, Skeletons, Pagination, Infinite Scroll, Image Optimization, and Code Splitting. Do not claim the original product actually uses these technologies.

## 32. Security Decompilation
Design requirements for Authentication, Authorization, CSRF, XSS, SQL Injection, Rate Limiting, Encryption, Secrets, Audit Logs, Sessions, API Keys, Webhook Signatures, File Uploads, and Tenant Isolation. Explicitly define multi-tenant data-isolation requirements.

## 33. SaaS Business Model Decompilation
Analyze ICP, Persona, JTBD, Acquisition, Activation, Monetization, Retention, Expansion, Referral, and Churn. Infer the likely expansion path from Free → Paid → Team → Enterprise.

## 34. Growth Design Decompilation
Look for Invite, Content, Collaboration, Sharing, Template, Integration, and Data Network Effect loops. Explain each as Trigger → User Action → External Exposure → New User → Activation.

## 35. Marketing Site Decompilation
Analyze the persuasion structure Hero → Problem → Value Proposition → Product Demonstration → Use Case → Social Proof → Integration → Pricing → FAQ → CTA. For each section explain reader psychology, message, proof, and the role it plays in moving users forward.

## 36. Competitive SaaS Comparison
Decompile SaaS A and SaaS B with the same framework and compare Target User, JTBD, IA, Core Feature, Workflow, UX, Design, Collaboration, AI, Integrations, Pricing, Growth Loop, and Moat. End with the different ways of working or worldviews each product proposes.

## 37. MVP Decompilation
Design an MVP that reproduces roughly 80% of user value with roughly 20% of the functionality. Classify features into P0/P1/P2/P3, then define the minimum Data Model, Screens, APIs, and User Flows.

## 38. Build It in One Week
Assume 1–2 engineers, web only, one week, and no need for perfect fidelity. Create a Day 1–Day 7 implementation plan that prioritizes the core experience and safely outsources commodity functionality to external SaaS where appropriate.

## 39. Decompilation for AI Coding Agents
Convert the product into an implementation-ready specification for an AI coding agent: Product Overview, User Stories, Routes, Screen Specification, Component Tree, Data Model, APIs, State, Permissions, Validation, Error Handling, Responsive Behavior, Acceptance Criteria, Test Cases, and Implementation Order. Add Given/When/Then criteria for each feature.

## 40. Full Reconstruction Master Prompt
Analyze the following SaaS for the purpose of independently rebuilding its observable product behavior. Target: [URL / screenshots / video / description]. Act as Product Manager, UX Researcher, UI Designer, Design System Designer, Frontend/Backend Architect, Database Designer, Security Engineer, Growth PM, and QA Engineer. Output in order: A.Product, B.IA, C.Features(P0-P3), D.Screen Spec, E.User Flow, F.UI System, G.Data Model, H.Business Logic, I.API, J.Auth, K.Billing, L.Integrations, M.Non-functional, N.Analytics, O.MVP, P.Implementation, Q.Test.

---

## Most Important Rule

Never mix these three categories:

- **Observation**: directly visible facts
- **Inference**: reasonable design conclusions from evidence
- **Speculation**: hypotheses with insufficient evidence

A strong decompilation raises abstraction in this order: **Pixel → Component → Screen → Flow → Feature → Data → Rule → System → Business**.
