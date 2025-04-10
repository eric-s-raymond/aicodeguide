<div align="center">
<img src="https://i.imgur.com/hpgnZsf.png" alt="AI Code Guide">
  <p align="center">
    𝕏 <a href="https://x.com/aut0mata">Follow me on X</a> • 
    🤗 <a href="https://void.cc">My personal website</a> • 
    💻 <a href="https://github.com/automata">My GitHub</a>
  </p>
</div>
<br/>

> Everything you wanted to know about using AI to help on coding.

## Introduction

It's April of 2025, I just arrived in Munich -- I live in London but I'm here for a
work trip -- and I decided to open my laptop, pop a Club Mate and dump
everything I have been researching and implementing around AI to help on
code generation..

I really love coding, I do. I'm doing that for a living during the past 15
years as both a SWE and AI/ML Engineer. I love computers, to build them, break
them in parts, understand their fundamentals and everything around it. And
because of that I love to spend time reading about it, studying it, hacking
it...

All that is to say that I've been following hypes and trends for a long time
and the way we interact with computers and code them is
changing. And it's a profound change. It's a change on the tools we use, the
way we code and think about software products and systems.

And it's changing super fast! New LLM models are being released every week. New
tools, new editors, new "vibe coding" practices, new protocols (MCP, A2A, SLOP,
...)... and it's really hard to keep track of all that. Everything is
scattered in different places, websites, repos, etc.

That's why I decided to
write this guide. It's my humble attempt to put everything together and present
you the practices and tools around AI coding or AI code generation, all in one
place, with no fluf, in an accessible way.

But wait, is this guide for me? Let's see:

- If you're a coder/dev/SWE/MLE who already know how to code but is not using
  AI code assistants yet. Yep, this guide is for you: it introduces all most
  recent tools and practices to make the most of them to help on your daily
  jobs
- If you never coded before but you're interested in this new "vibe coding"
  thing to build your own SaaS and other software products. This guide is
  definetely for you: I'll try to do my best to remove obscurity and leave you
  only what's required to start your journey, but being super critic about what
  is really important and what's "just hype" (tm)

Let's start!

📚 Resources:

- [The End of Programming as We Know It](https://www.oreilly.com/radar/the-end-of-programming-as-we-know-it) by Tim O'Reilly
- [How to prepare for the future of development and AI](https://www.youtube.com/watch?v=BP54GqVK3JA) by Santiago

## AI coding? Vibe coding?

All those terms are pretty similar. But basically AI coding is about using AI
models (specially LLMs these days) and all the tooling around it to help you
write software. It's also called "AI for code generation" or "code gen" for
short, and there's an entire fascinating field of research and engineering,
that dates back to 1950's when we used Lisp to generate code. Now we have LLMs
as main engines to power code generation, and there's also some threads on
neurosymbolic hybrid approaches starting to show up. And AI coding is also a
practice: if you're using Cursor and tab-tab-tab your way to get completions,
you're "AI coding"; if you're full on using Cursor agent mode, you're also "AI
coding". In summary: it's any way to use an AI models to help you to generate
code. Generally you have coders in this group.

Vibe coding is AI coding cranked up :-) Here you don't care much about the code
being generated, you just give a prompt and expect the AI to code everything
for you. The term was creaetd by Karpathy in 2024 and it's getting pretty
popular. IMHO it's helping to democratize coding for everyone that never
thought about coding before!

So, in summary, no matter if you're using AI to discuss your software ideas or
to help on coding only parts of your already existing code base, or if you're
full on vibe coding, you're using AI to help you generate code. Let's call it
AI coding and move on.

## What's AI and LLM?

If you know what's all about, please move on for the next section. Otherwise,
just a few words about our main guys here.

# 🗺️ The Roadmap

## 1. How I start?

- If you don't know how to code and want to play with it, I recommend starting
with some web-based tool like [Bolt](https://bolt.new), [Replit](https://replit.com)
or [Lovable](https://lovable.dev).

- If you already know how to code, install Cursor or Windsurf. You can start with the
free plan and then upgrade to $20 monthly plan. I pay for Cursor, it's pretty good and cheap,
given you'll have tons of tokens to use on most recent LLM models out there.

- If you want a more open source alternative, try OpenHands. You run it as a Docker container
that exposes a webapp. You'll have to create an Anthropic account to get access to an API key,
or use some LLM available in OpenRouter.

- If you already know how to code and is a terminal maniac like me, check aider and Claude Code.
For those you'll need to setup API keys for Anthropic Claude or for OpenRouter.

> Suggestion: I really recommend creating an account in OpenRouter. It's really easy and you'll
get access to the most updated LLM models and even free versions of it. For instance,
my go-to LLM model these days is Gemini 2.5 Pro and I run it through OpenRouter for free
(there are daily quotas of credits, but it's still an interesting option for experiments
with aider and OpenHands, for instance).

> Important note: Claude Code is super expensive these days! You can easily spend $50/day.
So be careful, monitor your usage. That's why I recommend starting with Cursor so you don't
have to worry about it.

📚 Resources:

- [Vibe Coding 101 with Replit](https://www.deeplearning.ai/short-courses/vibe-coding-101-with-replit/)
- [OpenRouter]()

## 2. How I prompt for coding?

After you installed, played with those tools a bit, you'll notice they will
hallucinate, enter in endless cycles of trying to fix a possible error, etc.
It's important to know how to prompt well. Some tips:

- Do not ask everything in one prompt. Only
- Give it details
- Break you project into tasks and subtasks
- Create a PRD first
- Try different models for different goals
- Try different models to confirm
- LLMs are "yes machines", so be critic

📚 Resources:

- [You are using Cursor AI incorrectly...](https://ghuntley.com/stdlib/) by Geoffrey Huntley:
here Geoff introduces his
idea of using a stdlib of Cursor rules and keep growing it automatically
- [From Design doc to code: the Groundhog AI coding assistant (and new Cursor vibecoding meta)](https://ghuntley.com/specs/) by Geoffrey Huntley:
after 

## What are Cursor rules?
## 3. How I avoid hallucinations? What is a PRD?

PRD. What?! They say that the best ways to solve a problem in engineering is to
create a new achronym and here it's no exception :-) J/k... PRD is short for
Project Requirements Document. Basically, it's just a bunch of docs (or only
one doc) describing the requirements and other details about your software
project.

Turns out, if you leave your loved LLM free, with not much context of what to
do, it will hallucinate pretty wild and quick. You need to tame the beast and
PRDs are a great way to do it.

What I most like about PRDs is how they are super helpful to anyone, from
people who never coded before to senior SWE.

You don't need any background to start a PRD, you just need your idea for an
app and that's it.

To write a PRD, you can follow some strategies:

Strategy 1:

Open ChatGPT and copy-and-paste the following prompt:

...

Strategy 2:

In Cursor, ...

## How I start my project?

### Webapp

### Backend

### Python Project

## 4. How I deal with errors and bugs?

One thing you must know about coding and softwares in general: they will fail.
No matter what you try to prevent that, it will happen. So let's first embrace
that and be friends with errors and bugs.

The first strategy here is to mimic what SWE do: see what the
interpreter/compiler gave to you as an error message and try to understand it. 

Another great idea is to add MCP tools great for debugging like browser one 

## 5. What's MCP (and SLOP) and how can I benefit from it?
- https://mcpslop.com/
## Creating my own MCP server
## Start from scratch or with a boilerplate?
## Greenfield/clean state/fresh project vs existing codebase
- And if my code already exists?
    - repomix, llmtxt and other ways to fit your code base into LLMs
    - go per task instead of per project!
## Should I use TDD or any other type of tests?
## How to make it safe?
## How to get structured data? How to validate the LLM output?
## I want to learn more about all this code the AI is generating

Do you need to understand programming? Computer and systems fundamentals? Not entirely,
but I truly believe in computer literacy: everybody should learn how to code and to understand
how systems work, and it's never been more true than now.

I prepared some  "down the rabbit hole" sessions here. They are not finite on themselves but
they provide pointers to were to know more about fundamentals concepts that would ground
your AI coding skills.

- Going deeper the code gen rabbit hole... Let's build a code assistant ourselves!
    - Show lilcoder, different versions
- Going deeper the web dev rabbit hole
    - Explain how web works, webapps, etc
- Going deeper the LLM rabbit hole
    - CoT
    - RAG and CAG
    - LangChain and LangGraph, Autogen
    - Embeddings and vector databases: LlamaIndex, MongoDB Vector DB, Pinecone, ...
    - Validating outputs of LLMs: https://github.com/confident-ai/deepeval
	- https://github.com/mongodb-developer/GenAI-Showcase


# Tools

Here I keep an updated list of main tools around using AI for coding. I tested
most of them and you'll find my honest opinion during the time I tested.

## Editors / IDE

- Cursor
- Cline
- Windsurf
- OpenHands

## CLI

- Claude Code
- Aider
- Claude Engineer
- Roo

## Webapps
 
- Bolt
- Replt
- Lovable

## Misc

- Task master
- CodeGuide
- repomix

## MCP Servers

# Who to follow

- [@GeoffreyHuntley](https://x.com/GeoffreyHuntley)
- []()

# Acknowledgements

This guide was inspired by the great [llm-course](https://github.com/milanm/DevOps-Roadmap) from Maxime Labonne.

Special thanks to:

* Gabriela Thumé for everything <3
* ChatGPT 4o for generating all the images you see here :-)
