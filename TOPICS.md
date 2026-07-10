# Topics Roadmap

> **⚠️ routine 须知**：本表即全部计划。只写下面**已列出**的条目；**全部写完就停**——别自己发明新主题、别往本文件加行。写完只发一条 PushNotification 请 BigCat 补充。（新条目由 BigCat / deep-research 反哺加进本表，届时你自然继续写。）

源是仓库中的文件本身（`ls *-{day,week,book,issue}*.html`）。本文件是主题查找表：N → 主题。

**本路线图已收口：Day 1–53 封顶，不再自动续写。** Phase 1–5（Day 1–48）为 AI 超级个体工程全集；Phase 6（Day 49–53）是 cross-ref 补齐的工程空白（推理模型工程化 / 安全护栏与沙箱 / 自动 prompt 优化 / 智能体商务与支付协议 / 用 AI 学习的护栏工程）——概念归 ai-ml，本 routine 只讲工程。向量库 / ANN 索引等已在两边覆盖（ai-ml Day 4/22 + 本 routine Day 11/43），不再补。Day 53 是从 deep-research「初级工程师」一期反哺回来的手动增补（learning guardrails + junior engineer 组织用法），非 cron 产出。

## Phase 1 — Engineering 核心
- Day 1: Prompt Engineering — System prompt 架构、四层结构、XML vs MD、CoT 边界、prefix caching
- Day 2: Context Engineering — lost-in-the-middle、信息排布、chunk vs embedding、compaction、长 context vs RAG
- Day 3: Harness Engineering — harness 定义、Claude Code harness 拆解、自建 harness 最小架构、Anthropic 'Building effective agents' 精读
- Day 4: Tool Use & Function Calling — tool schema 设计、参数描述>名字、过多 tool 退化、parallel tool calls、为 Claude 设计 tool 的 7 条经验
- Day 5: Agent Design Patterns — Reflexion / ReAct / Plan-and-execute / Multi-agent debate、agent 失败模式、Anthropic 'Less is more' 哲学、self-eval 不可靠 / backward rationalization / confidence inflation
- Day 6: Eval 工程 — LLM-as-judge 去偏、A/B prompt、regression test for prompts、Anthropic Evals 框架
- Day 7: Memory & State 管理 — 滑动窗口 vs summarization vs vector retrieval、长期记忆 3 种架构、user profile
- Day 8: 多模态工程 — 图片压缩与分辨率、PDF 处理、视觉 prompt 设计、多模态 RAG 的坑
- Day 9: LLM 反直觉行为 / Prompting Patterns — Calibration 双向性（anchor 单边失控）、否定指令为何无效、列表数量=emphasis（3:1 失衡）、Examples > 抽象规则、yes-man 与 steelman、lost-in-the-middle
- Day 10: Hallucination 的工程治理 — LLM 不说「不知道」是 RLHF bug、哪些 token 几乎 100% 编（citations/URLs/function names/dates）、specificity 反比（问得越具体编得越细）、grounding via tools/RAG、structured output、verification chains、hallucination-aware eval
- Day 11: RAG 实战工程 — Chunk 策略、hybrid search、reranker 真实价值、HyDE / multi-query / fusion
- Day 12: Fine-tuning vs Prompting — LoRA / QLoRA 工程权衡、数据集质量>数量、distillation、open weights 超越 Claude 的场景、temperature/top-p 调优误区

## Phase 2 — 应用与系统
- Day 13: Multi-agent Systems — Orchestrator-worker、debate、specialist agents、何时反模式、agent 协作协议、coordination overhead
- Day 14: Inference Optimization — vLLM / TGI / TensorRT-LLM、KV cache 工程、continuous batching、speculative decoding 实战
- Day 15: Latency Engineering — Streaming、prompt caching、并行调用、p50/p95/p99 优化、用户感知延迟
- Day 16: Cost Engineering — Token 经济学、缓存策略、model routing、batch API、监控与告警
- Day 17: Claude Code 高阶用法 — Subagents / hooks / slash commands / MCP servers、SDK 自动化、大 repo CLAUDE.md
- Day 18: MCP — 协议核心、自建 MCP server、stdio vs http、tool/resource/prompt 三层
- Day 19: Coding Agents 工程 — Cursor / Claude Code / Aider harness 差异、plan mode 重要性、AI pair programming
- Day 20: Code Refactoring with AI — 大规模重构分步、AI 不擅长的重构、test-first AI refactor
- Day 21: AI for Research — Deep Research 对比、个人研究 agent 自建、信息源筛选、引用追溯
- Day 22: Writing 工程化 — 用 AI 保持 voice、style transfer、章节-段落-句子分层 prompt
- Day 23: Personal AI Infra — LLM gateway、跨模型路由、cache 层、observability、API key 管理
- Day 24: Prompt Injection 攻防 — direct/indirect injection、defense in depth、untrusted content 隔离

## Phase 3 — 前沿与边界
- Day 25: Agentic IDE 未来 — Cursor / Windsurf / Claude Code / Devin 路线对比
- Day 26: Computer Use & Browser Agents — Anthropic Computer Use API、Browser Use / Playwright agent
- Day 27: Synthetic Data & Self-improvement — Constitutional AI、RLAIF、self-play
- Day 28: Local & Edge LLM — Ollama / LM Studio / MLX、量化成本、本地模型够用场景
- Day 29: AI Eval Beyond Benchmark — MMLU/HumanEval 误导、为真实场景写 eval
- Day 30: Open Source Models 实战 — Llama / Qwen / DeepSeek / Mistral
- Day 31: AI Safety in Personal Use — Model misuse、deceptive AI 早期信号、个人 agent kill switch
- Day 32: AI Coding 的未来 5 年 — Coding agents 路线图、SWE-bench 局限、个人护城河

## Phase 4 — 人机协作与生产化
- Day 33: 大规模 Legacy 代码库的 AI 治理 — Strangler/codemod 渐进引入、护栏即代码(fitness functions)、ratchet 棘轮、CODEOWNERS/分层信任、自动门 + 风险分级 + 抽样评审 + provenance
- Day 34: Human-in-the-loop 工程 — 异步审批队列、agent 暂停/通知/恢复、置信度路由(auto/ask/deny)、风险分级、升级与委派、可中断 checkpoint、审批审计
- Day 35: Prompt 即代码 / 版本治理 — prompt registry、git 化管理、A/B 与灰度、回滚、跨模型 prompt 漂移监控
- Day 36: 大型组织的 Skills Library 治理 — skill/工具库的准入评审、版本化与废弃、重复与冲突检测、质量与安全门、权限与可见性、使用度量驱动淘汰、命名规范与可发现性
- Day 37: AI 可观测性 — agent 的 trace/span、prompt 监控、漂移检测、在线评估
- Day 38: 结构化输出工程 — JSON mode、函数调用可靠性、schema 约束、解析容错
- Day 39: Agent 错误恢复与韧性 — retry/指数退避、幂等与补偿、checkpoint/断点续跑、超时与熔断、部分失败处理
- Day 40: 数据 pipeline for AI — embedding 的 ETL、增量索引、数据版本、特征存储
- Day 41: 流式与中断工程 — streaming UX、增量/部分解析、tool call 流式、中途取消与回滚、首 token 延迟
- Day 42: AI 测试与 CI/CD — prompt 回归测试、评估流水线、金丝雀发布、影子测试
- Day 43: 检索质量工程 — 召回 vs 精度、混合检索调优、reranker 训练、检索评估
- Day 44: AI 辅助数据分析 — 自然语言查 SQL、图表生成、数据故事、分析 agent
- Day 45: AI 工程的反模式 — 过度工程化、评估缺失、prompt 脆弱性、供应商锁定

## Phase 5 — 非 LLM 模态
- Day 46: 语音 AI 工程 — STT/TTS pipeline、实时语音 agent、打断处理、语音克隆与伦理
- Day 47: 图像生成工程 — Diffusion 控制(ControlNet/LoRA)、图像 prompt 工程、图像 agent、水印与版权
- Day 48: 知识库与 GraphRAG — 文档解析、表格/图表理解、知识图谱构建、GraphRAG

## Phase 6 — 新前沿的工程化：推理 · 安全 · 自动优化（cross-ref ai-ml 后补齐）
- Day 49: 推理模型的工程化 — 何时用 reasoning(o1/o3/R1) vs 标准模型、extended thinking 与思维预算控制、推理成本/延迟权衡与路由、agent 内的推理调用、解析与利用 reasoning trace（概念见 ai-ml Day 28 推理模型）
- Day 50: LLM 安全护栏与沙箱 — 输入/输出过滤、PII 脱敏与密钥防泄、越狱与有害内容防御、输出校验与策略门(guardrails)、agent 代码执行沙箱（注入攻防见 Day 24、对齐失败机制见 ai-ml Day 47）
- Day 51: 自动 Prompt 优化 — 程序化 prompt(DSPy)、APE/自动 prompt 搜索、eval 驱动迭代 vs 手调、few-shot 自动选样与指令优化（prompt 概念见 ai-ml Day 3、版本治理见 Day 35）
- Day 52: 智能体商务与支付协议 — agent 代人付款/相互结算的新协议层：AP2(Agent Payments Protocol, Google) 的 Mandate 授权(Intent/Cart)、ACP(Agentic Commerce Protocol, OpenAI/Stripe)、x402(Coinbase, HTTP 402 稳定币原生支付)、与 A2A/MCP 的关系、授权·真实性·问责三难与工程落地（2026 前沿，月度前沿刷新纳入；概念/生态见来源，本 routine 讲协议与落地工程）
- Day 53: 用 AI 学习的护栏工程 — PNAS 无护栏 −17% / 导师版消除损害、生成-验证倒置（学习 vs 干活模式）、工程师验证瓶颈（METR）、组织里给 junior engineer 用的四条护栏、测量职业阶梯；反哺自 deep-research「初级工程师」
- Day 54: 给自己的 AI 工作流做 oracle 盘点 — 哪些验证环节有独立裁判(测试/编译器/形式检查)、哪些是AI 看 AI, 按可验证性重排自动化边界, 同源验证的独立性陷阱, 个人版护栏先于规模检查清单(钩子·源自 deep-research #3)
- Day 55: 把三个已验证开关装进自己的学习流程 — 检索练习(带反馈+延迟后测)、间隔(比例随考期变化, 递增无证据)、交错(仅限易混材料); 实验室→课堂衰减账本与轻剂量陷阱; AI 学习工具选型: 看它是否默认这三个开关而非卖学习风格(钩子·源自 deep-research #4)
