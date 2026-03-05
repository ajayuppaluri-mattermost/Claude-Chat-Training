# Day 5 Lesson: Advanced Features & Team Workflows

This week you've learned to use Claude as an individual productivity tool. Today you'll unlock the features that make Claude a team asset — Projects, Artifacts, and shared workflows. You'll also get a high-level understanding of Cowork and Code for when you need capabilities beyond standard chat.

## Section 1 — Projects Deep Dive

Projects are the single most powerful feature for teams. A Project gives Claude persistent context — so instead of re-explaining your brand, audience, and goals in every conversation, you set it up once and every chat within that Project starts with that knowledge.

### Creating a Project

1. Click **Projects** in the left sidebar (or the "+" icon next to it)
2. Give it a clear name — use a naming convention like `[Team]-[Initiative]-[Quarter]`
   - Example: `Marketing-ProductLaunch-Q2`
   - Example: `Sales-CompetitiveIntel-2025`
3. Write **Custom Instructions** (this is the most important step — see below)
4. Upload **Knowledge Files** (documents Claude should reference in every conversation)

### Writing Custom Instructions

Custom Instructions shape every conversation in the Project. Think of them as a brief you give to a new contractor on their first day.

A strong set of Custom Instructions includes:

```
Role: You are a marketing strategist supporting the Marketing team at [Company].

Audience: Our target audience is [description — be specific about industry, company size, role, pain points].

Voice: Write in a [tone] voice. Always [positive instructions]. Never [negative instructions].

Constraints: All content must comply with [guidelines — brand guide, legal requirements, etc.]. Maximum length for emails is [N words]. Maximum length for social posts is [N words].

Key facts:
- Our product is [description]
- Our key differentiators are [list]
- Our main competitors are [list]

Output preferences: Unless I specify otherwise, use bullet points for lists, keep paragraphs under 3 sentences, and always include a clear CTA.
```

### Uploading Knowledge Files

Upload documents that Claude should reference across all conversations in the Project:

- **Brand/style guide** — So Claude matches your voice
- **Product documentation** — Features, pricing, positioning
- **Target persona documents** — Who you're writing for
- **Campaign briefs** — Current initiative details
- **Examples of approved content** — So Claude can match the standard

Each Project supports up to 200K tokens of context — roughly equivalent to a 500-page book. That's plenty for most marketing teams.

### How It Works in Practice

Once your Project is set up:
1. Open the Project from the sidebar
2. Start a new conversation — Claude already knows your brand, audience, and guidelines
3. You can skip the context-setting you've been doing all week and go straight to your task
4. Every conversation within the Project benefits from the same instructions and knowledge

## Section 2 — Artifacts

Artifacts are standalone content pieces that Claude generates in a separate panel alongside the conversation. Think of them as outputs that live outside the chat.

### When Artifacts Appear

Claude automatically creates Artifacts for:
- Longer structured documents (briefs, reports, plans)
- Tables and data displays
- Code snippets
- Anything you explicitly ask to be created as an Artifact

### Working with Artifacts

- **View** — Artifacts appear in a panel to the right of the conversation
- **Copy** — Click the copy button to grab the content
- **Download** — Save Artifacts as files
- **Edit via chat** — Ask Claude to modify an Artifact by describing the changes
- **Version history** — Compare different iterations using the version selector

### Sharing Artifacts

One of the most useful team features:
- Click the share button on any Artifact to get a shareable link
- Anyone with the link can view and use the Artifact
- They can even interact with AI-powered Artifacts using their own Claude account
- Sharing is free — usage counts against each viewer's own plan

### When to Use Artifacts

- Generating a campaign brief you'll share with the team
- Creating a spreadsheet-style comparison table
- Building a document that needs multiple rounds of revision
- Any output that needs to live beyond the conversation

## Section 3 — Team Features

### Sharing Conversations

You can share specific conversations with teammates:
- Useful for showing your thought process or a particularly good Claude interaction
- Team members can view shared conversations and continue working from where you left off

### Team Administration

Your Team/Enterprise plan includes:
- **Seats** — Each team member gets their own account with full access
- **Usage limits** — Higher limits than individual plans; check with your admin for specifics
- **Privacy** — By default, your conversations are private. Only conversations and Projects you explicitly share are visible to teammates.

### Chat Search

Claude can search across your conversation history within your account:
- "Have we ever discussed [topic]?"
- "What was I working on before the holiday break?"
- "What were the next steps from my competitive analysis last week?"

This works across individual chats and within Projects.

## Section 4 — Beyond Chat: Cowork & Code

Standard chat is ideal for most daily tasks. But Claude offers two additional modes for when you need something different.

### Cowork

**What it is:** Cowork lets Claude work on longer tasks autonomously in the background. Instead of a back-and-forth conversation, you give Claude a task and it works on it independently — like assigning work to a capable colleague.

**When to use it instead of chat:**
- Drafting a long document (10+ pages) where you'd rather review a finished product than iterate step-by-step
- Processing a large batch of similar tasks (e.g., rewriting 20 product descriptions)
- Research and analysis tasks where Claude needs to do multiple steps on its own
- Any task where you'd prefer to do other work while Claude works in parallel

**How it works:** Start a Cowork session from the Claude interface. Describe what you want as if you were briefing a colleague: clear objectives, context, and what "done" looks like. Claude works on it and notifies you when it's ready for review.

**Think of it as:** Chat is a conversation. Cowork is a delegation.

### Code

**What it is:** Claude Code is a command-line interface (CLI) tool for software development. It lets Claude read, write, and modify code directly in a developer's terminal.

**When it's relevant to you:**
- If you work closely with engineering or have technical teammates, they may use Claude Code for writing code, debugging, and building features
- You don't need to learn Claude Code yourself, but understanding it exists helps you collaborate with technical teammates who use it
- It's included in your Team/Enterprise plan

**The key difference from chat:** Claude Code works directly with code files on a developer's computer, while Claude.ai chat works with text in a browser. Chat is your tool; Code is your engineering team's tool. Both are powered by the same Claude AI.

## Section 5 — Building Team Conventions

The difference between a team that gets value from Claude and one that doesn't is usually conventions — shared agreements on how to use the tool.

### 1. Create a Shared Prompt Library

Set up a Project specifically for shared prompts:
- Name it something like `Team-PromptLibrary`
- Upload your best prompt templates as knowledge files
- When someone discovers a prompt that works well, add it to the library
- New team members start here to see what's already been figured out

### 2. Establish Naming Conventions for Projects

Agree on a format so everyone can find things:
- `[Team]-[Initiative]-[Quarter]` for campaign-specific Projects
- `[Team]-[Always-On]` for persistent Projects (like brand voice or competitive intel)
- Avoid personal projects in shared spaces — those can be individual

### 3. Write Team-Wide Custom Instructions

For shared Projects, include instructions that apply to everyone:
- Brand voice and tone requirements
- Compliance or legal constraints
- Output format standards (e.g., "always use metric units," "always include a CTA")
- Information that should never be shared externally

### 4. Onboard New Team Members

Point new hires to:
1. This training course (start with Day 1)
2. Your team's shared Prompt Library Project
3. Any active campaign Projects they need access to
4. The [Cheat Sheet](../../resources/cheat-sheet.md) for quick reference

---

[← Day 5 Overview](README.md) | [Next: Exercises →](exercises.md)
