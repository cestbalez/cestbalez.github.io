---
layout: post
title: 'What We’re Rethinking in the Age of AI: Product, Workflow, and Scale'
date: 2025-06-11 13:25 +0800
last_modified_at: 2025-03-23 17:34 +0800
open_graph:
  image:
    path: /assets/images/guerrillabuzz.jpg
    caption: "What We’re Rethinking in the Age of AI: Product, Workflow, and Scale"
categories:
  - technology-and-strategy
tags:
  - ai-adoption
  - workflow-automation
  - product-development
  - saas
  - agents
  - internal-tools
---

When we started Midstay in 2021, we were building a B2C social app for digital nomads and remote workers. Like many early-stage startups, we kept our tech stack lean and focused on moving fast. Our workflow was fairly pragmatic and conventional: Figma for design, Notion for planning, Heroku for deployment, and Tailwind with Flowbite to build our Ruby on Rails UIs quickly. It worked well, and for a team of our size, we were reasonably productive.

But looking back now, 4 years later, it feels like we were moving at a snail’s pace. The tools were solid, and although we had some automation, it was still a very manual process.

With the arrival of GPT-3 in 2022, I was excited. And even more so when Github launched their Copilot. However, after playing around with it for a while, it left a lot to be desired. GPT-3 was useful, but lacking, and I couldn’t make Copilot work for me past some one-line autocompletes. This made me shift my attention away from it for a while, mainly using ChatGPT as a pair programmer/strategist, and just checking in occasionally to see what was new in the AI hype. For a long time, it felt too immature to make a substantial difference.

### A super-powered workflow?

Since then we pivoted to B2B and focused fully on Team Retreats. Initially we used our tech resources to build an internal tool to streamline both our sales and operations, but along the way we saw an opportunity to offer the core functionality of this tool to our main partners, the MICE (Meetings, Incentives, Conferences, and Events) hotel industry. This industry is currently highly manual, and follows a very similar workflow as our Team Retreats business. As we started planning that shift, and as the AI agent hype was really starting to roar, I decided to intensify the research into how new AI developments could help us build our upcoming SaaS initiative. Initially I was focused on the tech workflow, but it has led me way past that.

Over the last few months our development workflow has started to transform:

- **Prototyping** now takes a fraction of the time using tools like Lovable or Builder.io.
- **Cursor** is now writing a growing share of our code, thanks to tighter workflows and better prompt design. It integrates deeply with Notion, GitHub, Figma, and Sentry, so context flows directly into the development experience, helping us move a lot faster. We are optimising our Notion templates to provide the best possible context for our agents, and I’ve built the first iteration of our a tailored workflow system, [MCP](https://github.com/railwave-labs/railagent).
- **Claude Code in GitHub** lets us apply small AI-driven changes directly to pull requests, without even opening an IDE.
- **Cursor’s Background Agents** (and recently GitHub’s Copilot Agents) now act like junior devs in the cloud. You assign a task, and they open a PR when done. We haven’t used this yet, but I’m investigating how we could “train” these agents, or provide improved workflows and context, for them to solve increasingly complex tasks.

While we're cautious about giving too much autonomy without stronger guardrails—and I haven’t completely jumped on the 'vibe-coding' train—it’s clear this is where things are heading. And what we are learning is that putting effort into guiding and controlling the AI agents is starting to pay off big time as the processes get fine-tuned and the tooling keeps improving.

### Scaling a service business

These were areas I was directly researching to improve our team, but as I was learning more and more I was starting to understand new use cases across our business. First of all, we have been aware that our Team Retreats service business has had clear limitations to scale. There are so many parts of the business that have been difficult to automate, but this is about to change with the potential of modern AI agents. Service businesses now have the potential to scale in a way they didn’t use to before.

Many of our workflows depend on interpreting context, stitching together information from different sources, and making judgment calls — all things that were hard to automate with conventional systems. But agents that can operate across tools, extract meaning, and take action are starting to make this possible. We're now exploring how parts of our retreat coordination process could be handled by agents that interpret incoming requests, generate draft itineraries, assign tasks, or even prep proposals. It's early, but the shape of what's possible is getting clearer.

### The future SaaS landscape

Finally, this is also starting to change the way we think about our SaaS. Our internal product is still quite conventional, with our procedures and interfaces being handled by our Ruby on Rails backend - in Ruby, and this was our starting point as we were brainstorming the new potential SaaS product. We now see a different future, where SaaS may be shifting from interface-driven software toward agent-driven products. We are not fully ready for this shift yet, but we are preparing for it. It brings attractive potential in how we can offer more flexibility in our software at a lower development cost, but most importantly it can provide a better experience and capabilities for our future users.

### Don’t sleep on this

We are obviously not the only company in this transition, and we may even be late. However, this post is for anyone still on the sideline, either out of lack of interest or faith, or just because you haven’t spent the time it takes to dig into it. To be fair, it’s a significant investment, but I think it will be a huge mistake not to make it. Now. Software companies are most likely to adopt all the new tooling first, but other industries also need to pay attention. Don’t sit on the sidelines just because your initial prompts didn’t seem valuable. It will take effort, but it will be worth it.