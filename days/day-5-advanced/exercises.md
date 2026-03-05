# Day 5 Exercises

These exercises set up real team infrastructure. By the end, you'll have a working Project, experience with Artifacts, and a shareable prompt library.

---

## Exercise 1: Build Your First Project (10 min)

**Scenario:** You're setting up a Project for an upcoming campaign so your whole team can use Claude with consistent context.

**Steps:**

1. In Claude.ai, click **Projects** in the left sidebar, then create a new Project
2. Name it using the convention: `Marketing-[YourCampaign]-Q2` (use a real campaign name or invent one like `Marketing-SmartReportLaunch-Q2`)
3. Write Custom Instructions. Paste and customize this template:

```
Role: You are a senior marketing strategist supporting the Marketing team at [YOUR COMPANY].

Audience: Our target audience is marketing operations managers at mid-size B2B companies (200-1000 employees). They are hands-on practitioners who manage campaign execution, reporting, and marketing technology. Their biggest frustration is spending too much time on manual reporting.

Voice: Write in a direct, conversational tone. Be confident but not arrogant. Use concrete examples and specific numbers whenever possible. Never use buzzwords like "synergy," "leverage," or "game-changer." Never start a piece with "In today's fast-paced world" or similar cliches.

Product context:
- Product name: [YOUR PRODUCT] (or use "TaskFlow Pro" if practicing)
- Key feature being launched: AI-powered weekly report generation (SmartReport)
- Key stat: Customers save an average of 4 hours per week on reporting
- Competitors: ProjectBeam, WorkHub, PlanStack

Output defaults: Unless I specify otherwise, keep emails under 150 words, social posts under 200 words, and use bullet points for any list with 3+ items.
```

4. Upload at least one Knowledge File — use your brand guide, a product one-pager, or any relevant document. If you don't have one handy, skip this step and add files later.

5. Start a conversation **inside the Project** and test it:

```
Write a LinkedIn post announcing the SmartReport feature launch.
```

Notice how Claude uses the voice, audience context, and product details from your instructions without you having to specify them again.

6. Try a second test to see the instructions working across different tasks:

```
Write a subject line and opening paragraph for a cold email to a
marketing ops manager about SmartReport.
```

**What good looks like:** Both outputs should reflect your custom instructions — correct tone, audience awareness, product details — without you repeating that context. This is the power of Projects: set it once, use it everywhere.

---

## Exercise 2: Artifact Workshop (7 min)

**Scenario:** You need to create a campaign brief and a social media calendar as shareable documents.

**Steps:**

1. Open a new chat (inside your Project from Exercise 1, or in a regular chat)
2. Ask Claude to create a campaign brief:

```
Create a campaign brief for the SmartReport product launch as an Artifact.

Include:
- Campaign name and objective
- Target audience
- Key messages (3)
- Channels: Email, LinkedIn, one webinar
- Timeline: 6 weeks starting April 1
- Success metrics: MQLs, demo requests, trial signups
- Budget: $50K

Format it as a professional document with clear sections.
```

3. The brief should appear as an Artifact in the right panel. Review it.
4. Now ask for a second Artifact in the same conversation:

```
Now create a social media content calendar for the first 2 weeks of this
campaign as an Artifact. Format it as a table with columns: Date, Platform,
Post Type, Topic/Angle, CTA.

Include 3 posts per week across LinkedIn and Twitter.
```

5. Practice working with Artifacts:
   - Click between the two Artifacts to view each one
   - Copy one to your clipboard
   - If you see a download option, download one as a file
   - Click the share button to see sharing options (you don't have to share it)

**What good looks like:** Two well-structured Artifacts that are ready to share with your team. The campaign brief should be comprehensive enough to align stakeholders. The calendar should be specific enough to hand to a content creator.

---

## Exercise 3: Team Prompt Library (8 min)

**Scenario:** You've been using Claude all week and discovered prompts that work well. Now you'll formalize them into shareable templates for your team.

**Steps:**

1. Open a new chat in Claude.ai
2. Think of 3 prompts you used this week that produced good results. If you can't recall specific ones, use these three tasks:
   - Writing a follow-up email after a meeting
   - Creating a competitive positioning statement
   - Repurposing a blog post for social media

3. Ask Claude to help you formalize them:

```
I want to create a prompt template library for my marketing team.
Help me turn these 3 tasks into clean, reusable prompt templates with
clear placeholder variables in [BRACKETS].

Task 1: Writing a follow-up email after a sales meeting
Task 2: Creating a competitive positioning statement
Task 3: Repurposing a blog post for social media

For each template:
- Give it a clear name
- Write the full prompt with [PLACEHOLDER] variables
- Add a 1-line usage note explaining when to use it
- Keep each template under 150 words

Format these so they could be saved as a reference document.
```

4. Review the templates. Refine any that don't match your needs:

```
For template #[N], adjust the tone instruction to [YOUR PREFERENCE]
and add a placeholder for [SOMETHING YOU WANT TO INCLUDE].
```

5. **Optional:** Create a new Project called `Team-PromptLibrary`, paste the finalized templates into the Custom Instructions or upload them as a Knowledge File, and share it with your team.

**What good looks like:** Three templates that are specific enough to produce good results but generic enough to work across different situations. Clear placeholders that make it obvious what information needs to be filled in. A format that's easy for a teammate to scan and use.

---

## Recap

You now have real team infrastructure set up:
- **A working Project** (Exercise 1) with custom instructions and knowledge files
- **Experience with Artifacts** (Exercise 2) — creating, managing, and sharing standalone documents
- **A prompt library** (Exercise 3) — reusable templates ready to share with your team

Check out today's workflow for a complete team setup checklist: [Team Project Setup Playbook →](workflow-team-project.md)

---

[← Lesson](lesson.md) | [Day 5 Overview](README.md) | [Workflow →](workflow-team-project.md)
