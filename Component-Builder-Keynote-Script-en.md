# Component Builder Minimal Deck — Speaker Script (English)

- **Slide Deck**: [Component-Builder-Keynote-en.html](Component-Builder-Keynote-en.html)
- **Audio Narration**: [Component-Builder-Keynote-en-Gemini.mp3](Component-Builder-Keynote-en-Gemini.mp3) (Gemini TTS · `Aoede` · Duration `04:06.798`)

---

## [00:00.000] 1. Meet the Component Builder Agent

> **Stage Cue**: Show Slide 1. Point to the Component Builder AI AGENT badge and the 5-stage overview row.

Hi everyone. Let's take a quick look at Component Builder. First and foremost, Component Builder is not just a code snippet generator—it is an autonomous AI Agent for Android UI engineering. You give it a single exact Figma node link, and this Agent orchestrates specialized Skills end to end: writing Jetpack Compose code, running tests, fixing pixel drift, attaching visual proof, and triggering an independent review to deliver a review-ready Pull Request.

## [00:28.621] 2. The 7-Step Autonomous Pipeline

> **Stage Cue**: Advance to Slide 2. Click steps 01 Design, 04 Diff, and 06 Upload to highlight the SKILL badges.

On Slide 2, you can see the seven-step closed loop. Step one invokes the figma-tools Skill to pin the exact design node and create a clean working branch. Step two builds the Compose component and KDoc. Step three runs device and screenshot tests. Step four invokes the visual-compare Skill to diff every state pixel by pixel. If anything drifts, step five heals the code automatically. Step six uses the built-in browser Skill to attach screenshots on GitHub Enterprise, and step seven dispatches a second read-only Agent running the pr-review Skill.

## [01:04.002] 3. Exact Specs, Safe Branches, and Dual Tests

> **Stage Cue**: Advance to Slide 3. Highlight cards 01, 02, and 03.

Slide 3 shows the engineering discipline behind implementation and testing. First, exact specs and safe branches: it pins the exact Figma node ID and version, works on a dedicated story branch, never auto-stashes unrelated local files, and captures before-change renders when updating existing components. Second, production Compose code: it preserves public API compatibility, updates Samples and Previews, and places a clean Figma URL right in KDoc. Third, dual verification: it pairs real-component Android instrumentation tests with permanent Paparazzi host captures on JDK 17 and SDK 35.

## [01:45.383] 4. Three-Column Pixel Diff (visual-compare Skill)

> **Stage Cue**: Advance to Slide 4. Toggle between 'Before: 8px Drift' and 'After: 0px Aligned'.

Slide 4 shows how visual validation works. Using the visual-compare Skill, the Agent builds a three-column comparison image for each state: the Figma reference on the left, the current Paparazzi render in the middle, and an amplified difference panel on the right. Even an eight-pixel horizontal shift in a single state stands out immediately, and toggling to the post-fix view confirms zero remaining drift.

## [02:10.964] 5. Self-Healing Loop and 2-Pass Circuit Breaker

> **Stage Cue**: Advance to Slide 5. Contrast the green self-healing loop on the left with the amber 2-Pass Stop card on the right.

When a visual discrepancy appears, the Agent doesn't punt it to human reviewers. On Slide 5, it enters a self-healing loop: tracing the root cause in code, applying established design tokens, recapturing screenshots, and rechecking sibling states to prevent regressions. Just as important is the two-pass circuit breaker on the right: after two consecutive passes without verified improvement, the Agent stops immediately, keeps all evidence, leaves the PR in Draft, and asks a specific question—never looping forever and never gaming thresholds.

## [02:45.385] 6. GitHub Enterprise Browser Upload and Pixel Verification

> **Stage Cue**: Advance to Slide 6. Point to the SKILL GHES Browser UI badge and the 3 verification cards.

Slide 6 tackles a practical enterprise constraint: GitHub Enterprise Server does not support attaching PR images from the command line. So after opening a template-compliant PR, the Agent uses its built-in browser Skill to embed each three-panel PNG directly into the PR description. Then it reopens the saved PR to verify that every image loads for reviewers, preserves its aspect ratio, and matches the exact decoded pixels.

## [03:14.686] 7. Independent Two-Agent Review

> **Stage Cue**: Advance to Slide 7. Show the Builder Agent, Pull Request, and Reviewer Subagent diagram.

Slide 7 enforces separation of powers: the builder writes, and a second Agent audits. Once the PR and visual proof are published, an isolated Reviewer Subagent runs the pr-review Skill against that exact commit SHA. Its code access is strictly read-only—it validates and posts objective review comments on the PR, and never approves its own work.

## [03:39.627] 8. Clear Human-Agent Governance

> **Stage Cue**: Advance to Slide 8. Conclude with the Agent legwork column vs. the three Human keys.

Finally, Slide 8 sums up governance. The Agent handles the heavy lifting—branching, Compose code, dual testing, pixel alignment, browser uploads, and first-pass review. Meanwhile, humans hold the three final keys: clarifying ambiguous specs, authorizing golden baseline commits, and giving final design and merge sign-off. That is Component Builder: autonomous speed backed by pixel-level engineering trust. Thank you!
