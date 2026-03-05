# Workflow: Prompt-Refine-Polish

A three-step process for consistently getting publish-ready output from Claude. Use this every time you need something more polished than a quick first draft.

## Step 1: Draft Your Prompt

Use the Role + Task + Context + Format structure from Day 1:

```
[ROLE — who should Claude be?]

[TASK — what do you need?]

Context:
- [RELEVANT DETAIL 1]
- [RELEVANT DETAIL 2]
- [RELEVANT DETAIL 3]

Format:
- Tone: [TONE]
- Length: [LENGTH]
- Must include: [REQUIREMENTS]
- Must avoid: [EXCLUSIONS]
```

## Step 2: Pre-Send Checklist

Before hitting Enter, scan your prompt for these five elements. Every one you include improves the output.

- [ ] **Tone** — Did I specify how it should sound?
- [ ] **Length** — Did I set a word count or size constraint?
- [ ] **Audience** — Did I name who will read this?
- [ ] **Avoidances** — Did I say what NOT to do?
- [ ] **Example or reference** — Did I provide a sample, style guide, or existing content to match?

If you've checked 3 or more, send it. If fewer than 3, add more detail — it's faster to specify up front than to iterate later.

## Step 3: Refine with Targeted Phrases

After Claude's first response, use these phrases to dial in the output:

| When you want to... | Say this |
|---|---|
| Adjust length | "Make it [30% shorter / under X words / longer with more detail]." |
| Fix tone | "Make the tone more [casual / formal / urgent / empathetic / confident]." |
| Fix a section | "Keep everything, but rewrite the [first paragraph / CTA / headline] to be more [specific quality]." |
| Add something | "Add [a specific stat / a customer quote / a deadline] to the [section]." |
| Remove something | "Remove the [section / sentence about X]. It's not relevant." |
| Get alternatives | "Give me 3 alternative versions of the [headline / subject line / CTA]." |
| Shift audience | "Rewrite this for a [CFO / technical / executive] audience instead." |
| Final polish | "Review this for grammar, clarity, and flow. Fix any issues and list what you changed." |

## Quick Tip

Two rounds of refinement is typical. If you're on round 4+, it's usually faster to start a new chat with a better initial prompt — incorporating what you learned from the failed attempts.

---

[← Exercises](exercises.md) | [Day 2 Overview](README.md)
