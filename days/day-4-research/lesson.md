# Day 4 Lesson: Research & Analysis Workflows

Today shifts from writing to thinking. You'll use Claude to summarize long documents, analyze competitors, interpret data, and build research briefs — the analytical work that's high-value but eats hours of your week.

## Section 1 — Summarization Techniques

### Basic Summarization

The simplest and most frequently useful pattern:
```
Summarize this in 5 bullet points for a [ROLE — e.g., sales leader,
marketing director, executive]:
[PASTE CONTENT]
```

Specifying the audience changes what Claude emphasizes. A summary for a sales leader highlights revenue impact and customer objections. A summary for a CMO highlights brand positioning and campaign implications.

### Tiered Summarization

When you need both a quick take and the details:
```
Provide two summaries of this document:

1. Executive summary: 3 sentences, focus on decisions needed and impact
2. Detailed breakdown: section-by-section summary with key data points

[PASTE CONTENT OR UPLOAD FILE]
```

### Targeted Extraction

When you don't need a summary — you need specific information pulled out:
```
From this document, extract:
- Every mention of pricing or cost
- All specific metrics or statistics
- Any deadlines or dates mentioned
- Names and roles of people mentioned

Format as a table.

[PASTE CONTENT]
```

### File Uploads

For longer documents (10+ pages), use file upload instead of pasting:
1. Click the paperclip icon in Claude.ai
2. Upload your PDF, Word doc, or CSV
3. Ask your question — Claude reads the entire file

This works well for:
- Quarterly reports
- Competitor whitepapers
- Survey results (CSV or Excel)
- Meeting transcripts
- Industry research reports

## Section 2 — Competitive Analysis with Claude

### Structured Comparison

```
I'm analyzing a competitor. Here's what I have:

Their website copy: [PASTE]
Their product page: [PASTE]

Please analyze:
1. Their positioning: Who are they targeting and how do they describe themselves?
2. Their key value propositions: What 3 benefits do they lead with?
3. Their messaging strengths: What do they do well?
4. Their messaging weaknesses: Where is their copy vague, generic, or unconvincing?
5. How they differ from us: [DESCRIBE YOUR POSITIONING BRIEFLY]
```

### Role-Playing as a Competitor

A creative technique for pressure-testing your own messaging:
```
You are the VP of Marketing at [COMPETITOR NAME]. Based on the following
information about their product and positioning:

[PASTE COMPETITOR INFO]

Write a pitch for why a [TARGET CUSTOMER TYPE] should choose your product
over [YOUR COMPANY NAME], whose value proposition is: [YOUR VALUE PROP].

Be persuasive and specific.
```

Then flip it:
```
Now switch roles. You are our VP of Marketing. Write the counter-argument —
why should that same customer choose us instead?
```

### SWOT Analysis

```
Based on the following information about [COMPETITOR], generate a
SWOT analysis formatted as a 2x2 table:

[PASTE EVERYTHING YOU KNOW — WEBSITE COPY, PRODUCT INFO, REVIEWS, NEWS]

Our company's position for comparison: [BRIEF DESCRIPTION]
```

### Important Caveat

Claude's training data has a cutoff date. For competitive analysis:
- **Do** paste in current competitor materials (website copy, recent press releases, product pages)
- **Do** upload recent documents
- **Don't** ask Claude what a competitor is doing right now without providing that information
- **Always** verify specific claims about competitors independently

## Section 3 — Data Interpretation

Claude is surprisingly effective at turning numbers into narratives. The key is giving it the actual data.

### Table Interpretation

```
Here is our marketing performance data for the last 4 quarters:

| Metric | Q1 | Q2 | Q3 | Q4 |
|--------|-----|-----|-----|-----|
| MQLs | 450 | 520 | 480 | 610 |
| SQLs | 180 | 195 | 160 | 245 |
| MQL→SQL Rate | 40% | 37.5% | 33% | 40% |
| Revenue | $890K | $1.1M | $950K | $1.4M |
| CAC | $285 | $310 | $340 | $295 |

Analyze this data and provide:
1. A 3-sentence executive summary
2. The top 3 trends or patterns
3. 2 areas of concern with suggested next steps
```

### Generating Talking Points

```
Based on this data, write 5 talking points for a board presentation.
Each talking point should:
- Lead with the insight, not the number
- Include the supporting data
- Be one sentence
- Sound confident but honest about challenges
```

### Anticipating Questions

```
Based on this data, what are the 5 most likely questions a CMO would ask?
For each question, draft a concise answer using the data.
```

## Section 4 — Building Research Briefs

For deeper research tasks, use Claude as a thinking partner to structure your work.

### The Brief Builder Approach

**Step 1: Get the structure**
```
I need to create a research brief on [TOPIC] for [AUDIENCE].
What should a thorough brief cover? Give me a recommended outline
with section descriptions.
```

**Step 2: Fill it in section by section**
```
Write the [SECTION NAME] section. Here's what I know:
[PASTE YOUR NOTES, DATA, OR SOURCES]
Target: [WORD COUNT] words.
```

**Step 3: Identify gaps**
```
Review the brief so far. What important questions does it NOT yet answer?
What additional data or research would make this brief more actionable?
```

This three-step approach turns Claude into a research assistant that helps you think more rigorously — not just produce text.

---

[← Day 4 Overview](README.md) | [Next: Exercises →](exercises.md)
