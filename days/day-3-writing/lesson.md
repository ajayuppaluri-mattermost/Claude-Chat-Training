# Day 3 Lesson: Writing & Communications Workflows

You now know how to write good prompts and refine Claude's output. Today you'll apply those skills to the writing tasks that consume most of your day — emails, blog posts, content repurposing, and editing. The goal is to make Claude your daily writing partner.

## Section 1 — The Draft-Critique-Revise Loop

This three-step technique consistently outperforms asking Claude for a single draft. It works because Claude is surprisingly good at critiquing its own work.

**Step 1: Generate a draft** with full context (using what you learned in Days 1-2).

**Step 2: Ask Claude to critique its own draft:**
```
Now review this draft as a senior marketing editor. Identify specific
weaknesses in:
- Clarity (any confusing or vague phrases?)
- Persuasion (is the value proposition compelling?)
- Flow (does it read smoothly from start to finish?)
- CTA (is the call-to-action clear and motivating?)

Be specific — point to exact sentences that need improvement.
```

**Step 3: Ask Claude to revise based on its critique:**
```
Now rewrite the draft, fixing every issue you identified. Keep what's
working and improve what isn't.
```

The result is typically 50-70% better than the first draft. This loop works for emails, blog posts, landing pages, case studies — any content where quality matters.

## Section 2 — Email Workflows

### Cold Outreach
```
Write a cold outreach email.

Sender: [YOUR NAME], [YOUR TITLE] at [COMPANY]
Recipient: [THEIR TITLE] at a [COMPANY SIZE] [INDUSTRY] company
Goal: [DESIRED ACTION — e.g., book a 15-min call]
Our value prop: [ONE SENTENCE ABOUT WHAT YOU DO]
Proof point: [STAT, CASE STUDY REFERENCE, OR CUSTOMER RESULT]

Tone: [professional / casual / consultative]
Length: under [WORD COUNT] words
Open with their problem, not our product.
End with a low-commitment question, not a hard CTA.
```

### Follow-Up Sequences
```
I sent this email [DAYS] days ago and got no response:
[PASTE ORIGINAL EMAIL]

Write a follow-up that:
- References the original email without just repeating it
- Adds a new angle or piece of value (not "just checking in")
- Is shorter than the original
- Keeps the same tone
```

### Internal Communications
```
Write an internal announcement about [TOPIC] for [AUDIENCE — all-hands, sales team, leadership].

Key facts:
- [FACT 1]
- [FACT 2]
- [FACT 3]

What people need to do: [ACTION ITEMS]
Deadline: [DATE]
Tone: [TONE]
Length: under [WORD COUNT] words
```

## Section 3 — Long-Form Content

### Blog Posts: Outline First, Then Section by Section

Don't ask Claude to write a full blog post in one prompt. Break it into steps:

1. **Get headline options:**
```
Give me 5 headline options for a blog post about [TOPIC].
Target audience: [WHO]. Goal: [drive traffic / educate / convert].
Make them specific and benefit-focused.
```

2. **Get an outline:**
```
I'm going with headline #[N]: "[HEADLINE]"
Create a blog post outline with:
- An intro hook (2-3 sentences, not a generic opener)
- 4-5 main sections with descriptive subheadings
- Key points to cover in each section
- A conclusion with a clear CTA
Target length: [WORD COUNT] words total
```

3. **Draft section by section:**
```
Write the [SECTION NAME] section. Target [WORD COUNT] words.
Use the outline above but add specific examples and concrete details.
```

This approach gives you more control and produces more coherent long-form content.

### Case Studies
```
Write a case study using this structure:

Situation: [WHO IS THE CUSTOMER AND WHAT'S THEIR CONTEXT]
Challenge: [WHAT PROBLEM WERE THEY FACING]
Solution: [WHAT DID THEY DO — how did they use our product]
Result: [QUANTIFIED OUTCOMES]

Include:
- A compelling headline that leads with the result
- A 2-sentence executive summary at the top
- A pull quote from the customer (you can draft a realistic one)
- Specific numbers wherever possible

Length: [WORD COUNT] words
Tone: professional but story-driven
```

### Landing Page Copy
```
Write landing page copy for [PRODUCT/FEATURE].

Target audience: [WHO]
Primary pain point: [WHAT PROBLEM DOES THIS SOLVE]
Key differentiator: [WHY US OVER ALTERNATIVES]

Write:
1. Hero headline (under 10 words) + subheadline (under 25 words)
2. Three benefit blocks (icon-style: short headline + 2 sentences each)
3. One social proof section (stat + customer quote)
4. CTA button text + supporting line
```

## Section 4 — Editing and Polishing

Claude is excellent at editing existing text. Use these patterns:

**Improve clarity:**
```
Edit this for clarity. Simplify complex sentences, remove jargon,
and make every sentence easy to understand on first read:
[PASTE TEXT]
```

**Cut length:**
```
Cut this to under [WORD COUNT] words. Preserve the key message
and CTA. Remove anything that doesn't directly support the main point:
[PASTE TEXT]
```

**Shift tone:**
```
Rewrite this in a [TARGET TONE] tone. Keep the same information
and structure, just change how it sounds:
[PASTE TEXT]
```

**Generate alternatives:**
```
Give me 5 alternative versions of this headline. Each should take
a different angle:
[PASTE HEADLINE]
```

---

[← Day 3 Overview](README.md) | [Next: Exercises →](exercises.md)
