# Nandana Dileep

AI Engineer · IIT Madras '24 · Bengaluru

I build AI infrastructure: reliable agent runtimes, inference systems, and experiments that measure what actually helps. I write about the architecture, results, and trade-offs behind them.

[Website](https://nandanadileep.com) · [Writing](https://medium.com/@nandanadileep29) · [LinkedIn](https://www.linkedin.com/in/nandana-dileep-06935a212/) · [X](https://x.com/nandana_dileep) · [Email](mailto:nandanadileep29@gmail.com)

## Selected projects

### [Mycelium](https://github.com/mycelium-labs/mycelium) — reliability for agent tool calls

Creator and maintainer of an open-source Python runtime that validates tool inputs and authority, controls retries and concurrency, and records durable outcomes for crash recovery. Integrates with LangGraph, CrewAI, and custom agents; experimental TypeScript and Go clients connect through an HTTP sidecar.

[![PyPI downloads](https://static.pepy.tech/badge/mycelium-runtime)](https://pepy.tech/project/mycelium-runtime)

`pip install mycelium-runtime` · [Docs](https://mycelium-labs.github.io/) · [Design write-up](https://nandanadileep.com/read-about-mycelium/)

### [tiny-reranker](https://github.com/ver-labs/tiny-reranker) — inference performance experiments

Studied a pretrained MiniLM reranker on **Apple M5 and NVIDIA L40S**, comparing PyTorch, MLX, compilation, custom Metal/CUDA/Triton kernels, and Python/Rust serving.

- **11 implementation audits passed; 12,288 accepted HTTP responses validated.**
- Compiled PyTorch reached **736.8 pairs/sec** on L40S and **102.1 pairs/sec** on M5 in warm direct scoring: FP32, 100 documents/query, batch 16, maximum 512 tokens.
- Custom CUDA/Triton kernels did not beat compiled PyTorch on this workload; Rust coordination showed no practical HTTP throughput advantage.

[Results and protocol](https://github.com/ver-labs/tiny-reranker/blob/main/experiments/E18/REPORT.md) · [Engineering write-up](https://medium.com/@nandanadileep29/13-performance-experiments-on-one-reranker-the-limits-of-faster-gpu-code-94670171711f)

### [LLM serving on Apple Silicon](https://github.com/nandanadileep/vllm-like-llm-serving) — studying the serving stack

An experimental MLX/FastAPI inference server with continuous batching, chunked prefill, prefix caching, paged KV-cache experiments, SSE streaming, and an OpenAI-compatible API. Includes a load-testing harness for latency, time to first token, throughput, and memory.

[Architecture write-up](https://medium.com/@nandanadileep29/building-a-vllm-inspired-llm-serving-engine-on-apple-silicon-with-mlx-65b0576ebd05)

### [nanoLLM](https://github.com/nandanadileep/nanoLLM) — modern LLM architecture, one component at a time

Extended nanoGPT with **7 architectural changes**: RMSNorm, SwiGLU, RoPE, GQA, MLA, MoE, and multi-token prediction. On Shakespeare character-level experiments (4 layers, 4 heads, 128 dimensions, 2,000 CPU training steps, same seed), the combined stack reduced validation loss from **1.6645 to 1.5259** and reached the baseline's final loss by **step 500**.

[Benchmarks](https://github.com/nandanadileep/nanoLLM#component-benchmarks) · [Write-up](https://medium.com/@nandanadileep29/i-rebuilt-a-tiny-gpt-into-a-mini-deepseek-one-component-at-a-time-718d3e04cfb6)

### [Identiti](https://github.com/nandanadileep/aegis) — personal AI memory

A React/Flask app that extracts confidence-scored entities from conversations into a Neo4j knowledge graph, with Redis-backed history, Supabase authentication, review, and portable export.

[Try it](https://identiti.nandanadileep.com)

### [TicTic](https://github.com/nandanadileep/tictic) — voice typing for Indian languages

A native SwiftUI macOS app with **23 language choices**, automatic language detection, global dictation shortcuts, transliteration, English translation, and direct text insertion into the active app. Powered by Sarvam AI.

## Selected writing

- [13 Performance Experiments on One Reranker: The Limits of Faster GPU Code](https://medium.com/@nandanadileep29/13-performance-experiments-on-one-reranker-the-limits-of-faster-gpu-code-94670171711f) — kernels, compilation, serving, and negative results.
- [Mycelium: Turning AI Agents into Reliable Systems](https://nandanadileep.com/read-about-mycelium/) — the runtime behind reliable tool execution.
- [Checklist to Prevent All the Agent Failure Modes](https://medium.com/@nandanadileep29/checklist-to-prevent-all-the-agent-failure-modes-f4dfdc7597e1) — failure modes and execution controls.
- [Building a vLLM-Inspired LLM Serving Engine on Apple Silicon](https://medium.com/@nandanadileep29/building-a-vllm-inspired-llm-serving-engine-on-apple-silicon-with-mlx-65b0576ebd05) — scheduling, batching, and KV-cache design with MLX.
- [Swapped Every Part of nanoGPT With Modern Alternatives](https://medium.com/@nandanadileep29/i-rebuilt-a-tiny-gpt-into-a-mini-deepseek-one-component-at-a-time-718d3e04cfb6) — component-by-component architecture experiments.

## Tools I work with

<p>
  <img src="https://skillicons.dev/icons?i=python,pytorch,fastapi,postgres,redis,neo4j,typescript,react,swift,aws,docker&amp;perline=11" alt="Python, PyTorch, FastAPI, PostgreSQL, Redis, Neo4j, TypeScript, React, Swift, AWS, and Docker" />
</p>

![MLX](https://img.shields.io/badge/MLX-000000?style=for-the-badge&logo=apple&logoColor=white)
![CUDA / Triton](https://img.shields.io/badge/CUDA%20%2F%20Triton-76B900?style=for-the-badge&logo=nvidia&logoColor=white)
![LangGraph](https://img.shields.io/badge/LangGraph-1C3C3C?style=for-the-badge&logo=langgraph&logoColor=white)
![CrewAI](https://img.shields.io/badge/CrewAI-FF5A50?style=for-the-badge&logo=crewai&logoColor=white)
