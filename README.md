<div align="center">
<img src="https://i.imgur.com/v0Tx6am.png" alt="AI Code Guide">
  <p align="center">
    𝕏 <a href="https://x.com/aut0mata">Follow me on X</a> • 
    🤗 <a href="https://void.cc">My personal website</a> • 
    💻 <a href="https://github.com/automata">My GitHub</a>
  </p>
</div>
<br/>

> Everything you wanted to know about using AI to help you code and/or to code
> for you.

<div align="center" style="font-size: 30px">
  <a href="#vibe">TL;DR Just show me how to vibe code 😎!</a>
</div>

## Introduction

It's April of 2025, I just arrived in the sunny Munich and I decided to open my laptop,
pop a *Club Mate* and dump
everything I have been researching around **AI to help on code generation**.

The way we interact with computers and code them is
changing. And it's a profound change: on the tools we use, the
way we code and think about software products and systems.

And it's changing super fast! New LLM models are being released every week. New
tools, new editors, new "vibe coding" practices, new protocols, MCP, A2A, SLOP,
... And it's really hard to keep track of all that. Everything is
scattered in different places, websites, repos, YouTube videos, etc.

That's why I decided to
write this guide. It's my humble attempt to put everything together and present
you the practices and tools around **AI coding** or **AI assisted code generation**, all in one
place, with no fluf, in an accessible form.

- **If you're a coder but is not using AI code assistants yet**, this guide is for you: it presents the most
  recent tools and good practices to make the most of them to help on your daily
  jobs. Either having AI as your copilot or being the copilot for an AI agent.

- **If you never coded before but you're interested in this new "vibe coding"
  thing to build your own SaaS and other software products**, this guide is
  definetely for you: I'll try to do my best to remove obscurity and leave you
  with what's required to start your journey, but being super critic about what
  is really important and what's "just hype".

Cool, let's start!

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
neurosymbolic hybrid approaches starting to show up. AI coding is also a
practice: if you're using Cursor and tab-tab-tab your way to get completions,
you're "AI coding"; if you're full on using Cursor's agent mode, you're also "AI
coding". In summary: it's any way to use an AI models to help you to generate
code. Generally you have people who already know how to code in this group.

Vibe coding is AI coding cranked up :-) Here you don't care much about the code
being generated, you just give a prompt and expect the AI to code everything
for you. The term was created by Karpathy in 2024 and it's getting pretty
popular. IMHO it's helping to democratize coding for everyone that never
thought about coding before!

So, in summary, no matter if you're using AI to discuss your software ideas or
to help on coding only parts of your already existing code base, or if you're
full on vibe coding, you're using AI to help you generate code. Let's call it
AI coding and move on.

## How can I use it?

You can use AI coding in many different ways, but in summary:

- AI is your copilot: you use AI models to augment yourself, to boost your
  productivity. Either by firing up ChatGPT to help you on brainstroming ideas
  for your SaaS; or using Cursor to autocomplete your docstrings. There are
  many gains here, specially for creative exploration and to automate boring
  parts of your work.

- AI is the pilot: here you are the copilot. This is where the "vibe coding"
  happens. You turn on the Cursor Agent YOLO mode and trust everything the
  agents do to generate your code. Really powerful way to automate yourself,
  but demands some good practices on how to design systems, tame the agents and
  jumping in on a spaghetti of code you actually don't know about, specially to
  solve errors.

IMHO you should learn and practice both!

# 🗺️ The Roadmap

## How I start?

- If you don't know how to code and want to play with it, I recommend starting
with some web-based tool like [Bolt](https://bolt.new), [Replit](https://replit.com)
or [Lovable](https://lovable.dev).

- If you already know how to code, install [Cursor](https://cursor.com/) or [Windsurf](https://windsurf.com/).
You can start with the
free plan and then upgrade to $20 monthly plan. I pay for Cursor, it's pretty good and cheap,
given you'll have tons of tokens to use on most recent LLM models out there.

- If you want a more open source alternative, try [OpenHands](https://github.com/All-Hands-AI/OpenHands).
You run it as a Docker container
that exposes a webapp. You'll have to create an [Anthropic API account](https://console.anthropic.com/) to get access to an API key,
or use some LLM available in [OpenRouter](https://openrouter.ai/).

- If you already know how to code and is a terminal maniac like me, check [aider](https://aider.chat/) and [Claude Code](https://docs.anthropic.com/en/docs/agents-and-tools/claude-code/overview).
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

## How I prompt for coding? AKA How I vibe code?<a id='vibe'></a>

After you installed and played with those tools a bit, you'll notice they will
hallucinate, enter in endless cycles of trying to fix a possible error, etc.
It's important to know how to prompt well. Some tips:

- Do not ask everything in one prompt. Only prompting "hey, building me an app
  to for my pet store" doesn't help a software engineer and much less an AI :-)
  Understand your project, brainstorm first with an LLM, create a PRD
  (requirements), make a plan and split them in tasks.
- Give it details. If you know what you want, say it. If you know which
  programming language you want, which tech stack, what type of audience, add
  it to your prompt.
- Create a PRD first. Check the session above about it, it makes a world of
  difference.
- Break you project into tasks and subtasks.
- Try different models for different goals.
- Try different models to confirm and validate output of other models.
- LLMs are "yes machines", so be critic.

Here is a method/procedure/strategy/workflow that generally works well:

1. Use `ChatGPT 4.5`, `4o` or `o3` with the following prompt:

```
You're a senior software engineer. We're going to build the PRD of a project
together.

VERY IMPORTANT:
- Ask one question at a time
- Each question should be based on previous answers
- Go deeper on every important detail required

IDEA:
<paste here your idea>

```

2. You're going to enter in a loop of questions/answers for a few minutes. Try
   to answer as much as you can with as much details as possible. When finished
   (or when you decide it's enough), send this prompt to guide the model to
   compile it as a PRD:

```
Compile those findings into a PRD. Use markdown format. It should contain the
following sections:

- Project overview
- Core requirements
- Core features
- Core components
- App/user flow
- Techstack
- Implementation plan
```

3. Copy and save this file into a `docs/specs.md` inside your project folder
4. Now let's create the task list for your project. Ask the following:
```
Based on the generated PRD, create a detailed step-by-step plan to build this project.
Then break it down into small tasks that build on each other.
Based on those tasks, break them into smaller subtasks.
Make sure the steps are small enough to be implemented in a step but big enough
to finish the project with success.
Use best practices of software development and project management, no big
complexity jumps. Wire tasks into others, creating a dependency list. There
should be no orphan tasks.

VERY IMPORTANT:
- Use markdown
- Each task and subtask should be a checklist item
- Provide context enough per task so a developer should be able to implement it
- Each task should have a number id
- Each task should list dependendent task ids
```
5. Save this as `docs/todo.md` inside your project folder

This should give you the PRD and the tasks lists to build your project! With
that in hands, you can open your Cursor (or other AI code editor), point it to
those files and ask:

```
You're a senior software engineer. Study @docs/specs.md and implement what's
still missing in @docs/todo.md. Implement each task each time and respect task
and subtask dependencies. Once finished a task, check it in the list and move
to the next.
```

Enable YOLO mode the first time Cursor Agent executes a command and then keep
accepting or asking `continue` in the prompt.

In the case of Cursor, sometimes the LLM will reach some limits and ask for
retry. Just do it and continue. Yep, you're vibe coding :-)

📚 Resources:

- [You are using Cursor AI incorrectly...](https://ghuntley.com/stdlib/) by Geoffrey Huntley:
here Geoff introduces his
idea of using a stdlib of Cursor rules
- [From Design doc to code: the Groundhog AI coding assistant (and new Cursor vibecoding meta)](https://ghuntley.com/specs/) by Geoffrey Huntley:
part 2 of the previous post, where Geoff suggests to use LLMs to build specs
(PRD) and Cursor rules automatically
- [My LLM codegen workflow atm](https://harper.blog/2025/02/16/my-llm-codegen-workflow-atm/)

## Which LLM model I should use?

LLMs are trained and finetuned with different goals, here is a comprehensive
list of goals/use you might have and which model to use it for:

| Goal                 | Models                            |
|----------------------|-----------------------------------|
| Brainstorming        | GPT 4.5, 4o, o3                   |
| PRD creation         | GPT o1-pro                        |
| Task split           | GPT o1-pro                        |
| Coding (Agent mode)  | Gemini 2.5 Pro, Claude 3.7 Sonnet |
| Coding (Chat)        | Claude 3.5 Sonnet                 |

## What are Cursor rules?

*TODO*

## How I avoid hallucinations? What is a PRD?

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

Check <a href="#vibe">here</a> how to use a LLM to create one for you.

## How I start my project?

### Webapp

*TODO: Start a React or Nextjs  project with a starter kit*

### Backend

*TODO: Start a Python FastAPI project with uv*

## How I deal with errors and bugs?

One thing you must know about coding and softwares in general: they will fail.
No matter what you try to prevent that, it will happen. So let's first embrace
that and be friends with errors and bugs.

The first strategy here is to mimic what SWE do: see what the
interpreter/compiler gave to you as an error message and try to understand it. 

Another great idea is to add MCP tools great for debugging like
[BrowserTools](https://browsertools.agentdesk.ai/).

## What's MCP, SLOP and A2A and how can I benefit from it?


📚 Resources:

- https://mcpslop.com/

## Creating my own MCP server

*TODO*

## Start from scratch or with a boilerplate?

Generally LLMs do better starting fresh. But you can also start with a
boilerplate and add rules in the context window to make it sure it will respect
your starter kit.

Another great idea is to index your project (that you just created with the
starter kit) using Cursor's own indexing feature, or using some tool like
repomix 

## Greenfield/clean state/fresh project vs existing codebase

If you have an existing codebase, a good idea is to use repomix or llmtxt to
pack it into the context window.

Another great tip is to prompt for changes at task level and not in project
level. For instance, focus in one feature you want to implement and ask Cursor
Agent to implement it. Give a mini-PRD for the specific feature. Imagine that
you're guiding a junior developer to work in a specific GH ticket :-)

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

- [Cursor](https://cursor.com)
  - The go-to AI editor, the one I use daily in my daily job and side projects
  - Pricing: Free and then starts with $20
- [Windsurf](https://windsurf.com)
- [Cline](https://cline.bot/)
- [OpenHands](https://github.com/All-Hands-AI/OpenHands)
- [Devin](https://devin.ai)
- [VSCode + GitHub Copilot](https://code.visualstudio.com/docs/copilot/setup)

## CLI

- [Claude Code](https://github.com/anthropics/claude-code)
- [Aider](http://aider.chat/)
- [Claude Engineer](https://github.com/Doriandarko/claude-engineer)
- [Roo Code](https://github.com/RooVetGit/Roo-Code)

## Webapps

- [Bolt](https://bolt.new)
- [Replit](https://replit.com)
- [Lovable](https://lovable.dev)

## Helpful Tools

- [Claude Task master](https://github.com/eyaltoledano/claude-task-master)
- [CodeGuide](https://www.codeguide.dev/)
- [repomix](https://repomix.com/)

## MCP Servers

# Who to follow

Some super interesting people implementing AI coding models/tools or using it
on their own projects.

- [@GeoffreyHuntley](https://x.com/GeoffreyHuntley)
- [@aut0mata](https://x.com/aut0mata)
- [@NathanWilbanks_](https://x.com/NathanWilbanks_)
- [@skcd42](https://x.com/skcd42)
- [@xingyaow_](https://x.com/xingyaow_)
- [@_catwu](https://x.com/_catwu)
- [@EyalToledano](https://x.com/EyalToledano)
- [@skirano](https://x.com/skirano)
- [@beyang](https://x.com/beyang)

# Acknowledgements

This guide was inspired by the great [llm-course](https://github.com/milanm/DevOps-Roadmap) from Maxime Labonne.

Special thanks to:

* Gabriela Thumé for everything <3
* ChatGPT 4o for generating all the images you see here :-)

# License

MIT
