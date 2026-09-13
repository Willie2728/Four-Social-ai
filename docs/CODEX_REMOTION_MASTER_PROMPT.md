# Copy/Paste Master Prompt for Secondary ChatGPT Account with Codex

Use the following as the instruction to Codex.

---

You are working on the production product **4-Social / Four-Social AI**, powered by the **Implement AI** autonomous workforce layer.

GitHub source-of-truth repository:
`Willie2728/Four-Social-ai`

## Mission

Perform a disciplined product-engineering and marketing-production handoff. Do not invent functionality, testimonials, traction, ratings, integrations, or benchmark results. Inspect the repository and the audit documents first. Separate all product capabilities into **LIVE**, **BETA**, **PLANNED**, or **BLOCKED**. Marketing may demonstrate only LIVE functionality as fact; BETA and PLANNED capabilities must be labeled accurately.

## STEP 1 — Clone and inspect GitHub

1. Clone `Willie2728/Four-Social-ai`.
2. Read every file in `docs/` before writing code or marketing copy.
3. Inspect the repository structure and determine whether the full Base44 application source has been synchronized into GitHub.
4. If the full app source is absent, do NOT fabricate a replacement and do NOT claim to have updated the Base44 product. Preserve the audit/handoff documentation, create the Remotion marketing workspace in this repository, and clearly report that the Base44 source sync/export is still required before code-level parity work can occur.
5. If app source is present, run build, lint, typecheck and tests before changing anything. Record failures.
6. Never commit API keys, OAuth secrets, ElevenLabs keys, social tokens, or private customer data.

## STEP 2 — Product quality standard

The goal is a production-quality AI social/marketing/business operating system, not a mock dashboard.

Critical product principles:
- Every visible primary button must work, explain why it is disabled, or be labeled Demo/Beta/Coming Soon.
- No fake “Connected,” “Live,” success state, analytics, follower counts, ratings, customer counts, ROAS, revenue, or activity.
- Use official social APIs/connectors and obey capability restrictions.
- Build capability-aware platform adapters rather than pretending every platform supports identical actions.
- Keep the AI layer provider-neutral and LLM-agnostic.
- Keep avatar rendering/TTS provider-neutral.
- Include approval gates and audit logs for autonomous actions.

## STEP 3 — Required product architecture when app code is available

### A. AI Gateway
Create a provider-neutral AI interface so UI components never call one vendor directly.

Support adapters or extension points for:
- OpenAI
- Anthropic
- Google Gemini
- Base44
- custom OpenAI-compatible endpoint
- future local/self-hosted providers

Core operations:
- completion/chat
- streaming
- structured JSON output
- multimodal input
- tool/function calling
- health check
- usage/cost reporting

Include routing policy, fallback, timeout, retries, budget limits, latency metrics and provider audit logging.

### B. Social Publisher
Implement a common publisher contract with explicit per-provider capability flags:
- connect account
- validate media
- publish now
- schedule
- get job status
- cancel/edit where supported
- comments/replies
- DMs where supported
- analytics
- webhook/event ingestion

Required reliability:
- idempotency
- retry/backoff
- delivery receipt
- user-visible failure reason
- retry control
- history/audit log
- no false-success toast

### C. Create Once → Publish Everywhere
A user creates one source post and chooses destination platforms. AI adapts the source into platform-specific versions while preserving user intent.

Provide:
- platform previews
- per-platform editable copy
- media validation
- aspect-ratio warnings
- title/description/hashtags/CTA optimization
- best-time suggestion based on real account data when available
- schedule or publish
- receipt/status for every destination
- clear fallback when direct API publishing is unavailable

### D. Implement AI workforce
Implement AI is the orchestration layer. Departments include:
- CampaignPilot AI — marketing/media buying
- SocialMind AI — community, DMs, comments
- CreatorForge AI — content/media
- TrendHunter AI — micro-trend intelligence
- Insight Engine AI — finance/ROI/analytics
- ComplianceCore AI — policy/compliance

Agents must be proactive rather than passive. They may create recommendations and tasks based on configured triggers, but execution authority must follow an autonomy ladder:
1. Recommend only
2. Draft for approval
3. Execute after approval
4. Auto-execute within explicit rules/budgets
5. Full autonomy only inside explicitly authorized policy

Agents should cross-collaborate. Examples:
- TrendHunter detects a micro-trend → CreatorForge prepares creative → ComplianceCore reviews → CampaignPilot proposes spend → Insight Engine measures results.
- Marketing asks Finance whether spend fits budget.
- Marketing asks Compliance whether an ad or claim is acceptable.

Every agent action must be logged with source data, reasoning summary suitable for audit, action taken, provider/tool used, cost, status and approval identity when applicable.

### E. Photoreal conversational Avatar Runtime
Design a provider-neutral runtime for a photoreal, rigged conversational avatar.

It must be able to accept either:
- locally rendered GLB/FBX/Three.js avatar assets with rig/blendshapes, or
- a streamed conversational-avatar vendor session.

Support:
- microphone input
- speech-to-text
- TTS abstraction with ElevenLabs adapter
- viseme/phoneme timeline
- lip sync
- facial blendshapes
- eye/gaze behavior
- gesture events
- interruption/barge-in
- captions/transcript
- audio state
- boardroom seat state
- standing presenter state
- pointer/whiteboard interaction state
- connection/recovery fallback to 2D avatar + text

Do not lock the UI to one avatar or voice provider.

### F. AI Boardroom
The user can call a meeting, select agents, set an agenda and query by voice or text.

Required modes:
- Boardroom Mode
- Presenter Mode
- Proctor Mode

Presenter Mode:
- selected agent takes the floor
- avatar appears standing at presentation area
- slide deck, charts, graphs, videos or whiteboard can be displayed
- agent narrates slide-by-slide
- pointer/highlight events synchronize with presentation
- other agents may ask role-relevant questions

Proctor Mode:
- manage agenda and speaking order
- identify unresolved questions
- summarize agreements/disagreements
- record decisions
- create action items
- assign owners/due dates
- generate meeting minutes

### G. TrendHunter proactive intelligence
TrendHunter should seek weak/early signals rather than only mainstream trends.

Monitor configured public/connected sources for:
- engagement acceleration
- unusual comment velocity
- sentiment changes
- emerging phrases
- rising sounds/formats
- local/regional changes
- niche community movement
- competitor creative patterns

Report:
- signal
- evidence/source
- confidence
- velocity
- expected shelf life
- affected demographic/platform
- recommended action
- cost/risk

Never fabricate a trend when live evidence is unavailable.

### H. Unified Inbox
Unify supported DMs, comments and email into one workflow.

AI can:
- classify
- prioritize
- summarize
- draft
- route
- escalate
- auto-reply within explicit policy

High-value, sensitive, legal, financial, harassment, refund, dispute and ambiguous conversations should be escalated according to policy rather than blindly auto-sent.

### I. Media Studio
Build toward a reliable creator studio that responds directly to competitor pain points:
- transcript-guided clipping
- narrative-aware clip boundaries
- editable subtitles
- brand templates
- thumbnail/image generation interface
- voice generation interface
- video generation interface
- preview before expensive generation/render
- 1080p/4K export pathways
- render status and failure reason
- automatic internal-credit rollback on failed renders
- per-platform derivatives

### J. Analytics / ROI
Unify organic performance, paid spend and revenue where connectors permit.

Track:
- impressions/views
- watch time/retention
- engagement
- CTR
- leads
- conversions
- revenue
- product revenue
- ad spend
- CPM/CPC/CPA
- CAC
- ROAS
- contribution margin when inputs exist

AI should recommend best times, platforms, audiences, creatives and budget reallocations based on real observed data and show the evidence behind recommendations.

### K. Creator Commerce / Ufolio
Long-term capability should include:
- branded storefront
- custom domain
- digital products
- courses
- bookings
- memberships
- lead magnets
- affiliates
- email sequences
- customer management
- product analytics
- mobile fulfillment
- transparent fee display

## STEP 4 — Competitive positioning research supplied by repository

Read `docs/COMPETITOR_INTELLIGENCE.md`.

Position competitors fairly:
- Blotato: strong unified publishing/API/MCP and automation.
- Crayo: strong rapid short-form/faceless content-generation breadth.
- Stan: strong creator storefront and monetization workflows.

4-Social’s intended differentiation is the connection of all these categories plus proactive AI employees, unified ROI intelligence, inbox automation and embodied AI meetings.

Do NOT say competitors are scams, broken, useless, or inferior as universal facts. Individual public complaints are anecdotal. Use language such as:
- “Creators frequently ask for…”
- “A recurring review theme is…”
- “4-Social is designed to address…”

Never fabricate a 4-Social testimonial from a Blotato, Crayo or Stan review. If competitor feedback is shown, label it explicitly as third-party competitor-user feedback and preserve attribution/source in project notes.

## STEP 5 — Build a Remotion marketing project

If no Remotion project exists, create one under a clearly named directory such as `marketing/remotion`.

Use current Remotion best practices:
- React/TypeScript
- frame-driven animations with `useCurrentFrame()` and `interpolate()`
- do not rely on CSS transitions/animations for rendered motion
- use `Sequence` or equivalent multi-scene structure
- put local assets in `public/`
- use `staticFile()`
- use Remotion media components for audio/video
- create editable composition props where practical
- start Studio with `npx remotion studio --no-open`; if file watcher limits occur, use `--webpack-poll 1000`

Create THREE finished master compositions, each exactly approximately 2 minutes 30 seconds. At 30fps target 4500 frames each.

Render final MP4 masters after they pass preview QA.

Also create derivative compositions/exports appropriate for:
- 60-second cut
- 30-second cut
- 15-second cut
- 16:9 landscape
- 9:16 vertical
- 1:1 square where practical

### VIDEO 1 — “One Command Center Instead of Twelve Tabs”

Goal: clearly explain the 4-Social problem/solution for creators and small businesses.

Story arc:
1. Hook: creator/business owner overwhelmed by separate apps, inboxes, posting tools, editor, store, analytics and ads.
2. Show 4-Social as one command center.
3. Demonstrate Create Once → Publish Everywhere.
4. Show AI adaptation per platform.
5. Show unified inbox concept.
6. Show real-time analytics and ROI concept.
7. Introduce Implement AI agents.
8. End with AI Boardroom meeting and concise CTA.

Visual language:
- premium product film
- authentic UI-first scenes
- no fake social metrics
- kinetic but readable typography
- real interface captures when available; otherwise label concept renders clearly

### VIDEO 2 — “Meet the AI Marketing Department”

Goal: make the AI-workforce differentiation unforgettable.

Story:
1. User calls a meeting by voice.
2. CampaignPilot, SocialMind, CreatorForge, TrendHunter, Insight Engine and ComplianceCore arrive in a photoreal boardroom concept.
3. TrendHunter reports an early micro-trend with evidence.
4. CreatorForge proposes content.
5. ComplianceCore flags/clears claims.
6. CampaignPilot presents audience/budget plan.
7. Insight Engine challenges spend and forecasts ROI range.
8. Presenter Mode: marketing agent stands, advances slides, points to graphs and projected creative.
9. Proctor Mode captures decisions/tasks.
10. CTA: “Stop asking AI questions. Put AI to work.” or another truthful approved line.

Important: if the photoreal avatar/boardroom functionality is not LIVE, make the visual explicitly a “Product vision / Beta preview” rather than implying the live app currently does it.

### VIDEO 3 — “Creation to Distribution to Revenue”

Goal: persuade users familiar with Blotato, Crayo and Stan without misleading comparisons.

Opening idea:
“Publishing is only one part. Creating clips is only one part. Selling is only one part. What happens when one operating system connects all three?”

Use a fair category comparison, not an attack ad.

Show:
- Blotato category strength: publishing/automation/API
- Crayo category strength: rapid short-form content tools
- Stan category strength: storefront/creator monetization
- 4-Social intended advantage: connect content creation + publishing + inbox + paid media + commerce + ROI + proactive AI workforce

Any comparison matrix must include LIVE/BETA/PLANNED status for 4-Social features.

Use competitor customer pain themes only as generalized research insights. Examples:
- users value time-saving cross-platform publishing
- creators want editing control and reliability
- users dislike wasted credits on failed renders
- creators want deeper analytics and stronger branding
- users want better support/transparency

Then show exactly how 4-Social is designed to address those needs.

## STEP 6 — Marketing collateral

Create a reusable collateral package in the repository.

Required assets/content:
- 10 social promo concepts
- 6 comparison-card concepts
- 3 carousel concepts with 5–8 cards each
- 10 short-form video hooks
- 10 headline/subheadline/CTA combinations
- 5 product-feature spotlights
- 3 “Meet Your AI Team” campaign concepts
- 3 “Create Once → Publish Everywhere” campaigns
- 3 “From Content to Revenue” campaigns
- website comparison-section copy
- landing-page hero alternatives

Design outputs should cover:
- 1080x1080
- 1080x1350
- 1080x1920
- 1920x1080

Where raster/design generation is outside Remotion, create structured creative briefs/prompts and reusable templates rather than fake finished screenshots.

## STEP 7 — Truthful comparison matrix

Create a sourced internal comparison file with rows such as:
- multi-platform publish
- scheduling
- per-platform AI adaptation
- API/MCP
- comments/DMs
- content generation
- short-form clipping
- image/thumbnails
- storefront/commerce
- courses/downloads/bookings
- email marketing
- paid-ad analytics
- ROAS/budget optimization
- proactive AI agents
- AI boardroom
- photoreal avatar meetings
- LLM agnostic architecture
- unified action audit log
- brand customization

For every competitor cell, use official source or clearly labeled public-review evidence. Use “Not verified” when uncertain.
For every 4-Social cell, use LIVE/BETA/PLANNED/BLOCKED.

## STEP 8 — QA the videos and collateral

Before calling them complete:
- preview every Remotion composition
- verify no text overflows
- verify captions are readable on phone-sized previews
- verify no media stretches incorrectly
- verify audio levels are sensible
- verify no missing assets
- verify spelling: **4-Social**, **Implement AI**
- verify competitor names: **Blotato**, **Crayo**, **Stan**
- verify claims against sources and current product status
- verify no fake testimonials
- verify any quote is short, attributed and stored with its source
- verify renders complete successfully

## STEP 9 — Deliverables

Commit:
- Remotion source
- reusable components
- assets that are licensed/original
- scripts/copy
- comparison matrix
- sources/research notes
- render instructions
- QA report
- final master videos and derivatives when file-size/repository policy permits; otherwise store clear render paths and artifact instructions

Create a final `HANDOFF_REPORT.md` stating:
- what was actually built
- what tests passed
- what remains blocked
- what is LIVE/BETA/PLANNED
- exact render commands
- exact paths to video and collateral outputs
- exact Git commit SHA

Do not report completion until you have actually tested the relevant output.

---

End of master prompt.
