---
layout: post
title: How to Reign In Your Coding Agent
date: 2025-06-18 21:08 +0800
last_modified_at: 2025-06-18 21:08 +0800
excerpt: "Everyone’s hyped about AI coding agents. Big tech says they’re replacing engineers. Solo founders claim they’ve built entire startups with a prompt. But if you’ve tried to use one on a real project, you’ve probably realized: it’s messy. This post explores how to make it less so - by giving your agent just enough structure to be useful."
open_graph:
  image:
    path: /assets/images/georges-malher.jpg
    caption: "How to Reign In Your Coding Agent"
categories:
  - technology-and-strategy
tags:
  - ai-adoption
  - workflow-automation
  - internal-tools
  - product-development
---

*Everyone’s hyped about AI coding agents. Big tech says they’re replacing engineers. Solo founders claim they’ve built entire startups with a prompt. But if you’ve tried to use one on a real project, you’ve probably realized: it’s messy. This post explores how to make it less so - by giving your agent just enough structure to be useful.*
{: .notice}

## The state of agentic coding

AI coding agents are either about to write all software or are still an over-hyped distraction. On the one side you have people like Anthropic’s CEO, Dario Amodei, who outrageously stated that essentially [all code will be written by AI by the end of 2025](https://www.businessinsider.com/anthropic-ceo-ai-90-percent-code-3-to-6-months-2025-3), and on the other side you have people who still claim that AI coding agents are more trouble than useful, and doesn’t help them build faster. I’d argue reality sits somewhere in between.

There are even examples on Twitter of people claiming to have deployed full-scale SaaS products with only Lovable. And although it’s probably possible to launch a SaaS without coding a line of code yourself, it’s most likely not very wise. AI-generated code often exposes serious security vulnerabilities, and many of these sites have already been easily hacked. Although the Lovable team has made [attempts to mitigate this](https://www.linkedin.com/posts/oliversild_releasing-gimmick-security-features-are-going-activity-7323316047359430656-zSsK/), I would still not trust it. 

Apart from Dario Amodei, there’s also a lot of talk from other big-tech players on how more and more of their code is written by AI. Last year, Google CEO Sundar Pichai, claimed that [25% of their code was generated by AI](https://www.forbes.com/sites/jackkelly/2024/11/01/ai-code-and-the-future-of-software-engineers/) and Meta has made [similar claims](https://www.engadget.com/ai/mark-zuckerberg-predicts-ai-will-write-most-of-metas-code-within-12-to-18-months-213851646.html). These companies obviously have big incentives in making such claims, so I wouldn’t trust this outright, but it would be risky to ignore it completely. 

Solo-founders or *solopreneurs* arguably have the biggest incentive in making something like this work, due to their limited resources. And I think you’ll be hard-pressed to find one who isn’t already using Cursor agents or similar to write some or even most of their projects’ code. For example, [levelsio](https://www.twitter.com/levelsio) famously built a flight simulator game [mostly by “vibe-coding”](https://x.com/levelsio/status/1893468798101094587). For those still unfamiliar with this term, it was [originally introduced](https://x.com/karpathy/status/1886192184808149383) by Andrej Karpathy to express the state *“where you fully give in to the vibes, embrace exponentials, and forget that the code even exists”*.

Smaller startups like my own, Midstay, are always under pressure to make the most of our resources, and thus also has great incentives in making this work. The last month or so I’ve therefore invested serious time looking into how we could use this to increase our productivity.

## The problem

If you have tried to use an AI agent to work on a project that is non-trivial, you have probably run into issues pretty fast. First of all, if you want it to be any real help as opposed to you coding everything yourself, you’re going to want to use what Cursor calls “yolo-mode”. For anyone not familiar, this is Cursor’s naming for giving your agent free reigns to code without asking for your confirmation at every step. 

This seems very powerful at first, but if the only context you provide the agent is the same that you would provide a developer for a typical sprint task, e.g. a description and some acceptance criteria in Notion or Jira, you’ll not be happy with the result. A developer will have had months or years of context building on your product, and the agent does not have this. This often leads to surprising and sometimes disastrous detours that derail the implementation. Moreover, the agent can easily get stuck in loops, and start to over-engineer the problem in an attempt to get itself out of trouble. To fix that, you either have to just restart from scratch, or have the agent revert the steps. You can also restore to checkpoints, but either way, this is really inefficient and annoying, and doesn’t provide an improvement to a conventional workflow.

## Solving the context problem

The extent by which the agent will run into problems is related to the amount of context it has about the codebase and the problem itself. But the challenge is that you can’t just feed it infinite context and expect it to just work either. The different AI models have a limited context window, 200,000 tokens for Claude Sonnet 4, corresponding to ~10,000-15,000 lines of text. But even if it can swallow all this doesn’t mean that it will do well if provided with all that information. Typically, the models’ reasoning ability goes down the more context it is fed. It simply does not know what to prioritize and focus on. In effect, you need to feed it as much context as the task requires, but nothing more than that. 

What does this mean in practice when you are trying to get it to write a feature, fix a bug, refactor something or do any other type of chore? If you need to spend all this time and effort to calibrate the perfect amount of context for the agent, how is this helping you move faster?

Some of the more experienced “vibe-coders” I’ve come across, attempt to solve this by breaking the process down into multiple steps where context is contained and summarized in each step. Cursor also has built-in functionality to do this inside and across each chat. Most of the “vibe-coding” examples I’ve found are from those building a product from scratch, and one of the most popular frameworks that’s used to deal with the context and workflow problem is *Task master* ([claude-task-master](https://github.com/eyaltoledano/claude-task-master)). This tool requires an elaborate Product Requirement Documents (PRD) that contains a detailed description about all the necessary information about a product, and breaks it down into smaller tasks. The agent can then work with the context of one task at a time, and it also tracks progress, and updates the tasks with new information learned underway. This improves things significantly, since the agent doesn’t get overwhelmed by thinking about too many things simultaneously.

*Task master* is nice, and even if it requires a PRD, you can also feed it a smaller feature or task document, and it will adapt. This is obviously crucial, since in an existing product you are typically solving smaller tasks at a time, to make it easier to review, safer to deploy, limit conflicts and more. However, it doesn’t solve the entire problem. Even the best workflow is only as good as your requirement prompts.

So while tools like *Task master* help with context slicing, their effectiveness still hinges on well-formed requirements. That raises a deeper question: how do you actually create these requirements without slowing your team down?

## Building your own workflow

Every developer and team develops their own workflow based on their experience, preferences and philosophies. Midstay and I are no exception. I’ve therefore attempted to develop a process that mimics *Task master*, but where we keep it simpler and stay closer to how we usually work. Most importantly, I want a lot of control over each step of the way, so that I can correct the agent before it derails and gets lost down a tangent. I’ve called it [Railagent](https://github.com/railwave-labs/railagent), and for now it’s simply a collection of prompts packaged in an MCP server.

The workflow should be optimized for the tasks we usually work with, and the pace, review process etc. To achieve this I have found inspirations in existing solutions, mainly *Task master*, but adding some prompts and hooks to help the developer generate thorough requirement documents, and some predefined behaviour around how it should behave around testing, commits etc. Essentially I wanted it to use the following approach.

**Planning**

1. *The agent* plans the implementation based on a task description, and available codebase and product context. The plan should include concrete steps that correspond to a single commit.
2. *The developer* reviews the plan and steps created by the agent and asks it to adjust any wrong turns or assumptions it has made.
3. *The agent* breaks the implementation plan down into separate task files that are tracked in a [todo.md](http://todo.md) document.

It’s only step 1 and 2 that differs from what *Task master* provides. I prefer having this extra step before the agent breaks down the steps into tasks, due to the importance of a thorough requirements document.

To optimize these two steps, the agent can prepare a detailed architecture document via a carefully designed prompt that also takes in context about the different modules we have in our application, and their purpose. These are described as markdown files in an application context directory in `.cursor/`. Using Cursor’s Max mode and pulling this into context during planning leads to significantly better planning results. 

*Currently the prompt generates a document over the entire application, but in the future, it’ll probably be wise to break this down into modules to avoid wasting context window on irrelevant things.* 
{: .notice}

**Execution**

1. *The agent* gets to work on the first task and is instructed to pause before it is done and ready to commit. At this point the developer can review the diffs, and either correct any missteps or allow it to commit the work.
2. Before committing, *the agent* writes down notes about what has been done in the previous step, and updates any of the upcoming tasks for which the conditions have changed. It’s also instructed to review the changes to security vulnerabilities and other potential issues.

**Recent learnings**

When I started this work I was under the impression that *Task master* was mainly meant for “vibe-coding” full-scale products from scratch. Since then I’ve realized that it handles the task management process way better than Railagent’s simple prompts, and there’s already a big community continuously improving on it. I aim to start using *Task master* for the task management itself, and rather provide some additional functionality through Railagent, including extra planning steps, and some distinct behaviour that’s not provided or is cumbersome to use Cursor rules for.

## Looking ahead

It’s very early days for this, but in our last sprint I attempted to use the workflow for the first time to solve a mid-sized refactor, and it worked surprisingly well. There’s still a lot of adjustments and corrections that have to be made in the different prompts and workflows, but it’s a good start. The next sprint we plan to have the whole team working with it, adjusting as many existing hiccups as we can, and to share our experience in working in this way.

We will see how it goes, but I do expect us to increasingly be working in this way. Currently I’m highly focused on enabling us to go as far as the current tech allows, through designing good workflows and other optimizations. 

This could then also have an impact on how we architect our application, and how much effort or priority we put into making changes. Although we already have a modular approach to writing code, we haven’t gone all in with a *modular monolith* architecture yet. However, this has been on my mind for a while already, and considering how such an approach can reduce the surface area when working on a problem within a specific domain, it would most likely also allow for an agent to work far more effectively. Interesting times ahead!

*Curious to try it? The Railagent prompts are up on GitHub. Nothing fancy - just a starting point that’s worked well for us so far. [Check it out here](https://github.com/railwave-labs/railagent).*
{: .notice}