# Day 2 Lesson: Getting Exactly What You Need

Yesterday you learned the basics — how to navigate Claude and write a first prompt. Today is about going from "okay output" to "exactly what I wanted." The difference comes down to three skills: specificity, context loading, and iteration.

## Section 1 — The Specificity Ladder

Most people write prompts at Level 1. Your goal is to reach Level 3 consistently.

**Level 1 — Vague:**
```
Write me a follow-up email.
```
Result: Generic, could be for anyone, about anything. You'll spend more time editing than you saved.

**Level 2 — Directed:**
```
Write a follow-up email to a prospect who attended our webinar
on AI-powered analytics but didn't book a demo.
```
Result: Better — Claude knows the scenario. But it still guesses at tone, length, and approach.

**Level 3 — Fully Specified:**
```
Write a follow-up email to a marketing director at a mid-size
e-commerce company. She attended our webinar "5 Ways AI Saves
Marketing Teams 10 Hours Per Week" three days ago but didn't
book a demo.

Tone: helpful and consultative, not pushy
Length: under 150 words
Include: one specific insight from the webinar topic, a soft CTA
to book a 15-minute call (not a full demo)
Avoid: "just following up," "I hope this email finds you well,"
multiple CTAs, aggressive urgency

Reference: our best-performing outreach emails use short
paragraphs, lead with value, and end with a low-commitment question.
```
Result: Claude produces something close to send-ready on the first attempt.

**The takeaway:** Every detail you add saves you an editing round. Specificity up front is faster than iteration afterward.

## Section 2 — Context Loading

Claude doesn't know your brand, your data, or your writing style — unless you give it that information. The fastest way to get high-quality output is to paste in your existing materials.

**Paste text directly:**
```
Here is our brand voice guide:
[Paste 2-3 paragraphs from your style guide]

Using this voice, write a LinkedIn post announcing our new
partnership with DataCorp.
```

**Upload files:**
Click the paperclip icon to attach PDFs, CSVs, images, or documents. Claude will read the full file.

Good files to upload:
- Brand or style guides
- Product one-pagers
- Competitor landing pages (for analysis)
- Spreadsheets with campaign data
- Meeting transcripts or call recordings

**The reference pattern:**
```
Here is my reference material:
[Paste content]

Now, using this as context, please [your task].
```

This pattern works every time. The more relevant context you provide, the less guessing Claude does.

## Section 3 — Negative Instructions and Guardrails

Telling Claude what NOT to do is just as important as telling it what to do. This is especially useful when Claude keeps producing patterns you don't want.

**Useful negative instructions:**
- "Do not use jargon or acronyms."
- "Do not exceed 150 words."
- "Do not start with 'In today's fast-paced world' or any cliche opener."
- "Do not use exclamation marks."
- "Do not include a greeting or sign-off — just the body text."
- "Do not mention competitors by name."

**Setting boundaries on format:**
- "Use bullet points, not numbered lists."
- "No more than 3 paragraphs."
- "Do not use headers or subheaders — this is a plain email."

**Pro tip:** If Claude keeps doing something you don't like, add a specific negative instruction about it. "Stop using the word 'leverage'" is more effective than "use simpler language."

## Section 4 — Iterative Refinement

You don't need a perfect prompt on the first try. Claude is designed for back-and-forth conversation. The skill is knowing how to give useful feedback.

**Effective refinement phrases:**
- "Keep everything but make the opening more direct."
- "This is 80% there. Specifically, change the CTA to be less aggressive."
- "Rewrite just the second paragraph to focus on ROI."
- "Make it 30% shorter without losing the key points."
- "The tone is too formal — make it conversational, like a colleague sending a Slack message."
- "Add a specific example in the third bullet point."

**Ineffective feedback:**
- "Make it better." (Better how?)
- "I don't like it." (What specifically?)
- "Try again." (Same prompt = similar output)

**When to continue vs. start over:**
- **Continue** when the structure and direction are right but details need adjusting
- **Start a new chat** when the fundamental approach is wrong and you want to try a completely different angle
- **Start a new chat** if the conversation is getting very long (10+ back-and-forth messages) — Claude can lose focus in extremely long threads

## Section 5 — Using the Prompt Generator

Your team has access to an internal **Prompt Generator** tool built by engineering. It helps you construct well-structured prompts quickly instead of starting from scratch.

**How to access it:**
1. Go to [the Prompt Generator project](https://claude.ai/project/0197ad63-8685-75cc-8209-1279d717bd5e)
2. Start a conversation within that project
3. Describe what you need in plain language
4. The Prompt Generator will create a structured, optimized prompt for you

**When to use it:**
- When you're tackling a new type of task and aren't sure how to structure the prompt
- When you want to quickly generate a reusable template for a recurring task
- When you want to improve an existing prompt that isn't getting great results

**When to skip it:**
- For simple, one-off requests where the Day 1 template is sufficient
- When you're already confident in your prompt structure
- For quick follow-up messages in an existing conversation

The Prompt Generator is a great training wheel — use it liberally at first, and you'll naturally internalize the patterns over time.

---

[← Day 2 Overview](README.md) | [Next: Exercises →](exercises.md)
