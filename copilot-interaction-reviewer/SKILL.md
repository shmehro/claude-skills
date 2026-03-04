---
name: copilot-interaction-reviewer
description: Reviews any product artifact — a PRD, user flow, UX copy, design description, wireframe annotation, interaction spec, error state, or feature idea — through a senior UX designer's lens, specifically calibrated for Copilot and AI-powered experiences in Microsoft 365. Trigger this skill whenever someone shares work involving an AI or Copilot interaction and wants critique, a design review, a pre-ship check, a craft review, an accessibility audit, or just wants to know if their design is good. Also trigger for questions like "does this feel right?", "what am I missing?", "is this on-brand?", "how would a designer review this?", or "how do I make this better?" If the artifact touches Copilot entry points, response surfaces, agent flows, prompt UI, AI-generated content, AI error states, loading/streaming states, or any AI-driven feature in Word, Excel, PowerPoint, Outlook, Teams, or any M365 surface — use this skill immediately.
---

# Copilot Interaction Quality Reviewer

A senior UX design review skill for Copilot and AI-powered product work in Microsoft 365.
Built for designers first — but useful for PMs and engineers who want to pressure-test their work against a high design bar before sharing it with the studio.

---

## How to run a review

### Step 1 — Identify the artifact and its maturity

| Artifact type | Examples |
|---|---|
| Concept / idea | "I'm thinking about adding Copilot to the document footer" |
| User flow | A sequence of steps describing what a user does |
| Interaction spec | States, transitions, triggers, and outputs |
| UX copy | Prompts, responses, error messages, button labels |
| Design description | An annotated walkthrough of a screen or component |
| PRD section | Feature requirement with user stories and acceptance criteria |

Maturity levels:
- **Exploratory** — rough idea, no screens. Focus on biggest structural gaps only.
- **In-progress** — flows or annotated wireframes. Full review across all dimensions.
- **Near-final** — ready for engineering. Exhaustive review, every dimension at maximum depth.

If it's unclear, ask only: *"Is this a rough idea or are you closer to final?"*

### Step 2 — Run the review

Evaluate across all 10 dimensions. For each:
- Assign a rating: **Strong / Needs Work / Missing**
- Note what's working (specific, not generic praise)
- Note what's missing or at risk (be direct)
- Give 1–3 concrete, actionable recommendations

### Step 3 — Output using the format at the bottom of this file

---

## The 10 Review Dimensions

---

### 1. Interaction Model & Mental Model Fit
*Does the design match how users already think about this task?*

The most common failure in Copilot design is building an interaction model that makes sense to the product team but breaks the user's existing mental model. A user in Word thinks about *their document*. A feature that pulls them into a chat-first paradigm creates friction even when it works perfectly.

**Check for:**
- Does the interaction build on what users already do in this surface (editing, reviewing, selecting), or does it ask them to switch contexts unnecessarily?
- Is the entry point contextually triggered (appears when text is selected, when a section is empty) or always-on in a way that competes for attention?
- Is the interaction model consistent with what Copilot does elsewhere in M365? Users bring expectations across apps.
- Does the user need to learn a new paradigm, or does this extend something familiar?
- Is the interaction modal or non-modal? Modal is sometimes right but must be justified.

**Red flags:**
- Copilot displacing the user's primary task surface
- Requiring the user to "enter" a Copilot mode to do something they'd expect inline
- Interaction model that only makes sense if you've seen the team's internal framing
- Feature works differently here than a comparable feature in an adjacent M365 app

---

### 2. Entry Points & Discoverability
*Can users find and invoke the feature at the right moment?*

Even great Copilot features go unused when the entry point is wrong. This is one of the highest-leverage design decisions and one of the most under-specified in early artifacts.

**Check for:**
- Is the entry point contextual (appears when relevant) or ambient (always present)?
- Is there a clear primary entry point? Are secondary entry points consistent?
- Does the entry point appear at the right moment — not too early (before the user needs it), not too late (after they've already done it manually)?
- Is the affordance recognizable — does it look invokable, or does it blend into surrounding UI?
- Is the Copilot icon used correctly per the Fluent AI icon spec?
- Is there a discoverability path for users who don't naturally encounter the entry point? (ribbon, command bar, right-click menu)
- What happens on first use? Is there a coachmark, tooltip, or empty state explaining what this does?

**Red flags:**
- Entry point buried 3+ levels deep with no shortcut
- Copilot icon used on a surface that doesn't involve AI generation
- Entry point appears only after the user has already done the work manually
- No first-run education — blank Copilot panel with no explanation
- Multiple competing entry points with no clear primary path

---

### 3. Response Surface & Information Design
*Is AI-generated content legible, scannable, and appropriately structured?*

Response surfaces in Copilot contexts are frequently under-designed — text dumped into a container with no hierarchy, no scannability, and no clear next action.

**Structure & hierarchy:**
- Is there a clear visual hierarchy? (Headline, body, actions — not a wall of prose)
- Is long-form content broken into scannable chunks? (Headers, bullets, short paragraphs)
- Are different types of content — instructions, generated text, citations, suggestions — visually differentiated?
- Is the response length proportional to the surface? A compact taskpane shouldn't return a 500-word essay without a truncation/expansion affordance.

**Density & readability:**
- Is line length within the readable range? (45–75 characters per line)
- Is there adequate spacing between response sections?
- Does dense output get paginated, collapsed, or truncated with a "show more" — or does it overflow the container?

**Actions & next steps:**
- After the AI responds, is it obvious what the user can do? (Accept, reject, copy, edit, regenerate, follow-up)
- Are actions visually anchored to the response they relate to — not floating ambiguously?
- Is there a clear primary action vs. secondary actions? (Not 5 equal-weight buttons)

**Provenance:**
- When content is sourced from documents, emails, or the web — is the source shown inline or accessible nearby?
- Is AI-generated content visually distinct from user-authored content in the document?

**Red flags:**
- Response drops into the document with no user confirmation
- All response text is the same visual weight — no hierarchy
- Actions shown as plain text links rather than recognizable controls
- No visual differentiation between AI output and the user's own content
- Response container has no max-height and can expand infinitely, destroying layout

---

### 4. Loading, Streaming & Transition States
*Does the interaction feel responsive, even during latency?*

AI features are slow compared to traditional UI. How you handle the time between invocation and response is one of the biggest differentiators between a polished Copilot feature and a frustrating one. This dimension is almost always under-specified.

**Invocation feedback:**
- Does the user get immediate feedback that their action was received? (Button state change, shimmer, spinner, skeleton) — ideally within 100ms
- Is the entry point disabled during generation so the user can't accidentally re-invoke?

**Streaming:**
- If the response streams, does the container grow gracefully or does it cause layout shift?
- Is there a stop/pause affordance once streaming begins?
- Does streaming start immediately, or is there a blank wait period before text appears?

**Long wait states:**
- If generation takes >5 seconds, is there explicit progress indication?
- Is there a timeout state? What does the user see at 15s? At 30s?
- Can the user cancel a long-running generation?

**Completion:**
- When generation completes, is there a clear visual signal?
- Does focus land somewhere useful — not back at the top of the screen?

**Red flags:**
- No loading state at all — UI freezes until response appears
- Streaming causes the entire page to reflow on every token
- No way to cancel a generation that is taking too long
- Focus lost after generation — user must manually find where the result appeared
- Same loading state for a 2-second response and a 20-second complex task

---

### 5. User Agency, Control & Reversibility
*Can the user always stay in charge?*

**Accept / reject / modify:**
- Can the user accept AI output as-is? Partially? Edit before accepting?
- Is rejection/dismissal always one clear action, never buried?
- If the output is wrong, can the user regenerate with the same prompt, or edit the prompt and retry?

**Undo:**
- If Copilot modifies the document, is the action undoable via Ctrl+Z?
- If Copilot takes a multi-step action (e.g., restructures an entire document), can it be rolled back as a single undo?
- Is there a "restore original" option for destructive rewrites?

**Interruption:**
- Can the user interrupt a generation mid-stream?
- Can the user navigate away from the Copilot panel without losing their document state?

**Consent for consequential actions:**
- Before any irreversible or hard-to-reverse action (send email, delete content, submit), does Copilot present a confirmation step?
- Is it clear what will change vs. what will stay the same before the user confirms?

**Red flags:**
- "Apply to document" with no preview of what will change
- Undo only goes back one token at a time, not to pre-generation state
- Copilot takes action without a confirm step
- Panel close loses all conversation context with no warning

---

### 6. UX Writing & Voice
*Is the language clear, human, and on-brand?*

UX writing in Copilot features is frequently either too robotic ("I am an AI assistant and I can help you with tasks") or too casual in ways that undermine trust. The right voice is: **clear, warm, direct, and empowering — not apologetic, not overpromising, not hedging every sentence.**

**Prompts & invitations:**
- Does the prompt text tell the user what Copilot can do — not just "Ask me anything"?
- Are suggested prompts specific enough to inspire real use? ("Summarize this document" beats "Ask a question")
- Is invocation copy verb-first? ("Draft", "Summarize", "Rewrite", "Find")

**Response copy:**
- Does Copilot briefly explain what it did before showing output — or does it just dump text?
- Are hedges used appropriately? ("This is a suggestion" = fine. A disclaimer paragraph = not fine.)
- Is first-person voice used sparingly? (Focus on what the user gets, not what Copilot does)

**Error messages:**
- Plain language, not error codes. ("Copilot couldn't reach your files. Check your connection and try again.")
- Every error tells the user what to do next.

**Empty states:**
- Specific to this feature — not a generic "Nothing here yet."
- Tells the user exactly how to get started.

**Button labels:**
- Verb-first, outcome-oriented. ("Insert into document" beats "Submit")
- Destructive actions clearly labeled. ("Discard draft" beats "Cancel")

**Red flags:**
- Placeholder copy left in spec
- Error messages with technical jargon or codes
- All buttons labeled "Submit", "OK", "Cancel"
- Copilot introduces itself as "I, your AI assistant" in every response
- Hedging in every single response that erodes user trust

**Microsoft voice principles:**
- **Clear over clever** — no puns or wordplay in functional UI
- **Warm but not cutesy** — friendly without being a chatbot character
- **Empowering** — frame outputs in terms of what the user can now do
- **Honest** — don't oversell; set accurate expectations upfront

---

### 7. Transparency, Trust & AI Disclosure
*Does the user understand what the AI is doing, and trust it appropriately?*

**Generation signals:**
- Is it clear when content is AI-generated vs. user-authored?
- Is the Copilot icon or "Generated by Copilot" label present where content enters the document?
- Is the AI's current mode communicated? (Summarizing vs. generating vs. reasoning vs. searching)

**Confidence & uncertainty:**
- When Copilot is uncertain, does it signal this usefully — without being paralyzed by hedging?
- When Copilot can't fully complete a task, does it explain what it did vs. what it couldn't?
- Are suggestions presented as suggestions, not instructions?

**Data & privacy:**
- Is it clear what data Copilot is using? (This document only? Your inbox? The web?)
- Are data boundaries surfaced appropriately — tenant data vs. public web?

**Red flags:**
- No visual signal that content is AI-generated after it's inserted into the document
- Copilot states things confidently that are clearly based on limited or partial context
- No disclosure of what data sources are in scope
- Privacy implications buried in a tooltip nobody will read

---

### 8. Accessibility & Inclusive Design
*Does this interaction work for every user?*

**Keyboard & focus:**
- Is the full Copilot interaction completable by keyboard alone?
- Is focus managed correctly when the panel opens? (Should move into the panel, not stay behind it)
- Is focus returned to a logical location after the panel closes?
- Is the focus order within the response surface logical? (Source → response text → actions)

**Screen reader:**
- Is AI-generated content announced in context? (Not just the text — the fact that it's AI-generated)
- Are loading states announced? ("Copilot is generating a response")
- Are live region updates announced without being interruptive?
- Are icon-only buttons (regenerate, thumbs up/down) given accessible text labels?

**Cognitive load:**
- Does the interaction present one decision at a time, or overwhelm with multiple choices?
- Is the reading level appropriate? (Aim for Grade 8 plain language unless context demands otherwise)
- For long responses, is there a summary or progressive disclosure affordance?

**Motion & animation:**
- Streaming text — is there a reduced-motion alternative?
- Panel transitions — do they respect `prefers-reduced-motion`?

**Color & contrast:**
- AI-specific elements (Copilot gradient, shimmer) — WCAG AA contrast minimum met?
- Is any information conveyed by color alone? (Must also use shape, label, or pattern)

**Red flags:**
- Focus trap in Copilot panel — can't Tab out without closing it
- Streaming text not announced to screen reader
- Icon-only feedback buttons with no accessible labels
- Reduced motion preference not respected
- Interaction that completely breaks without a mouse

---

### 9. Fluent Design System Alignment
*Does this use the right components, tokens, and patterns for Microsoft's design language?*

Fluent is not just a component library — it's a system of decisions that creates coherence across M365. Correct Fluent usage means the right component for the right job, not just any component that looks similar.

**Component usage:**
- Are standard Fluent components used where they exist? (Don't invent a custom input when Textarea exists)
- Is the Copilot-specific component set used correctly? (Copilot panel, response container, shimmer/skeleton, Copilot icon)
- Are button variants used correctly?
  - **Primary** — most important single action on the surface
  - **Secondary** — alternatives to primary
  - **Subtle** — low-priority or repeated actions
  - **Ghost / icon-only** — compact, space-constrained controls

**Spacing & layout:**
- Is the 4px grid followed? (All spacing: multiples of 4 — 4, 8, 12, 16, 20, 24, 32, 40, 48)
- Is there visual breathing room around response content?
- Are content density levels consistent with the host surface? (Compact in toolbars, comfortable in panels)

**Typography:**
- Is the Fluent type ramp used? (Segoe UI Variable; no invented font sizes outside the ramp)
- Is typographic hierarchy legible? Title → Subtitle → Body → Caption — not flat same-weight text
- Is line-height correct for response body text? (Fluent body: 20px / 1.43)

**Color & theming:**
- Are Fluent design tokens used instead of hardcoded hex values? (Enables light/dark/high-contrast support automatically)
- Is the Copilot gradient used only for Copilot-branded surfaces — not repurposed elsewhere?
- Does the design work in light mode, dark mode, and high-contrast mode?

**Elevation:**
- Is the Copilot panel at the correct elevation layer? (Above document canvas, below dialogs)
- Are shadows and borders using Fluent elevation tokens?

**Icons:**
- Are all icons sourced from the Fluent icon library?
- Is the Copilot sparkle used exclusively to mean "AI-generated" — never decoratively?

**Red flags:**
- Custom components that duplicate existing Fluent ones
- Hardcoded colors that break in dark mode or high-contrast
- Copilot sparkle used as decoration unrelated to AI
- Inconsistent spacing — mixed grids on the same surface
- Dialog (modal) used where a Panel (non-modal) is appropriate
- Typography outside the Fluent type ramp

---

### 10. Edge Cases & Spec Completeness
*What has the design not accounted for?*

Every artifact has blind spots. This dimension ensures the design holds under real-world conditions, not just the happy path.

**User states:**
- 🆕 **First-time user** — Never used Copilot here. What do they see? What teaches them?
- 🔁 **Returning user** — Has used it before. Any continuity? (Recent prompts, history)
- 💡 **Power user** — Uses this daily. Does the design add friction for them?
- 🚫 **Unlicensed user** — No Copilot license. Graceful or confusing?

**Content states:**
- 📭 **Empty state** — Nothing to work with. What does Copilot show?
- 📄 **Short content** — Only 1–2 sentences. Does the feature still make sense?
- 📚 **Very long content** — 100 pages. Does the feature handle or degrade gracefully?
- 🌐 **Non-English / RTL** — Japanese, Arabic, mixed-language. What happens?

**Error and edge states:**
- ⚡ **Timeout** — Generation takes >30 seconds. What does the user see?
- 🔌 **Offline / network failure** — Connection lost mid-generation. How does UI recover?
- ⚠️ **Content policy block** — Request blocked by content safety. Is the message clear and actionable?
- 🔒 **Permission gap** — Copilot needs access it doesn't have. How is this surfaced?
- 🧱 **Quota / rate limit** — User has hit their usage limit. What happens?

**Input edge cases:**
- Very short prompt (one word)
- Very long prompt (>500 characters)
- Ambiguous prompt ("make it better" — what does Copilot do?)
- Off-topic prompt ("book me a flight" in a Word Copilot context)
- Duplicate submission (user clicks generate twice quickly)

**Red flags:**
- Spec shows only the happy path — no error or empty states defined
- English only, no localization plan
- No definition of what unlicensed users see
- "We'll handle edge cases in a follow-up" — edge cases are part of the spec, not a follow-up

---

## Output Format

```
## Copilot Interaction Review

**Artifact:** [what was shared]
**Maturity:** [Exploratory / In-progress / Near-final]
**Overall signal:** [Ready to build / Needs revision before build / Concept only — significant gaps]

---

### 1. Interaction Model & Mental Model Fit — [Strong / Needs Work / Missing]
**What's working:** ...
**What's missing:** ...
**Recommendations:**
- ...
- ...

### 2. Entry Points & Discoverability — [Strong / Needs Work / Missing]
...

[repeat for all 10 dimensions]

---

## Top 3 priorities before next milestone
1. [Most critical — one sentence, specific and actionable]
2. [Second — one sentence, specific and actionable]
3. [Third — one sentence, specific and actionable]

## What's already strong
[2–3 sentences. Specific praise for what the design gets right. No generic compliments.]

## Open questions
[2–3 questions the review surfaced but can't answer from the artifact alone]
```

---

## Calibration guidance

**Be a senior designer, not a linter.** Don't just flag violations — explain the user experience consequence if the issue is left unfixed. "No error state defined" is a linter. "If generation fails at 20 seconds with no feedback, users will assume the product is broken and refresh the page, losing their work" is a senior designer.

**Prioritize ruthlessly.** A missing confirmation before an irreversible action is P0. Missing Fluent spacing tokens are P2. Make the distinction clear in the Top 3 priorities.

**Be specific.** "Add an error state" is not a recommendation. "Define a timeout state at 15s with a 'Copilot is taking longer than usual — keep waiting or cancel' message and a visible cancel button" is a recommendation.

**Match depth to maturity.** Early concepts don't need exhaustive component-level critique. Near-final specs need everything.

**Earn the right to be critical.** Always name what's working — genuinely and specifically. Feedback without acknowledgment of good work is demoralizing and less likely to land.

**Ask questions you can't answer from the artifact.** The best reviews surface what's unknown, not just what's wrong.

---

## Quick reference: Fluent AI component checklist

| Component | When to use |
|---|---|
| Copilot icon (sparkle) | Any entry point that invokes AI generation |
| Shimmer / skeleton | Loading state while AI generates |
| Copilot response container | Wrapping AI-generated output before user accepts |
| Inline AI badge | Marking content already inserted as AI-generated |
| Prompt input | Multi-line text input for Copilot prompts |
| Suggested prompts | Chips or list items showing example prompts |
| Thumbs up / down | Feedback on any AI-generated response |
| Stop generation button | Present whenever streaming is active |

---

## Microsoft Responsible AI — quick reference

| Principle | Design question |
|---|---|
| **Fairness** | Could outputs treat different users inequitably? |
| **Reliability & Safety** | What happens when this fails? Is failure safe? |
| **Privacy & Security** | What data is used? Is it clear to the user? |
| **Inclusiveness** | Does this work for users with disabilities or low digital literacy? |
| **Transparency** | Does the user understand what AI is doing and why? |
| **Accountability** | Is there a human in the loop for high-stakes decisions? |

Full guidance: [Microsoft Responsible AI principles](https://www.microsoft.com/en-us/ai/responsible-ai)

---

## Version history
- v1.0.0 (2026-03-03): Initial release — 8 dimensions
- v2.0.0 (2026-03-03): Expanded to 10 dimensions; deepened UX specificity across response surfaces, loading/streaming states, UX writing, Fluent alignment, and edge case coverage
