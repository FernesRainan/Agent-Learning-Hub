# Agent Learning Hub

A curated AI Agent learning roadmap for people who want to build useful, reliable agents instead of collecting random links.

这个仓库只维护一个核心展示面：README。目标是把社区里优秀分享、官方博客、论文、开源项目和真实工程经验，整理成一份可以照着执行的 AI Agent 学习 todo list。

> 说明：小红书、知乎、B 站等社区内容只作为路线设计的灵感来源。本仓库不收录小红书帖子正文，也不做平台内容搬运。

## How To Use

- 如果你是新手：按「Learning Todo List」从上到下做，每完成一项就打勾。
- 如果你已经会 LLM 应用：从 Stage 2 或 Stage 3 开始，重点补 Agent loop、工具调用、评测和工程化。
- 如果你想做项目：直接看「Project Ladder」，每一档做一个可运行作品。
- 如果你只想找资料：看「Curated Resources」，优先读官方文档和经典论文。

## Learning Todo List

### Stage 0: Understand What An Agent Is

- [ ] 区分 chatbot、workflow、agent、multi-agent。
- [ ] 理解 agent 的基本循环：observe -> think -> act -> observe。
- [ ] 明白什么时候不该用 agent：任务可预测、流程稳定、普通脚本能解决时，agent 反而增加不确定性。
- [ ] 读完 [Anthropic: Building effective agents](https://www.anthropic.com/engineering/building-effective-agents)。
- [ ] 读完 [OpenAI: A practical guide to building agents](https://openai.com/business/guides-and-resources/a-practical-guide-to-building-ai-agents/)。

产出：写一页短笔记，回答「我的场景为什么需要 agent，而不是普通 workflow？」

### Stage 1: Build A Minimal Agent Loop

- [ ] 会用一个 LLM API 完成普通对话。
- [ ] 会让模型输出结构化 JSON。
- [ ] 会定义一个工具函数，例如 search、calculator、read_file。
- [ ] 会解析模型的 tool call / function call。
- [ ] 会执行工具，并把工具结果喂回模型。
- [ ] 会给 agent loop 加最大步数、超时和错误处理。

推荐阅读：

- [OpenAI Function Calling](https://platform.openai.com/docs/guides/function-calling)
- [Gemini API Function Calling](https://ai.google.dev/gemini-api/docs/function-calling)
- [Claude Tool Use](https://docs.anthropic.com/en/docs/agents-and-tools/tool-use/overview)

产出：一个 50-150 行的最小 agent，可以选择工具、执行工具、返回最终答案。

### Stage 2: Learn Tool Use, RAG, And Memory

- [ ] 会做检索增强生成：chunk、embed、retrieve、answer with citations。
- [ ] 会把搜索、数据库、文件、浏览器、代码执行接成工具。
- [ ] 会区分短期上下文、会话记忆、长期记忆。
- [ ] 会处理工具失败、空结果、重复调用、幻觉引用。
- [ ] 会让 agent 在回答里给出来源或证据。

推荐阅读：

- [LlamaIndex Agents](https://docs.llamaindex.ai/en/stable/use_cases/agents/)
- [LangChain Docs](https://docs.langchain.com/)
- [Gemini API Code Execution](https://ai.google.dev/gemini-api/docs/code-execution)
- [Model Context Protocol](https://modelcontextprotocol.io/)

产出：一个资料研究助手，输入主题后自动搜索、筛选、总结并输出引用链接。

### Stage 3: Pick One Agent Framework

先选一个主框架学深，不要同时浅尝所有框架。

| Framework | Best For | Learn This If You Want To |
| --- | --- | --- |
| [LangGraph](https://langchain-ai.github.io/langgraph/) | Stateful workflows, graph orchestration | 构建可控、可恢复、可调试的复杂 agent |
| [OpenAI Agents SDK](https://platform.openai.com/docs/guides/agents-sdk/) | OpenAI-native agents | 学 handoff、tracing、guardrails、工具编排 |
| [CrewAI](https://docs.crewai.com/) | Role-based agent teams | 做内容生产、研究、运营类多角色协作 |
| [Microsoft AutoGen](https://microsoft.github.io/autogen/) | Multi-agent conversations | 学 agent 之间如何对话与协作 |
| [LlamaIndex](https://docs.llamaindex.ai/) | Data/RAG agents | 做知识库、文档、企业数据类 agent |
| [Pydantic AI](https://pydantic.dev/docs/ai/core-concepts/agent/) | Typed Python agents | 做类型安全、结构清晰的生产代码 |

- [ ] 跑通一个官方 quickstart。
- [ ] 改造 quickstart，让它调用你自己的工具。
- [ ] 加入状态管理或 memory。
- [ ] 打印完整 trace，能解释每一步为什么发生。
- [ ] 把同一个任务分别用「裸 agent loop」和「框架」实现，对比差异。

产出：一个可调试的 agent 项目，包含 README、运行步骤、示例输入输出。

### Stage 4: Multi-Agent Is Coordination, Not Magic

- [ ] 理解 planner / executor / reviewer / critic / router 等常见角色。
- [ ] 学会用 supervisor 或 graph 管理多 agent，而不是让 agent 随便聊天。
- [ ] 会定义每个 agent 的职责边界、输入输出 schema、停止条件。
- [ ] 会处理循环、争论、任务漂移、上下文膨胀。
- [ ] 会判断什么时候单 agent 更好。

推荐阅读：

- [Google Agent Development Kit](https://google.github.io/adk-docs/)
- [Google ADK announcement](https://developers.googleblog.com/agent-development-kit-easy-to-build-multi-agent-applications/)
- [Agent2Agent Protocol](https://google-a2a.github.io/A2A/specification/)
- [AutoGen paper](https://arxiv.org/abs/2308.08155)

产出：一个小型多 agent 系统，例如 research -> write -> review -> revise。

### Stage 5: Browser And Computer-Use Agents

- [ ] 理解 browser agent 和普通 API tool 的区别。
- [ ] 会用 Playwright 或 browser-use 做网页观察和点击。
- [ ] 会给浏览器操作加安全限制：不登录敏感账号、不越权、不绕过平台规则。
- [ ] 会处理页面变化、弹窗、加载失败、元素定位失败。
- [ ] 会记录截图、DOM、动作日志，方便复盘。

推荐阅读：

- [Claude Computer Use](https://docs.anthropic.com/en/docs/agents-and-tools/tool-use/computer-use-tool)
- [browser-use](https://github.com/browser-use/browser-use)
- [WebArena](https://arxiv.org/abs/2307.13854)
- [VisualWebArena](https://arxiv.org/abs/2401.13649)

产出：一个只操作公开网页的 browser agent，例如打开网页、提取信息、生成摘要。

### Stage 6: Evaluation, Observability, And Safety

- [ ] 为 agent 准备固定测试集，而不是只看 demo。
- [ ] 记录成功率、失败原因、工具调用次数、成本、延迟。
- [ ] 会看 trace，知道失败发生在 prompt、工具、检索、模型还是状态管理。
- [ ] 给危险工具加人工确认，例如发邮件、删文件、付款、发布内容。
- [ ] 了解 prompt injection、data exfiltration、tool abuse 等风险。
- [ ] 会用回归测试防止 prompt 或工具改动后能力退化。

推荐阅读：

- [OpenAI Evals](https://platform.openai.com/docs/guides/evals)
- [OpenAI Agent platform](https://openai.com/agent-platform/)
- [LangSmith](https://docs.smith.langchain.com/)
- [AgentBench](https://arxiv.org/abs/2308.03688)
- [SWE-bench](https://arxiv.org/abs/2310.06770)

产出：一个 agent eval 表格，至少包含 20 个任务、期望结果、实际结果、失败分类。

### Stage 7: Ship A Real Agent

- [ ] 有明确用户、明确任务、明确成功标准。
- [ ] 有日志、trace、错误重试、超时、成本上限。
- [ ] 有权限边界和人工确认机制。
- [ ] 有部署方式：CLI、Web app、Slack bot、GitHub Action 或后台任务。
- [ ] 有 README：怎么运行、怎么配置 key、怎么扩展工具、有哪些限制。

产出：一个别人能 clone 下来跑的 agent 项目。

## Project Ladder

| Level | Project | What You Learn |
| --- | --- | --- |
| 1 | Calculator Agent | 最小 tool call loop |
| 2 | Web Research Agent | 搜索、筛选、引用、总结 |
| 3 | PDF QA Agent | RAG、chunk、retrieval、citation |
| 4 | Coding Review Agent | 读取 diff、风险排序、测试建议 |
| 5 | Browser Agent | 页面观察、点击、提取、失败恢复 |
| 6 | Multi-Agent Writer | planner、writer、reviewer 协作 |
| 7 | Personal Knowledge Agent | 文件、网页、笔记、长期记忆 |
| 8 | Production Agent | evals、trace、权限、部署、监控 |

## Curated Resources

### Official Guides And Blogs

| Resource | Why It Matters |
| --- | --- |
| [Anthropic: Building effective agents](https://www.anthropic.com/engineering/building-effective-agents) | Agent 设计入门必读，讲清 workflow 和 agent 的边界。 |
| [OpenAI: A practical guide to building agents](https://openai.com/business/guides-and-resources/a-practical-guide-to-building-ai-agents/) | 面向产品和工程团队的 agent 落地指南。 |
| [OpenAI: New tools for building agents](https://openai.com/index/new-tools-for-building-agents/) | Responses API、Agents SDK、工具和 tracing 的官方介绍。 |
| [OpenAI Agents SDK](https://platform.openai.com/docs/guides/agents-sdk/) | OpenAI 原生 agent 开发入口。 |
| [Claude Tool Use](https://docs.anthropic.com/en/docs/agents-and-tools/tool-use/overview) | Claude 工具调用机制。 |
| [Claude Computer Use](https://docs.anthropic.com/en/docs/agents-and-tools/tool-use/computer-use-tool) | 电脑操作类 agent 的官方参考。 |
| [Gemini Function Calling](https://ai.google.dev/gemini-api/docs/function-calling) | Gemini 工具调用官方文档。 |
| [Gemini Code Execution](https://ai.google.dev/gemini-api/docs/code-execution) | Gemini 代码执行工具。 |
| [Google Agent Development Kit](https://google.github.io/adk-docs/) | Google 的 agent 开发框架。 |
| [Model Context Protocol](https://modelcontextprotocol.io/) | Agent 连接工具和数据源的重要协议。 |

### Framework Docs

| Framework | Link |
| --- | --- |
| LangGraph | https://langchain-ai.github.io/langgraph/ |
| LangChain | https://docs.langchain.com/ |
| LlamaIndex | https://docs.llamaindex.ai/ |
| CrewAI | https://docs.crewai.com/ |
| AutoGen | https://microsoft.github.io/autogen/ |
| Semantic Kernel Agents | https://learn.microsoft.com/en-us/semantic-kernel/frameworks/agent/ |
| Pydantic AI | https://pydantic.dev/docs/ai/core-concepts/agent/ |
| Qwen-Agent | https://github.com/QwenLM/Qwen-Agent |

### Papers

| Paper | Topic |
| --- | --- |
| [ReAct](https://arxiv.org/abs/2210.03629) | Reasoning + acting 的基础范式。 |
| [Toolformer](https://arxiv.org/abs/2302.04761) | 模型学习何时调用工具。 |
| [Reflexion](https://arxiv.org/abs/2303.11366) | 语言反馈和自我改进。 |
| [Generative Agents](https://arxiv.org/abs/2304.03442) | 记忆、反思、规划驱动的模拟 agent。 |
| [Voyager](https://arxiv.org/abs/2305.16291) | 开放世界中的长期学习 agent。 |
| [AutoGen](https://arxiv.org/abs/2308.08155) | 多 agent 对话框架。 |
| [AgentBench](https://arxiv.org/abs/2308.03688) | Agent 能力评测。 |
| [WebArena](https://arxiv.org/abs/2307.13854) | 真实网页环境下的 agent benchmark。 |
| [SWE-bench](https://arxiv.org/abs/2310.06770) | 真实 GitHub issue 修复评测。 |
| [SWE-agent](https://arxiv.org/abs/2405.15793) | 软件工程 agent 的 agent-computer interface。 |

### GitHub Repositories

| Repo | Why It Is Useful |
| --- | --- |
| [microsoft/ai-agents-for-beginners](https://github.com/microsoft/ai-agents-for-beginners) | 系统化入门课程。 |
| [datawhalechina/hello-agents](https://github.com/datawhalechina/hello-agents) | 中文智能体系统教程。 |
| [langchain-ai/langgraph](https://github.com/langchain-ai/langgraph) | 状态图和可控 agent 编排。 |
| [openai/openai-agents-python](https://github.com/openai/openai-agents-python) | OpenAI Agents SDK Python。 |
| [microsoft/autogen](https://github.com/microsoft/autogen) | 多 agent 对话与协作。 |
| [crewAIInc/crewAI](https://github.com/crewAIInc/crewAI) | 角色型多 agent 自动化。 |
| [run-llama/llama_index](https://github.com/run-llama/llama_index) | RAG 和数据型 agent。 |
| [QwenLM/Qwen-Agent](https://github.com/QwenLM/Qwen-Agent) | Qwen 生态 agent 框架。 |
| [browser-use/browser-use](https://github.com/browser-use/browser-use) | 浏览器 agent 实战。 |
| [SWE-agent/SWE-agent](https://github.com/SWE-agent/SWE-agent) | 软件工程 agent。 |
| [All-Hands-AI/OpenHands](https://github.com/All-Hands-AI/OpenHands) | 开源 coding agent。 |

### Thoughtful Blogs

| Blog | Why It Is Useful |
| --- | --- |
| [Lilian Weng: LLM Powered Autonomous Agents](https://lilianweng.github.io/posts/2023-06-23-agent/) | 经典长文，系统整理 agent 架构、记忆、规划和工具使用。 |
| [Simon Willison: AI/LLM writing](https://simonwillison.net/tags/llms/) | 非常务实的 LLM 工程观察，适合补工程直觉。 |
| [LangChain Blog](https://blog.langchain.com/) | LangGraph、LangSmith、agent 工程实践。 |
| [Google Developers Blog: ADK](https://developers.googleblog.com/agent-development-kit-easy-to-build-multi-agent-applications/) | Google ADK 官方发布文章。 |

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
