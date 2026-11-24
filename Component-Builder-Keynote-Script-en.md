# Component Builder Minimal Deck — Speaker Script (English)

- **Slide Deck**: [Component-Builder-Keynote-en.html](Component-Builder-Keynote-en.html)
- **Audio Narration**: [Component-Builder-Keynote-en-Gemini.mp3](Component-Builder-Keynote-en-Gemini.mp3) (Gemini TTS · `Aoede` · Duration `02:59.718`)

---

## [00:00.000] 1. Opening: Component Builder Agent

> **Stage Cue**: Show Slide 1. Point to the Component Builder AI AGENT badge and the 5-stage overview row.

Hi everyone, today I will introduce the Component Builder Agent. Component Builder is an autonomous AI agent for Android UI engineering. You give it a single exact Figma link, and this agent orchestrates specialized skills end to end: it reads the Figma node, generates the Jetpack Compose component, runs UI tests, fixes visual drift, and delivers a review-ready PR.

## [00:23.501] 2. 7-Step Closed Loop

> **Stage Cue**: Advance to Slide 2. Click steps 01 Design, 04 Diff, and 06 Upload to highlight the SKILL badges.

On Slide 2, you can see the seven-step closed loop. Step 1 invokes the figma-tools skill to pin the exact design node and states. Step 2, based on that Figma node, builds the Compose component, previews, and KDoc. Step 3 runs Android UI tests on a device to verify behavior, plus screenshot tests. Step 4 invokes the visual-compare skill to compare every state pixel by pixel. Step 5: if anything drifts, it heals the code automatically. Step 6 uses the built-in browser skill to attach screenshots to the GitHub PR. Step 7 dispatches an independent agent to review the PR.

## [01:03.882] 3. Implementation & Testing

> **Stage Cue**: Advance to Slide 3. Highlight cards 01, 02, and 03.

Slide 3 shows the engineering discipline behind implementation and testing. First, it pins the exact node ID and creates a safe story branch without touching your local files. Second, it keeps public APIs compatible and puts the Figma link right in KDoc. Third, it verifies both real device behavior and Paparazzi host screenshots.

## [01:25.783] 4. Visual Comparison

> **Stage Cue**: Advance to Slide 4. Toggle between 'Before: 8px Drift' and 'After: 0px Aligned'.

Slide 4 shows how visual validation works. Using the visual-compare skill, the agent builds a three-column comparison image for each state. As you can see: the Figma design is on the left, the current render is in the middle, and an amplified difference panel is on the right. Even an 8-pixel shift is caught right away—and after the fix, the outlines match completely.

## [01:49.164] 5. Self-Healing Loop

> **Stage Cue**: Advance to Slide 5. Contrast the green self-healing loop on the left with the amber 2-Pass Stop card on the right.

Slide 5 is the self-healing loop. Instead of leaving visual bugs to human reviewers, the agent finds the root cause in code, fixes it with design tokens, and checks all states again. And if two passes show no real improvement, it stops immediately, leaves the PR in Draft, and asks for human input.

## [02:08.225] 6. Browser Upload

> **Stage Cue**: Advance to Slide 6. Point to the SKILL GHES Browser UI badge and the 3 verification cards.

Slide 6 solves a GitHub Enterprise limitation. Since Enterprise GitHub cannot upload PR images from the command line, the agent uses its built-in browser skill to attach screenshots directly into the PR body, and reopens the page to verify every image.

## [02:24.366] 7. Independent Review

> **Stage Cue**: Advance to Slide 7. Show the Builder Agent, Pull Request, and Reviewer Subagent diagram.

Slide 7 shows our two-agent review model. The builder agent writes the code, while a second read-only agent runs the pr-review skill on the exact same commit—posting objective comments, and never approving its own PR.

## [02:39.227] 8. Closing

> **Stage Cue**: Advance to Slide 8. Conclude with the Agent legwork column vs. the three Human keys.

Finally, Slide 8 shows the boundary between the agent and humans. The agent does all the heavy engineering work, while humans keep final control over design questions, screenshot baselines, and merging the PR. In short: you just give a Figma link to this agent, and it delivers a pixel-verified, review-ready PR. Thank you!
