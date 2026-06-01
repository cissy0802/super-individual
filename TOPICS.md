# Topics Roadmap

源是仓库中的文件本身（`ls *-{day,week,book,issue}*.html`）。本文件只是主题查找表：N → 主题。超过现有编号时 routine 会 append 新主题。

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
