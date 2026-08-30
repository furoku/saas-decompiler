# SaaS Decompiler — English Prompt Library

Here, “SaaS decompilation” means inferring a SaaS product’s design philosophy and structure from observable information such as public websites, accessible product screens, screenshots, URLs, and public documentation.

## 1. General SaaS Decompilation

Decompile this SaaS completely.

Do not stop at a superficial UI description. Structure the product at a level detailed enough to rebuild it from scratch.

Analyze:

- The problem the SaaS solves
- Target users
- JTBD (the job the user is trying to get done)
- Core value
- Major use cases
- Screen structure
- Information architecture
- Navigation
- Feature inventory
- User flows
- State transitions
- Data structures
- Permission structure
- Business rules
- UI design system
- Component structure
- Functions that would likely be required as APIs
- External service integrations
- Billing model
- Onboarding
- Retention design
- Error handling
- Empty states
- Notifications
- Search
- Filters
- Admin console
- Security requirements
- Non-functional requirements
- Implementation priority

At the end, separate:

1. Facts directly observed
2. High-confidence inferred design
3. Speculation only
4. Parts that could be omitted in a reconstruction
5. Parts absolutely required for the MVP

## 2. Decompile SaaS from Screenshots

Decompile the structure of this product from the attached SaaS screenshots.

Do not merely describe what is visible. Infer:

“If this screen exists, what functions, data, states, and rules must exist behind it?”

Analyze:

- Page purpose
- Page hierarchy
- Global navigation
- Local navigation
- UI components
- Interactive elements
- CRUD operations
- Relationships between list / detail / edit views
- Data fields
- Data types
- Relationships between data
- Filters
- Sorting
- Search
- Pagination
- Statuses
- Permissions
- Modals
- Drawers
- Toasts
- Empty states
- Loading states
- Error states
- State changes caused by user actions

For each element, write:

**Evidence visible on screen → Inferred specification**

## 3. Decompile an Entire SaaS from a URL

Decompile the SaaS at this URL while exploring the site as broadly as possible.

Do not inspect only one page. Where accessible, review:

- Home page
- Sign-up
- Login
- Onboarding
- Dashboard
- Settings
- Billing
- Help
- Documentation
- FAQ
- Terms of service
- Privacy policy
- Public feature pages

Then separate:

**The value promised by the marketing site**

from

**The functionality actually provided by the product**

Finally, generate a Product Requirements Document-level specification for rebuilding this SaaS.

## 4. UI / UX Decompilation

Decompile this SaaS’s UI / UX design in detail.

Analyze:

### Layout

- Max width
- Grid
- Sidebar width
- Header height
- Column structure
- Spacing rules
- Content density

### Typography

- Font family / category
- Type scale
- Weight
- Line height
- Heading hierarchy
- Numeric display

### Colors

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

### Components

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

For each, infer:

- Appearance
- Size
- Variant
- State
- Hover
- Focus
- Disabled
- Loading
- Error

Finally, summarize everything as reusable Design Tokens.

## 5. Design System Decompilation

Extract the design system from this SaaS.

Do not copy individual pages. Discover rules shared across multiple pages.

Extract:

- Color Tokens
- Typography Tokens
- Spacing Tokens
- Radius
- Border
- Shadow
- Z-index
- Icons
- Grid
- Breakpoints
- Motion
- Component Variants
- Interaction States

If a value cannot be directly confirmed, label it explicitly as:

“Estimated from appearance.”

Where possible, organize the result so it can be converted into CSS Variables, a Tailwind Theme, or generic Design Tokens.

## 6. Frontend Architecture Decompilation

Decompile this SaaS as a frontend engineer.

Assume the screens will be rebuilt using React / Next.js or a similar stack, and decompose the product into:

- Layout
- Page
- Feature
- Component
- UI Primitive

Infer:

- Routing
- Nested Layouts
- Shared Components
- Feature Components
- State Management
- Server State
- Local State
- Form State
- Optimistic Updates
- Cache
- Pagination
- Infinite Scroll
- Search Params
- URL State

Finally, generate a recommended directory structure.

Do not claim that the original SaaS actually uses any specific internal technology. Present the result as:

“A reasonable architecture if rebuilding the product.”

## 7. Data Model Decompilation

Infer the underlying data model from this SaaS’s UI.

Extract entities from visible concepts such as:

- Name
- ID
- User
- Team
- Workspace
- Project
- Status
- Tag
- Date
- Owner
- Permission
- Relation

For each entity, infer:

- Entity name
- Role
- Fields
- Data types
- Required / Optional
- Relations
- Unique constraints
- Candidate indexes
- Lifecycle

Finally, produce a structure that can be converted into:

- ER diagram
- SQL Schema
- Prisma Schema or equivalent

Every inferred part must include a confidence level.

## 8. User Flow Decompilation

Decompile the steps users take to achieve their goals in this SaaS.

For each major JTBD, write the flow as:

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

Also infer branches for:

- Happy Path
- First-time user
- Returning user
- Zero-data state
- Input error
- Insufficient permission
- Network error
- Cancel
- Delete
- Restore

## 9. State Transition Decompilation

Infer the State Machine for major objects in this SaaS.

For example:

Draft
↓
Processing
↓
Completed

Use UI evidence such as Badges, Buttons, Menus, and visibility changes to infer state transitions.

For each state, document:

- State
- Entry Condition
- Allowed Action
- Forbidden Action
- Next State
- Rollback
- UI Representation

## 10. Business Logic Decompilation

Infer the business rules behind this SaaS from its UI.

Go beyond CRUD. Analyze questions such as:

“Why is this button visible only under this condition?”

“Why can this data not be edited?”

“Why does this object enter this status?”

Output rules in this format:

RULE-001

Condition:
WHEN ...

Action:
THEN ...

Exception:
EXCEPT ...

UI evidence:

Confidence:
High / Medium / Low

## 11. Authentication / Authorization Decompilation

Decompile this SaaS’s Authentication / Authorization design.

Infer:

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

Infer whether RBAC or ABAC is more appropriate.

Example roles:

- Owner
- Admin
- Member
- Viewer
- Guest

For each role, build a permission matrix covering:

View / Create / Edit / Delete / Invite / Billing / Admin

## 12. Workspace / Team Structure Decompilation

Decompile this SaaS’s account structure.

In particular, analyze the relationship among:

User
Organization
Workspace
Team
Project

Check:

- Whether one user can belong to multiple Workspaces
- Whether Workspace switching exists
- Invitation functionality
- Roles
- Ownership
- Seats
- Billing unit
- Data isolation
- Workspace deletion
- Ownership transfer

Create an inferred ER diagram.

## 13. Billing System Decompilation

Decompile the Billing structure from the pricing page, settings, and product limitations.

Analyze:

- Free / Trial
- Pro
- Team
- Enterprise
- Seat-based pricing
- Usage-based pricing
- Credit model
- Monthly / Annual
- Trial period
- Upgrade
- Downgrade
- Cancel
- Refund
- Invoice
- Tax
- Coupon
- Overage

Also identify:

**Which Features / Limits are behind a Paywall**

Then translate the result into a Billing Model suitable for rebuilding the product with Stripe or an equivalent service.

## 14. Onboarding Decompilation

Decompile the first-time user experience of this SaaS.

Analyze:

- Sign up
- Welcome
- Persona selection
- Use Case selection
- Workspace creation
- Import
- Integration
- Tutorial
- Checklist
- Sample Data
- Empty State
- First Success

In particular, explain:

**What the product does to shorten Time to Value**

Also infer what user information the product is trying to collect during onboarding.

## 15. Dashboard Decompilation

Decompile what this dashboard is trying to make the user understand and what it wants them to do next.

Analyze:

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

Classify information priority as:

P0 / P1 / P2

## 16. Table / List View Decompilation

Fully specify this list view.

Analyze:

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

Also design the UI for:

0 items
1 item
Large dataset
Loading
Error

## 17. Form Decompilation

Fully specify this form.

For every field, extract:

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

Also decide whether the form requires:

- Auto Save
- Draft
- Dirty State
- Unsaved Changes
- Confirm Dialog

## 18. Search Decompilation

Decompile the search UX of this SaaS.

Analyze:

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

Also infer keyboard behavior and search-result UI.

## 19. AI SaaS Decompilation

Decompile this AI SaaS.

In addition to normal SaaS analysis, infer from the UI whether it appears to use:

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

Important:

Do not claim to know internal prompts or private implementation details.

From behavior observable by users, describe:

“What would be a reasonable architecture if rebuilding this independently?”

## 20. AI Chat UI Decompilation

Decompile this AI chat interface.

Analyze:

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

Design an inferred data model including:

Conversation
Message
Attachment
ToolCall
Citation
Feedback

## 21. AI Agent SaaS Decompilation

Decompile the execution model of this agent-style SaaS.

Determine whether a loop like the following exists:

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

Also model the following as entities:

- Task
- Run
- Step
- Tool
- Artifact
- Approval
- Error
- Retry
- Human in the Loop

## 22. API Decompilation

Infer the APIs required from this SaaS’s screen operations.

Map each UI operation to:

GET
POST
PATCH
DELETE

Example:

Display user list
→ GET /users

Create user
→ POST /users

Update user
→ PATCH /users/:id

Delete user
→ DELETE /users/:id

Also generate an API specification including:

- Request
- Response
- Error
- Pagination
- Filter
- Sort
- Authentication

Do not try to identify the actual private API. Design the API required to reproduce the same product experience independently.

## 23. Webhook / Integration Decompilation

Infer external integration design from this SaaS’s Integration screens.

Analyze:

- OAuth
- API Key
- Webhook
- Import
- Export
- Sync
- Trigger
- Action
- Mapping

For each integration, design the lifecycle:

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

## 24. Notification System Decompilation

Decompile this SaaS’s Notification System.

Infer channels such as:

- In-app
- Email
- Push
- Slack
- Webhook

For each event, organize:

Event
Recipient
Channel
Template
Trigger
Frequency
Preference

Also design a Notification Preference screen.

## 25. Activity Log / Audit Log Decompilation

Decompile this SaaS’s history and activity features.

Event model:

Actor
Action
Target
Timestamp
Metadata

Infer the data structure required to generate events such as:

Kai updated Project A

Also consider audit-log fields such as:

- IP
- Device
- Before
- After
- Admin Action

## 26. Admin Console Decompilation

Infer the internal Admin Console required to operate this SaaS from the user-facing product.

Potential operator features:

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

Separate normal user functions from admin-only functions.

## 27. Error Design Decompilation

Enumerate likely Failure States for this SaaS.

Examples:

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

For every Error, design:

Cause
User Message
Recovery Action
Retry
Logging

## 28. Empty State Decompilation

For each relevant page in this SaaS, design the state where data does not yet exist.

Separate Empty States into:

- First Use
- No Search Results
- No Permission
- Deleted
- Filter Result 0

For each, design:

Title
Description
Illustration
Primary CTA
Secondary CTA

## 29. Responsive / Mobile Decompilation

Infer Mobile / Tablet behavior from the Desktop version.

Analyze:

- Sidebar
- Navigation
- Table
- Modal
- Form
- Toolbar
- Card
- Chart

Describe how each should transform across:

Desktop → Tablet → Mobile

Do not simply shrink everything. Design hiding, collapsing, or relocation based on information priority.

## 30. Accessibility Decompilation

Assume this SaaS will be rebuilt with WCAG in mind and extract the necessary accessibility requirements.

Analyze:

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

Also propose improvements that preserve the visual design.

## 31. Performance Decompilation

Infer the performance strategies required to implement this SaaS with equivalent perceived speed.

Analyze:

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

Do not claim that the original SaaS actually uses these technologies. Propose a reasonable architecture for reproducing the observed UX.

## 32. Security Decompilation

Infer the Security Requirements needed from this SaaS’s feature set.

Consider:

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

For a multi-tenant SaaS in particular, explicitly define the design required so that:

“Data from another Workspace can never be accessed.”

## 33. SaaS Business Model Decompilation

Decompile this service as a SaaS business rather than only as a product.

Analyze:

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

Also infer the Expansion Path:

Free → Paid
Individual → Team
Team → Enterprise

## 34. Growth Design Decompilation

Decompile the Growth Loops implied by this SaaS’s UI, pricing, onboarding, and sharing features.

Look for:

- Invite Loop
- Content Loop
- Collaboration Loop
- Sharing Loop
- Template Loop
- Integration Loop
- Data Network Effect

Explain each loop as:

Trigger

↓

User Action

↓

External Exposure

↓

New User

↓

Activation

## 35. Marketing Site Decompilation

Decompile this SaaS’s landing page.

Do not merely extract copy. Analyze the persuasion structure.

Example:

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

For each section, explain:

- Reader’s psychological state
- Message being communicated
- Proof being used
- Role in moving the reader to the next section

## 36. Competitive SaaS Comparison Decompilation

Decompile SaaS A and SaaS B using the same framework and compare them.

Compare:

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

Finally, go beyond simple feature differences and compare:

**What worldview and way of working each product proposes to the user.**

## 37. MVP Decompilation

Do not fully clone this SaaS. Design an MVP that reproduces 80% of the value with 20% of the functionality.

Classify every feature as:

- P0: Without this, the value proposition fails
- P1: Important, but can be added later
- P2: Appropriate for a mature SaaS
- P3: Not required for this version

Then define:

- Minimum data model
- Minimum screens
- Minimum API
- Minimum user flow

## 38. Build-in-One-Week Version

Assume the core experience of this SaaS must be rebuilt in one week.

Constraints:

- 1–2 engineers
- Web only
- Perfect reproduction is unnecessary
- Core experience first

Create a Day 1 through Day 7 implementation plan.

Use external SaaS aggressively for commodity capabilities that do not need to be built in-house.

## 39. Decompilation for AI Coding Agents

Convert this SaaS into an implementation specification that an AI Coding Agent can execute.

Ambiguous descriptions are not allowed.

Generate:

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

For every feature, include Acceptance Criteria in:

Given
When
Then

format.

## 40. Full Reconstruction Master Prompt

Thoroughly decompile the following SaaS for the purpose of rebuilding it from observable product specifications.

Target:
[URL / screenshots / video / description]

Act simultaneously as:

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

The goal is not to steal the target service’s code.

**The goal is to produce a specification for independently implementing equivalent user value from observable UX.**

Analyze in this exact order:

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

Classify the complete feature inventory as:

P0 / P1 / P2 / P3

### D. Screen Specification

For every screen, document:

- Purpose
- Input
- Output
- Action
- State
- Error
- Permission

### E. User Flow

End-to-End Flows for major JTBDs.

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

Describe in Rule format.

### I. API

Define the APIs needed to make the UI work.

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

Define major events such as:

- Viewed
- Clicked
- Created
- Updated
- Deleted
- Invited
- Upgraded
- Completed

### O. MVP

Extract the minimum viable configuration.

### P. Implementation

Recommend the technology architecture and implementation order.

### Q. Test

Define Acceptance Criteria and E2E Tests.

---

# Most Important Rule

In SaaS decompilation, never mix the following three categories.

## ① Observation

Something that can actually be verified.

Example:

“An Invite button exists in the upper-right corner of the screen.”

## ② Inference

Something that can reasonably be inferred from observations.

Example:

“It is likely possible to invite another user into the Workspace.”

## ③ Speculation

A hypothesis without enough evidence.

Example:

“The invitation token may expire after 24 hours.”

Always keep these three categories separate.

# Core Principle of SaaS Decompilation

A strong decompilation raises the level of abstraction in this order:

**Pixel → Component → Screen → Flow → Feature → Data → Rule → System → Business**

Do not look only at the image.

There is a Button
↓
There is an Action
↓
State changes
↓
Data changes
↓
A Business Rule exists
↓
The user’s job is completed

Follow the causal chain all the way through.

The final goal is not to copy “what color button this SaaS uses.” It is to reconstruct **why the SaaS took this form.**
