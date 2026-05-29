# Agent Learning Hub

A curated AI Agent learning roadmap for people who want to build useful, reliable agents instead of collecting random links.

This repository maintains only one core showcase: the README. The goal is to organize excellent community shares, official blogs, papers, open-source projects, and real engineering experience into an actionable AI Agent learning todo list that you can follow step-by-step.

## Maintainer

Curated by [Sizhou Chen (陈思州)](https://github.com/jjyaoao) (Datawhale Member) <a href="https://www.xiaohongshu.com/user/profile/67b9cc34000000000e013517" target="_blank"><img alt="Static Badge" src="https://img.shields.io/badge/Rednote-Rednote-e93c49"></a>

## How To Use

- **If you are a beginner**: Follow the "Learning Todo List" from top to bottom, checking off each item as you complete it.
- **If you are already familiar with LLM applications**: Start from Stage 2 or Stage 3, focusing on the agent loop, tool calling, evaluation, and engineering.
- **If you want to build projects**: Go straight to the "Project Ladder" and build a runnable project for each tier.
- **If you are just looking for resources**: Check out "Curated Resources", prioritizing official documentation and classic papers.

## What To Learn Now

The Agent field is evolving rapidly. Instead of outdated "role-playing multi-agent frameworks", it is much more worthwhile to invest in these directions that are closer to real productivity:

| Priority | Learn | Why |
| --- | --- | --- |
| 1 | Claude Code / Codex-style coding agents | Real codebases, shell access, file editing, testing, permissions, and context compression make them the best engineering reference for agents. |
| 2 | Agent harness engineering | A large part of an agent's capability comes from its harness: tool protocols, permissions, state management, feedback loops, replays, CI, and evaluation. |
| 3 | OpenClaw / Hermes-style personal agents | Long-running, local-first, cross-application, memory, skills, and messaging interfaces—more like a "personal operating system". |
| 4 | Skills / MCP / A2A / ACP | Skills manage capability reuse, MCP connects tools, A2A connects agents, and ACP connects the host application. |
| 5 | Evaluation and safety | An agent without evaluation, tracing, and permission boundaries is just a demo. |

It is not recommended to focus heavily on outdated crew/role-play frameworks that have become generic templates. They are worth knowing about but should not be your main focus.

## Learning Todo List

### Stage 0: Understand What An Agent Is

- [ ] Differentiate between chatbots, workflows, single agents, and multi-agents.
- [ ] Understand the fundamental agent loop: observe -> think -> act -> observe.
- [ ] Know when NOT to use an agent: when the task is predictable, the process is stable, or a standard script can solve it, an agent only adds unnecessary uncertainty.
- [ ] Read [Anthropic: Building effective agents](https://www.anthropic.com/engineering/building-effective-agents).
- [ ] Read [OpenAI: A practical guide to building agents](https://openai.com/business/guides-and-resources/a-practical-guide-to-building-ai-agents/).

**Output**: Write a one-page short note answering: "Why does my use case need an agent instead of a standard workflow?"

### Stage 1: Build A Minimal Agent Loop

- [ ] Learn to use an LLM API to complete a standard conversation.
- [ ] Learn to get structured JSON outputs from the model.
- [ ] Learn to define a tool function, e.g., `search`, `calculator`, `read_file`.
- [ ] Learn to parse the model's tool call / function call.
- [ ] Learn to execute the tool and feed the tool's output back to the model.
- [ ] Add maximum step limits, timeouts, and error handling to the agent loop.

**Recommended Reading**:

- [OpenAI Function Calling](https://platform.openai.com/docs/guides/function-calling)
- [Gemini API Function Calling](https://ai.google.dev/gemini-api/docs/function-calling)
- [Claude Tool Use](https://docs.anthropic.com/en/docs/agents-and-tools/tool-use/overview)

**Output**: A minimal agent of 50-150 lines that can select tools, execute them, and return the final answer.

### Stage 2: Learn Tool Use, RAG, And Memory

- [ ] Learn to build Retrieval-Augmented Generation (RAG): chunking, embedding, retrieving, and answering with citations.
- [ ] Learn to integrate search engines, databases, files, browsers, and code execution as tools.
- [ ] Differentiate between short-term context, session memory, and long-term memory.
- [ ] Handle tool failures, empty results, duplicate calls, and hallucinated citations.
- [ ] Make the agent provide sources or evidence in its answers.

**Recommended Reading**:

- [LlamaIndex Agents](https://docs.llamaindex.ai/en/stable/use_cases/agents/)
- [LangChain Docs](https://docs.langchain.com/)
- [Gemini API Code Execution](https://ai.google.dev/gemini-api/docs/code-execution)
- [Model Context Protocol](https://modelcontextprotocol.io/)

**Open-source Projects for Reference**:

| Project | Why It Fits Stage 2 |
| --- | --- |
| [GPT Researcher](https://github.com/assafelovic/gpt-researcher) | The closest finished product to a "research assistant": search, scrape, filter, cite, and generate long reports. |
| [Open Deep Research](https://github.com/langchain-ai/open_deep_research) | A deep research example built with LangGraph, ideal for learning multi-turn search, state management, and cited outputs. |
| [STORM](https://github.com/stanford-oval/storm) | Stanford OVAL's research and writing system, ideal for learning outlining, question asking, and synthesizing multi-perspective information. |
| [Khoj](https://github.com/khoj-ai/khoj) | A personal second brain, ideal for learning local files, web pages, semantic search, and long-term memory. |
| [Onyx](https://github.com/onyx-dot-app/onyx) | Enterprise-grade RAG/search assistant, ideal for learning connectors, hybrid search, permissions, and productionization. |
| [AnythingLLM](https://github.com/Mintplex-Labs/anything-llm) | A local RAG + agents product, great for beginners to quickly understand full application patterns. |
| [RAGFlow](https://github.com/infiniflow/ragflow) | A document-understanding RAG engine, ideal for learning ingestion, chunking, retrieval, and grounded answers. |
| [mem0](https://github.com/mem0ai/mem0) | A memory layer component, ideal for learning how to add long-term memory to agents. |
| [Letta](https://github.com/letta-ai/letta) | A memory/context platform for stateful agents, ideal for learning context management. |

**Output**: A research assistant that automatically searches, filters, summarizes, and outputs citation links when given a topic.

### Stage 3: Study One Modern Agent Harness

Choose one modern agent system to study deeply. The focus here is not "how to call the framework API", but rather how it organizes tools, context, permissions, states, logs, subtasks, and feedback.

| System | Best For | Learn This If You Want To |
| --- | --- | --- |
| [Claude Code Docs](https://code.claude.com/docs/en/overview) | Coding agent product | Learn about real coding agent CLI, tools, permissions, hooks, subagents, and MCP. |
| [learn-claude-code](https://github.com/shareAI-lab/learn-claude-code) | From-scratch agent harness | Replicate a Claude Code-like harness from scratch. |
| [claw0](https://github.com/shareAI-lab/claw0) | From-scratch OpenClaw gateway | Build session, channel, gateway, memory, heartbeat, delivery, resilience, and concurrency step-by-step from a basic agent loop. |
| [hello-agents](https://github.com/datawhalechina/hello-agents) | Chinese agent tutorial | Build agents from scratch, ideal for systematically studying agent principles and practices. |
| [OpenClaw](https://github.com/openclaw/openclaw) | Local-first personal agent | Learn about long-running local agents, skills, message gateways, system tools, and security boundaries. |
| [Hermes Agent](https://github.com/NousResearch/hermes-agent) | Self-hosted growing agent | Learn about long-term memory, skills, toolsets, multi-platform message gateways, and agent migration. |
| [CyberClaw](https://github.com/ttguy0707/CyberClaw) | Transparent agent architecture | Learn about full-behavior auditing, two-stage secure execution, dual-watermark memory, and heartbeat tasks. |
| [LangGraph](https://langchain-ai.github.io/langgraph/) | Stateful graph orchestration | Learn stateful graphs, human-in-the-loop/interruptibility, and controllable orchestration. |

- [ ] Read and understand the directory structure of an agent harness.
- [ ] Find its agent loop, tool registry, permission gate, session store, and context compaction mechanism.
- [ ] Run its minimal example and add one of your own tools.
- [ ] Observe a complete execution trace and explain why each step occurred.
- [ ] Implement the same task using a "bare agent loop" vs. "harness" and compare the differences.

**Output**: A debuggable agent harness demo containing a README, running steps, sample inputs/outputs, and failure logs.

### Stage 4: Multi-Agent Is Coordination, Not Magic

- [ ] Understand common roles like planner, executor, reviewer, critic, and router.
- [ ] Learn to manage multi-agents using a supervisor or a state graph, instead of letting agents chat aimlessly.
- [ ] Learn to define each agent's responsibility boundaries, input/output schemas, and stopping conditions.
- [ ] Learn to handle infinite loops, consensus conflicts, task drift, and context inflation.
- [ ] Learn to judge when a single agent is a better fit than multi-agents.

**Recommended Reading**:

- [Claude Code Subagents](https://code.claude.com/docs/en/sub-agents)
- [Claude Code Hooks](https://code.claude.com/docs/en/hooks)
- [Google Agent Development Kit](https://google.github.io/adk-docs/)
- [Agent2Agent Protocol](https://google-a2a.github.io/A2A/specification/)
- [Agent Client Protocol](https://agentclientprotocol.com/)

**Output**: A small multi-agent system, such as a pipeline of `research -> write -> review -> revise`.

### Stage 5: Learn Skills, Protocols, And Capability Packaging

A modern agent's capability comes not only from models and tools but also from reusable skills. A good skill is like a mini-operation manual: it tells the agent when to use it, how to use it, what scripts/resources are needed, and how to verify the results.

- [ ] Understand the difference between a Skill and a Tool: a tool is a callable interface, while a skill is reusable process knowledge.
- [ ] Understand the difference between a Skill and a Prompt: a prompt is usually a one-off instruction, while a skill is a discoverable, versionable, and distributable capability package.
- [ ] Understand the difference between a Skill and MCP: MCP connects external tools/data sources, while a skill teaches the agent how to complete a specific type of task.
- [ ] Read Claude Code Skills' file structure and triggering mechanism.
- [ ] Read OpenClaw Skills' loading, scoping, and security boundaries.
- [ ] Write a minimal `SKILL.md` containing name, description, when to use, steps, and acceptance criteria.
- [ ] Add a script or template file to the skill, specifying when the agent needs to load it.
- [ ] Write a smoke test for the skill to verify if it actually improves task success rates.

**Recommended Reading**:

- [Claude Code Skills](https://code.claude.com/docs/en/skills)
- [Claude Agent Skills](https://docs.claude.com/en/docs/agents-and-tools/agent-skills)
- [Claude Code Agent SDK Skills](https://code.claude.com/docs/en/agent-sdk/skills)
- [OpenClaw Skills](https://github.com/openclaw/openclaw/blob/main/docs/tools/skills.md)
- [Model Context Protocol](https://modelcontextprotocol.io/)
- [Agent2Agent Protocol](https://google-a2a.github.io/A2A/specification/)
- [Agent Client Protocol](https://agentclientprotocol.com/)

**Output**: A reusable skill, such as `code-review`, `research-report`, `migration-helper`, `pdf-extraction`, or `release-note-writer`.

### Stage 6: Browser And Computer-Use Agents

- [ ] Understand the difference between a browser agent and a standard API tool.
- [ ] Learn to use Playwright or browser-use to observe web pages and execute clicks/inputs.
- [ ] Apply security constraints to browser operations: do not log into sensitive accounts, do not exceed permissions, and do not bypass platform rules.
- [ ] Learn to handle dynamic page changes, popups, loading failures, and element location failures.
- [ ] Record screenshots, DOM trees, and action logs for easy debugging and post-mortem analysis.

**Recommended Reading**:

- [Claude Computer Use](https://docs.anthropic.com/en/docs/agents-and-tools/tool-use/computer-use-tool)
- [browser-use](https://github.com/browser-use/browser-use)
- [WebArena](https://arxiv.org/abs/2307.13854)
- [VisualWebArena](https://arxiv.org/abs/2401.13649)

**Output**: A browser agent that operates exclusively on public web pages, such as opening websites, extracting information, and generating summaries.

### Stage 7: Evaluation, Observability, And Safety

- [ ] Prepare a fixed benchmark dataset for your agent rather than just relying on ad-hoc demos.
- [ ] Record key metrics: success rate, failure reasons, number of tool calls, cost, and latency.
- [ ] Analyze execution traces to locate whether a failure occurred in prompt design, tool execution, retrieval, model inference, or state management.
- [ ] Add human-in-the-loop approval for high-risk tools (e.g., sending emails, deleting files, making payments, or publishing content).
- [ ] Understand security risks like prompt injection, data exfiltration, and tool abuse.
- [ ] Implement regression testing to prevent capability degradation after modifying prompts or tools.

**Recommended Reading**:

- [OpenAI Evals](https://platform.openai.com/docs/guides/evals)
- [OpenAI Agent platform](https://openai.com/agent-platform/)
- [LangSmith](https://docs.smith.langchain.com/)
- [AgentBench](https://arxiv.org/abs/2308.03688)
- [SWE-bench](https://arxiv.org/abs/2310.06770)

**Output**: An agent evaluation table containing at least 20 tasks, expected results, actual results, and failure classification.

### Stage 8: Ship A Real Agent

- [ ] Define clear target users, specific tasks, and measurable success criteria.
- [ ] Implement logging, tracing, error retries, timeouts, and cost caps.
- [ ] Incorporate permission boundaries and human-in-the-loop confirmation.
- [ ] Provide deployment options: CLI, Web app, Slack bot, GitHub Action, or background tasks.
- [ ] Write a README explaining how to run, configure API keys, extend tools, and key limitations.

**Output**: A runnable agent project that others can easily clone and execute.

## Project Ladder

| Level | Project | What You Learn |
| --- | --- | --- |
| 1 | Calculator Agent | Minimal tool call loop |
| 2 | Web Research Agent | Search, filtering, citations, and summarization |
| 3 | PDF QA Agent | RAG, chunking, retrieval, and citation |
| 4 | Coding Review Agent | Diff reading, risk prioritization, and testing advice |
| 5 | Browser Agent | Page observation, clicking, extraction, and failure recovery |
| 6 | Claude Code-like Nano Agent | Shell access, file editing, permissions, sessions, and compaction |
| 7 | OpenClaw-like Gateway | Channel, routing, session, memory, heartbeat, and delivery |
| 8 | Reusable Skill Pack | SKILL.md, scripts, templates, trigger conditions, and smoke tests |
| 9 | Multi-Agent Writer | Planner, writer, and reviewer collaboration |
| 10 | Personal Agent | OpenClaw/Hermes-style memory, skills, and messaging interfaces |
| 11 | Production Harness | Evals, tracing, permissions, CI, runners, and replay |

## Curated Resources

### Official Guides And Blogs

| Resource | Why It Matters |
| --- | --- |
| [Anthropic: Building effective agents](https://www.anthropic.com/engineering/building-effective-agents) | Essential reading for agent design, explaining the boundaries between workflows and agents. |
| [Claude Code Overview](https://code.claude.com/docs/en/overview) | Documentation entry point for one of the most prominent coding agents today. |
| [Claude Code Subagents](https://code.claude.com/docs/en/sub-agents) | Learn task decomposition, context isolation, and specialized sub-agents. |
| [Claude Code Hooks](https://code.claude.com/docs/en/hooks) | Learn how to intercept, validate, and extend agent behaviors. |
| [Claude Code GitHub Actions](https://docs.claude.com/en/docs/claude-code/github-actions) | Learn how coding agents integrate into PR and issue workflows. |
| [Claude Code Advanced Patterns](https://resources.anthropic.com/hubfs/Claude%20Code%20Advanced%20Patterns_%20Subagents%2C%20MCP%2C%20and%20Scaling%20to%20Real%20Codebases.pdf) | Official Anthropic materials covering sub-agents, MCP, and scaling to real codebases. |
| [OpenAI: A practical guide to building agents](https://openai.com/business/guides-and-resources/a-practical-guide-to-building-ai-agents/) | A practical guide to building agents for product and engineering teams. |
| [OpenAI: New tools for building agents](https://openai.com/index/new-tools-for-building-agents/) | Official introduction to the Responses API, Agents SDK, tools, and tracing. |
| [OpenAI Agents SDK](https://platform.openai.com/docs/guides/agents-sdk/) | Entry point for native OpenAI agent development. |
| [Claude Tool Use](https://docs.anthropic.com/en/docs/agents-and-tools/tool-use/overview) | Understanding the Claude tool use / function calling mechanism. |
| [Claude Computer Use](https://docs.anthropic.com/en/docs/agents-and-tools/tool-use/computer-use-tool) | Official reference for computer use and GUI-operating agents. |
| [Gemini Function Calling](https://ai.google.dev/gemini-api/docs/function-calling) | Gemini tool calling and function calling documentation. |
| [Gemini Code Execution](https://ai.google.dev/gemini-api/docs/code-execution) | Native code execution environment in Gemini API. |
| [Google Agent Development Kit](https://google.github.io/adk-docs/) | Google's framework and SDK for agent development. |
| [Model Context Protocol](https://modelcontextprotocol.io/) | Standard protocol for connecting agents with tools, data sources, and servers. |

### Project Map

Don't just browse repositories by GitHub stars; we recommend categorization based on your learning goals:

| Layer | Study These | Learn |
| --- | --- | --- |
| Build From Scratch | [learn-claude-code](https://github.com/shareAI-lab/learn-claude-code), [claw0](https://github.com/shareAI-lab/claw0), [hello-agents](https://github.com/datawhalechina/hello-agents) | Agent loops, tool registries, sessions, context compaction, gateways, traces, and sub-agents. |
| Personal / Always-On Agents | [OpenClaw](https://github.com/openclaw/openclaw), [Hermes Agent](https://github.com/NousResearch/hermes-agent), [CyberClaw](https://github.com/ttguy0707/CyberClaw) | Long-running tasks, skills, memory systems, message gateways, permissions, and security auditing. |
| Coding Agents | [Claude Code](https://code.claude.com/docs/en/overview), [OpenAI Codex](https://github.com/openai/codex), [OpenCode](https://github.com/opencode-ai/opencode), [OpenHands](https://github.com/All-Hands-AI/OpenHands), [SWE-agent](https://github.com/SWE-agent/SWE-agent), [pi](https://github.com/earendil-works/pi) | Real-world codebase editing, shell execution, testing, sandboxing, and PR workflows. |
| Deep Research / RAG Agents | [DeerFlow](https://github.com/bytedance/deer-flow), [LlamaIndex](https://docs.llamaindex.ai/) | Web search, scraping, retrieval, reranking, citation handling, and report generation. |
| Tutorial Encyclopedias | [GenAI_Agents](https://github.com/NirDiamant/GenAI_Agents), [hello-agents](https://github.com/datawhalechina/hello-agents), [smolagents](https://github.com/huggingface/smolagents), [agents-towards-production](https://github.com/NirDiamant/agents-towards-production) | Horizontal comparison of ReAct, Plan-and-Execute, Multi-Agent, and production engineering patterns. |
| Browser / Multimodal Agents | [browser-use](https://github.com/browser-use/browser-use), [UI-TARS-desktop](https://github.com/bytedance/UI-TARS-desktop) | Browser/desktop GUI manipulation, visual grounding, action spaces, and failure recovery. |

### Skills, Protocols, And Tooling

| Concept | Learn From | What It Solves |
| --- | --- | --- |
| Skills | [Claude Code Skills](https://code.claude.com/docs/en/skills), [OpenClaw Skills](https://github.com/openclaw/openclaw/blob/main/docs/tools/skills.md) | Packages process knowledge, scripts, templates, and acceptance criteria for a type of task into reusable capabilities. |
| MCP | [Model Context Protocol](https://modelcontextprotocol.io/) | Standardizes how agents connect to external tools, data sources, and services. |
| A2A | [Agent2Agent Protocol](https://google-a2a.github.io/A2A/specification/) | Enables different agents to discover, communicate, and collaborate with each other. |
| ACP | [Agent Client Protocol](https://agentclientprotocol.com/) | Establishes a unified interface between editors, terminals, IDEs, host applications, and agents. |
| Skill Quality | [SWE-Skills-Bench](https://arxiv.org/abs/2603.15401), [Agent Skills analysis](https://arxiv.org/abs/2602.08004) | Evaluates whether skills actually improve success rates instead of just adding prompt noise. |

### Modern Agent Systems

| System | Why It Is Useful |
| --- | --- |
| [Claude Code](https://code.claude.com/docs/en/overview) | Study the productized form of coding agents: shell access, file operations, permissions, hooks, subagents, and MCP. |
| [learn-claude-code](https://github.com/shareAI-lab/learn-claude-code) | Build a Claude Code-like nano agent from scratch, perfect for understanding harness engineering. |
| [claw0](https://github.com/shareAI-lab/claw0) | Build an OpenClaw-like agent gateway from scratch, covering channel, routing, session, memory, delivery, and concurrency. |
| [hello-agents](https://github.com/datawhalechina/hello-agents) | A systematic Chinese agent tutorial series, suitable for building up agent theory and practice from absolute zero. |
| [OpenClaw](https://github.com/openclaw/openclaw) | A local-first personal agent, ideal for studying long-running agents and system-level tool call boundaries. |
| [Hermes Agent](https://github.com/NousResearch/hermes-agent) | Self-hosted growing agent, featuring long-term memory, skills, toolsets, and multi-platform message routing. |
| [CyberClaw](https://github.com/ttguy0707/CyberClaw) | A transparent and controllable agent architecture, ideal for auditing, two-stage execution, and safety sandboxes. |
| [DeerFlow](https://github.com/bytedance/deer-flow) | ByteDance's open-source long-horizon SuperAgent harness, ideal for studying Deep Research, report generation, slides, web, image, and video generation. |
| [smolagents](https://github.com/huggingface/smolagents) | Hugging Face's lightweight agent framework; the CodeAgent paradigm is highly worth studying. |
| [LangGraph](https://langchain-ai.github.io/langgraph/) | Stateful graphs and controllable agent orchestration; still highly relevant as a foundational engineering framework. |
| [Qwen-Agent](https://github.com/QwenLM/Qwen-Agent) | Agent framework within the Qwen model ecosystem, covering tool calling, RAG, and MCP. |
| [Pydantic AI](https://pydantic.dev/docs/ai/core-concepts/agent/) | Type-safe and structured output agent framework, excellent for building production-grade Python agents. |
| [pi](https://github.com/earendil-works/pi) | AI agent toolkit (TypeScript) featuring a coding agent CLI, core runtime, unified multi-provider LLM API, and a TUI library, supporting self-expansion. |

### Legacy Or Optional Frameworks

These projects still hold reference value but are not recommended as the primary learning path.

| Framework | Note |
| --- | --- |
| [CrewAI](https://docs.crewai.com/) | Good to learn the role/task/crew abstractions, but many scenarios are now better covered by stronger coding agents or harness setups. |
| [AutoGen](https://microsoft.github.io/autogen/) | A classic project for multi-agent conversational frameworks; great for understanding agent history and papers, but avoid over-investing. |
| [LangChain Agents](https://docs.langchain.com/) | The ecosystem is still important, but we suggest shifting focus toward LangGraph and concrete engineering design patterns. |

### Papers

| Paper | Topic |
| --- | --- |
| [ReAct](https://arxiv.org/abs/2210.03629) | The foundational paradigm combining reasoning and acting. |
| [Toolformer](https://arxiv.org/abs/2302.04761) | Teaching models when and how to call external APIs/tools. |
| [Reflexion](https://arxiv.org/abs/2303.11366) | Self-reflection and linguistic feedback for agent reinforcement. |
| [Generative Agents](https://arxiv.org/abs/2304.03442) | Interactive agents driven by memory, reflection, and planning. |
| [Voyager](https://arxiv.org/abs/2305.16291) | An open-ended, lifelong learning agent in Minecraft. |
| [AutoGen](https://arxiv.org/abs/2308.08155) | Multi-agent conversational frameworks. |
| [AgentBench](https://arxiv.org/abs/2308.03688) | Evaluating LLMs as agents in multi-turn interactive environments. |
| [WebArena](https://arxiv.org/abs/2307.13854) | A realistic web-based agent benchmark. |
| [SWE-bench](https://arxiv.org/abs/2310.06770) | Resolving real-world software engineering issues from GitHub. |
| [SWE-agent](https://arxiv.org/abs/2405.15793) | Agent-computer interfaces tailored for software engineering. |
| [Dive into Claude Code](https://arxiv.org/abs/2604.14228) | An architectural analysis of coding agent harnesses, permissions, compression, and extension mechanisms. |
| [AI Harness Engineering](https://arxiv.org/abs/2605.13357) | Studying the agent harness as the core driver of agent performance and capability. |
| [Configuring Agentic AI Coding Tools](https://arxiv.org/abs/2602.14690) | Analysis of configuration mechanisms in Claude Code, Codex, Gemini, Cursor, etc. |
| [Your Agent, Their Asset](https://arxiv.org/abs/2604.04759) | Analyzing real-world security vulnerabilities and risks in local agents like OpenClaw. |

### GitHub Repositories

| Repo | Why It Is Useful |
| --- | --- |
| [datawhalechina/hello-agents](https://github.com/datawhalechina/hello-agents) | A systematic Chinese agent tutorial series, perfect for learning agent theory and practice from absolute zero. |
| [shareAI-lab/learn-claude-code](https://github.com/shareAI-lab/learn-claude-code) | "Bash is all you need" style tutorial to replicate a Claude Code-like agent harness from scratch. |
| [shareAI-lab/claw0](https://github.com/shareAI-lab/claw0) | Learn an OpenClaw-like gateway step-by-step from agent loops to concurrency over 10 gradual chapters. |
| [openclaw/openclaw](https://github.com/openclaw/openclaw) | Study local personal agents, skills, long-running tasks, system tools, and permission boundaries. |
| [NousResearch/hermes-agent](https://github.com/NousResearch/hermes-agent) | Study self-hosted agents, long-term memory, skills, toolsets, and multi-platform message gateways. |
| [ttguy0707/CyberClaw](https://github.com/ttguy0707/CyberClaw) | Study transparent agents, security auditing, two-stage execution, dual-watermark memory, and heartbeat tasks. |
| [bytedance/deer-flow](https://github.com/bytedance/deer-flow) | Deep Research / long-horizon agent framework for learning search, report generation, sandboxes, memory, skills, subagents, and message gateways. |
| [NirDiamant/GenAI_Agents](https://github.com/NirDiamant/GenAI_Agents) | Comprehensive tutorial repository, suitable for comparing ReAct, Plan-and-Execute, Multi-Agent, and other paradigms. |
| [NirDiamant/agents-towards-production](https://github.com/NirDiamant/agents-towards-production) | Production-grade agent tutorial repository, excellent for building production components. |
| [huggingface/smolagents](https://github.com/huggingface/smolagents) | A lightweight CodeAgent-style framework, ideal for studying "agent writes code to act" paradigms. |
| [openai/codex](https://github.com/openai/codex) | OpenAI's open-source coding agent CLI, ideal for studying sandboxing, approvals, and CLI product design. |
| [opencode-ai/opencode](https://github.com/opencode-ai/opencode) | Terminal-first open-source coding agent, perfect for comparing against Claude Code or Codex. |
| [langchain-ai/langgraph](https://github.com/langchain-ai/langgraph) | Stateful graphs and controllable agent orchestration. |
| [openai/openai-agents-python](https://github.com/openai/openai-agents-python) | OpenAI Agents SDK for Python. |
| [QwenLM/Qwen-Agent](https://github.com/QwenLM/Qwen-Agent) | Agent framework within the Qwen model ecosystem. |
| [browser-use/browser-use](https://github.com/browser-use/browser-use) | Hands-on browser agent implementation. |
| [bytedance/UI-TARS-desktop](https://github.com/bytedance/UI-TARS-desktop) | Multimodal desktop agent stack for visual-based GUI operations. |
| [SWE-agent/SWE-agent](https://github.com/SWE-agent/SWE-agent) | An open-source software engineering agent harness. |
| [All-Hands-AI/OpenHands](https://github.com/All-Hands-AI/OpenHands) | A widely-used open-source coding agent platform. |
| [microsoft/ai-agents-for-beginners](https://github.com/microsoft/ai-agents-for-beginners) | A structured curriculum for beginners. |
| [jjyaoao/HelloAgents](https://github.com/jjyaoao/HelloAgents) | A production-grade multi-agent framework based on the native OpenAI API, covering ToolResponse, context engineering, session persistence, sub-agents, and trace logging. |
| [earendil-works/pi](https://github.com/earendil-works/pi) | AI agent toolkit (TypeScript) featuring coding agent CLI, core runtime, unified multi-provider LLM API, and a TUI library, supporting Slack bots and vLLM pods. |

### Thoughtful Blogs

| Blog | Why It Is Useful |
| --- | --- |
| [Lilian Weng: LLM Powered Autonomous Agents](https://lilianweng.github.io/posts/2023-06-23-agent/) | A classic blog post systematically organizing agent architectures, memory, planning, and tool use. |
| [Simon Willison: AI/LLM writing](https://simonwillison.net/tags/llms/) | Highly pragmatic LLM engineering observations, great for building engineering intuition. |
| [LangChain Blog](https://blog.langchain.com/) | Engineering practices on LangGraph, LangSmith, and agents. |
| [Google Developers Blog: ADK](https://developers.googleblog.com/agent-development-kit-easy-to-build-multi-agent-applications/) | Official launch announcement and overview for Google ADK. |

### Claude Code Study Path

Claude Code is one of the most prominent coding agents worth dissecting today. We recommend studying it in the following order: "Official Docs -> Replicated Projects -> Architecture Analysis -> Engineering Comparison":

- Read the official documentation to understand hooks, sub-agents, MCP, GitHub Actions, and permissions.
- Read published analysis papers to abstract the design space of agent harnesses.
- Follow the [learn-claude-code](https://github.com/shareAI-lab/learn-claude-code) repository to replicate core mechanisms from scratch.
- Compare with open-source projects like [hello-agents](https://github.com/datawhalechina/hello-agents), [OpenClaw](https://github.com/openclaw/openclaw), and [Hermes Agent](https://github.com/NousResearch/hermes-agent) to study production engineering.

| Resource | Focus |
| --- | --- |
| [Claude Code Common Workflows](https://code.claude.com/docs/en/tutorials) | Official workflow tutorial, suitable for daily usage and team collaboration. |
| [Claude Code Overview](https://code.claude.com/docs/en/overview) | Official entry point to understand product capabilities and command-line interactions. |
| [learn-claude-code](https://github.com/shareAI-lab/learn-claude-code) | Replicate a Claude Code-like agent from scratch, perfect for learning a minimal harness implementation. |
| [Claude Code Architecture Review](https://claudecoding.dev/) | Architectural breakdown of Claude Code, ideal for understanding the design thoughts block-by-block. |
| [Claude Code Analysis Map](https://code.claudecn.com/) | A mapping approach to dissecting the agent loop, tools, commands, and multi-agent coordination. |
| [Dive into Claude Code](https://arxiv.org/abs/2604.14228) | A research-centric paper summarizing Claude Code's design space and agent harness patterns. |
| [Agentic Education](https://arxiv.org/abs/2604.17460) | An interactive curriculum design for learning Claude Code by using Claude Code itself. |

## Learning Principles

- Build first, then read deeper.
- Prefer small reliable agents over impressive demos.
- Use tools with strict schemas.
- Add evals before you add more agents.
- Trace every important run.
- Treat multi-agent as a coordination problem.
- Keep humans in the loop for risky actions.
- Respect platform rules, copyrights, and data access boundaries.

## Contributing

Good contributions are welcome. Please prefer:

- official docs and official engineering blogs;
- high-quality papers and benchmarks;
- open-source repositories with runnable code;
- serious technical blogs with original insight;
- small projects that help learners practice one specific skill.

Please avoid:

- copied platform posts;
- course ads without substantial content;
- private or paywalled material;
- scraping-oriented content that bypasses platform rules.
