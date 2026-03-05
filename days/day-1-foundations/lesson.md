# Day 1 Lesson: Getting Comfortable with Claude

## Section 1 — Choosing Your Platform

Claude is available in two forms. You can use either or both depending on your situation.

**Claude.ai (Web)**
- Access at [claude.ai](https://claude.ai) in any browser
- Best for: quick access from any device, no installation needed, sharing conversations with teammates
- All features available immediately

**Claude Desktop App**
- Download from [claude.ai/download](https://claude.ai/download) for Mac or Windows
- Best for: keeping Claude in a dedicated window separate from your browser tabs, slightly faster startup
- Same features as the web version

**Which should you use?** Start with whichever feels more natural. Most marketing and sales professionals prefer the web version since you're already in a browser. The desktop app is nice if you find yourself using Claude frequently and want it always one click away.

## Section 2 — The Interface Tour

When you open Claude.ai, here's what you'll see:

**Left Sidebar**
- **New Chat** button at the top — starts a fresh conversation
- **Search** — find past conversations by keyword
- **Recent conversations** — your conversation history, most recent first
- **Starred conversations** — pin important chats for easy access (click the star icon on any conversation)

**Main Area**
- **Message box** at the bottom — where you type your messages
- **Attachment button** (paperclip icon) — upload files like PDFs, images, CSVs, or documents
- **Model selector** — choose which Claude model to use (Claude Sonnet is fastest, Claude Opus is most capable for complex tasks)
- **Conversation area** — your messages and Claude's responses appear here

**Settings** (click your profile icon, bottom-left)
- Display name, team membership, usage information
- Feature settings including Artifacts (make sure this is turned on)

## Section 3 — Connecting Gmail, Google Calendar & Google Drive

Your Team/Enterprise plan lets you connect Google services so Claude can read your emails, calendar events, and Drive files directly — no copy-pasting needed. You set these up through **Settings > Connected Apps** (or via the integrations icon in the message box).

**Google Drive**

Setup:
1. Go to **Settings > Connected Apps**
2. Click **Connect** next to Google Drive
3. Authorize with your work Google account when prompted

How to use it: Click the attachment button (paperclip icon) in the message box, select **Google Drive**, then browse or search for the file you need. Claude reads the contents directly in your conversation.

> Works with Google Docs, Sheets, and Slides — no need to download and re-upload.

**Gmail**

Setup:
1. Go to **Settings > Connected Apps**
2. Click **Connect** next to Gmail
3. Authorize with your work Google account when prompted

How to use it: Once connected, Claude can search and read your emails when you ask. Try this example prompt:

```
Find my most recent email from [person] about [topic] and summarize the key points.
```

> Great for drafting replies, summarizing email threads, and finding information buried in your inbox.

**Google Calendar**

Setup:
1. Go to **Settings > Connected Apps**
2. Click **Connect** next to Google Calendar
3. Authorize with your work Google account when prompted

How to use it: Claude can see your calendar events and help you prepare. Try this example prompt:

```
What meetings do I have tomorrow? Help me prepare talking points for the 2pm strategy call.
```

> Perfect for meeting prep, daily schedule summaries, and finding free time for new meetings.

**Connect all three now** — you'll use them throughout this course. If any connector isn't available, check with your team admin.

Your organization may also have other integrations available (Notion, web search, Slack, etc.). Check **Settings > Connected Apps** for the full list.

## Section 4 — Anatomy of a Good First Message

The biggest mistake new users make is writing vague messages. Compare these two approaches:

**Vague prompt:**
```
Write me an email about our new product.
```

Claude will produce something generic because it doesn't know your product, audience, tone, or goal.

**Clear prompt using Role + Task + Context + Format:**
```
You are a B2B marketing copywriter.

Write a product launch announcement email for our project management
tool, TaskFlow Pro.

Context:
- Target audience: IT directors at mid-size companies (500-2000 employees)
- Key feature: AI-powered resource allocation that reduces project delays by 30%
- Launch date: March 15
- Special offer: 60-day free trial for companies that sign up in March

Format:
- Subject line + email body
- Professional but approachable tone
- Under 200 words
- End with a clear call-to-action
```

The difference in output quality is dramatic. The four parts of a good prompt are:

1. **Role** — Tell Claude who it should be ("You are a B2B marketing copywriter")
2. **Task** — What you need done ("Write a product launch announcement email")
3. **Context** — Background information Claude needs (audience, details, constraints)
4. **Format** — How the output should look (length, tone, structure)

You don't always need all four, but the more you include, the better your results.

## Section 5 — What Claude Can and Cannot Do

**Claude is great at:**
- Drafting and editing text (emails, blog posts, social copy, reports)
- Summarizing long documents
- Brainstorming ideas
- Restructuring information into different formats
- Analyzing text you provide (competitor copy, survey responses, meeting notes)
- Explaining concepts in simple terms

**Claude has limitations:**
- **No real-time data** — Claude's training has a knowledge cutoff. Use web search for current information, or paste in the data yourself.
- **No memory across conversations** — Each new chat starts fresh. Claude doesn't remember what you discussed yesterday (unless you use Projects — covered in Day 5).
- **Can generate plausible-sounding but incorrect information** — Always verify specific facts, statistics, quotes, and claims. Claude is a drafting partner, not a fact database.
- **Works best with your raw material** — Don't ask Claude to guess about your product, audience, or data. Paste it in.

## Section 6 — Your First Conversation Walkthrough

Let's do this together right now:

1. Open [claude.ai](https://claude.ai) in your browser
2. Click **New Chat**
3. Copy and paste this prompt into the message box:

```
You are a marketing strategist helping a B2B SaaS company.

I just had a brainstorming meeting and here are my rough notes:
- Need Q2 campaign for new analytics dashboard feature
- Target: marketing managers at e-commerce companies
- Pain point: they spend hours manually building reports
- Our dashboard auto-generates weekly reports with AI insights
- Budget: $50K for the quarter
- Channels: email, LinkedIn, one webinar

Please turn these notes into a clean campaign brief with:
- Campaign objective (1 sentence)
- Target audience description
- Key messages (3 bullets)
- Channel plan with one tactic per channel
- Success metrics to track
```

4. Press Enter (or click the send button)
5. Read Claude's response
6. Now type a follow-up: **"Make the key messages more specific to e-commerce pain points, and add a timeline for the quarter."**
7. Notice how Claude builds on the previous response

Congratulations — you just had your first productive conversation with Claude.

---

[← Day 1 Overview](README.md) | [Next: Exercises →](exercises.md)
