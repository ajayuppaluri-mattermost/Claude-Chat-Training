# Day 2 Exercises

These exercises build on Day 1 by focusing on prompt quality. You'll see firsthand how specificity, context, and iteration transform Claude's output.

---

## Exercise 1: The LinkedIn Post Ladder (8 min)

**Scenario:** You're announcing that your company just surpassed 1,000 customers. You'll write the same announcement at three specificity levels and compare the results.

**Steps:**

1. Open a new chat in Claude.ai
2. Start with a Level 1 (vague) prompt:

```
Write a LinkedIn post about reaching 1,000 customers.
```

3. Read the output. It will be generic. Now send a Level 2 (directed) prompt:

```
Write a LinkedIn post announcing that TaskFlow Pro, a B2B project management
tool, just reached 1,000 paying customers. The post should celebrate the
milestone and encourage engagement.
```

4. Read the output. Better, but still fairly template-like. Now send a Level 3 (fully specified) prompt:

```
Write a LinkedIn post for our company page announcing that TaskFlow Pro
just reached 1,000 paying customers.

Context:
- We launched 18 months ago
- Our customers are mid-size tech and professional services companies
- The 1,000th customer is a 500-person consulting firm
- Our average customer reports saving 8 hours per week on project reporting

Requirements:
- Tone: proud but humble, grateful to customers
- Length: 150-200 words
- Start with a specific, attention-grabbing first line (not "We're excited to announce")
- Include the 8 hours/week stat
- End with a genuine question to drive comments
- Maximum 3 hashtags at the very end
- Do not use: "thrilled," "game-changer," "journey"
```

5. Compare all three outputs. The Level 3 version should be dramatically better.

**What good looks like:** A noticeable quality jump at each level. The Level 3 post should feel like it was written by someone who actually works at the company, not a generic AI template.

---

## Exercise 2: Brand Voice Loader (8 min)

**Scenario:** You need Claude to write in your company's voice — but first, Claude needs to understand what that voice sounds like.

**Steps:**

1. Open a new chat in Claude.ai
2. Paste in 2-3 paragraphs of your company's existing marketing copy. If you don't have any handy, use this sample:

```
Here are three paragraphs from our website and recent marketing materials:

"Most project management tools give you more dashboards, more charts, more
complexity. TaskFlow Pro gives you fewer meetings. Our AI watches your team's
workload in real time and flags problems before they become fire drills. No
setup wizards. No 40-page implementation guides. Just connect your tools and
let TaskFlow do the thinking."

"We built TaskFlow for teams that are tired of managing their project
management tool. Our customers are operations leaders, marketing managers,
and engineering directors who'd rather spend their brainpower on actual work
than updating status reports nobody reads."

"When DataCorp switched to TaskFlow Pro, their Monday status meetings went
from 60 minutes to 15. Their project lead said, 'We stopped talking about
work and started doing it.' That's the goal."
```

3. Ask Claude to analyze the voice:

```
Analyze the brand voice in these paragraphs. Give me 5 specific
characteristics of this writing style, with an example phrase for each.
```

4. Read Claude's analysis. Then ask it to write something new in that voice:

```
Using this exact brand voice, write a short product description (100 words)
for our new feature: AI-powered weekly report generation that automatically
summarizes project progress and emails it to stakeholders every Monday.
```

5. Compare the new copy against the originals. It should sound like the same company wrote it.

**What good looks like:** Claude accurately identifies the voice traits (direct, conversational, anti-complexity, results-focused, uses humor) and the new copy matches that style — not generic marketing language.

---

## Exercise 3: Refine Until Ready (7 min)

**Scenario:** You need a cold outreach email and you'll refine it through three rounds of feedback to see how iteration works.

**Steps:**

1. Open a new chat in Claude.ai
2. Start with a solid initial prompt:

```
Write a cold outreach email from a sales rep at TaskFlow Pro to a
VP of Operations at a 300-person logistics company.

Goal: Get a 15-minute introductory call.
Our value prop: We reduce project delays by 30% through AI-powered
resource allocation.
Keep it under 120 words. Tone: professional but human.
```

3. Read the first draft. Now give specific feedback — Round 1:

```
Too long. Cut it to under 80 words. Remove the second paragraph entirely
and strengthen the opening line — make it about their problem, not about us.
```

4. Read the revision. Round 2:

```
Better. The CTA is too aggressive — change "book a call" to something
softer like asking if it's worth a quick conversation. Also, the subject
line is generic — make it specific to logistics operations.
```

5. Read the revision. Round 3:

```
Almost there. Add one specific stat or proof point in the middle
(use the 30% reduction in project delays). Keep the total length under
80 words.
```

6. The final version should be significantly better than the first draft.

**What good looks like:** Each round produces a visible improvement. The final email should be concise, specific, open with the prospect's problem, include a proof point, and end with a low-pressure CTA. Three rounds of targeted feedback should get you to a send-ready email.

---

## Recap

You practiced three skills that separate mediocre Claude users from effective ones:
- **Specificity** (Exercise 1) — More detail = dramatically better output
- **Context loading** (Exercise 2) — Paste in real materials and Claude matches your style
- **Iteration** (Exercise 3) — Give specific feedback, not vague reactions

Next, check out today's reusable workflow: [Prompt-Refine-Polish →](workflow-prompt-refiner.md)

---

[← Lesson](lesson.md) | [Day 2 Overview](README.md) | [Workflow →](workflow-prompt-refiner.md)
