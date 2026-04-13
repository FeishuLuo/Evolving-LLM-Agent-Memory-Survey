<p align="center">
  <img src="./figures/figure1.PNG" alt="Evolution Path of LLM Agent Memory" width="90%">
</p>

<h1 align="center">From Storage to Experience:<br>A Survey on the Evolution of LLM Agent Memory Mechanisms</h1>

<p align="center">
  <a href="https://openreview.net/forum?id=l9Ly41xxPb"><img src="https://img.shields.io/badge/Paper-OpenReview-b31b1b?logo=openaccess&logoColor=white" alt="Paper"></a>
  <a href="https://github.com/FeishuLuo/Evolving-LLM-Agent-Memory-Survey"><img src="https://img.shields.io/github/stars/FeishuLuo/Evolving-LLM-Agent-Memory-Survey?style=social" alt="GitHub Stars"></a>
  <a href="https://github.com/FeishuLuo/Evolving-LLM-Agent-Memory-Survey/blob/main/LICENSE"><img src="https://img.shields.io/github/license/FeishuLuo/Evolving-LLM-Agent-Memory-Survey" alt="License"></a>
  <a href="https://github.com/FeishuLuo/Evolving-LLM-Agent-Memory-Survey/commits/main"><img src="https://img.shields.io/github/last-commit/FeishuLuo/Evolving-LLM-Agent-Memory-Survey" alt="Last Commit"></a>
  <a href="https://github.com/FeishuLuo/Evolving-LLM-Agent-Memory-Survey/issues"><img src="https://img.shields.io/github/issues/FeishuLuo/Evolving-LLM-Agent-Memory-Survey" alt="Issues"></a>
  <img src="https://img.shields.io/badge/Papers-140%2B-blue" alt="Paper Count">
  <img src="https://img.shields.io/badge/PRs-Welcome-brightgreen" alt="PRs Welcome">
</p>

<p align="center">
  <b>ACL 2026 (Findings) &nbsp;|&nbsp; ICLR 2026 Workshop MemAgents</b> &nbsp;|&nbsp; Actively maintained
</p>

<p align="center">
  A curated and continuously updated collection of <b>140+ papers</b> and <b>40+ benchmarks</b><br>
  on the <b>evolutionary framework of LLM agent memory mechanisms</b>.
</p>

- [LightThinker++: From Reasoning Compression to Memory Management](https://arxiv.org/abs/2604.03679) (2026) `Arxiv`

    > Dynamically compresses intermediate reasoning thoughts into compact semantic representations, with a reversible "memory management" mode that allows re-expansion when logical bottlenecks arise.

- [Understand and Accelerate Memory Processing Pipeline for Disaggregated LLM Inference](https://arxiv.org/abs/2603.29002) (2026) `Arxiv`

    > Unifies sparse attention, RAG, and compressed memory into a four-step pipeline (Prepare → Relevancy → Retrieval → Apply), identifying 22%–97% memory processing overhead and proposing systematic acceleration.

- [MemBoost: A Memory-Boosted Framework for Cost-Aware LLM Inference](https://arxiv.org/abs/2603.26557) (2026) `Arxiv`

    > Enables a lightweight model to reuse previously generated answers from memory, selectively escalating difficult queries to a stronger LLM for significant cost reduction.


---

> If you find this survey useful, please consider giving us a :star: to stay updated with the latest additions!
>
> We welcome contributions! If you know of a relevant paper we missed, please open an [issue](https://github.com/FeishuLuo/Evolving-LLM-Agent-Memory-Survey/issues) or submit a [pull request](https://github.com/FeishuLuo/Evolving-LLM-Agent-Memory-Survey/pulls). See our [Contributing Guidelines](CONTRIBUTING.md).

---

## News

- **2026-04** &mdash; Added 10 new papers (LightThinker++, SelRoute, MemSifter, Pancake, etc.) and new 2026 benchmarks
- **2026-01** &mdash; Paper accepted at **ACL 2026 Findings** and **ICLR 2026 Workshop MemAgents**
- **2025-01** &mdash; Preprint released &amp; repository created

- [Codebase-Memory: Tree-Sitter-Based Knowledge Graphs for LLM Code Exploration via MCP](https://arxiv.org/abs/2603.27277) (2026) `Arxiv`

    > Constructs persistent, language-agnostic knowledge graphs from source code using Tree-Sitter across 66 languages, exposed via Model Context Protocol for structural code understanding.

---

## Table of Contents

- [Overview](#overview)
- [Evolution Path](#evolution-path)
- [Paper List](#paper-list)
  - [Storage (33 papers)](#storage)
  - [Reflection (28 papers)](#reflection)
  - [Experience (42 papers)](#experience)
- [Benchmarks & Datasets (43 entries)](#benchmarks--datasets)
- [Citation](#citation)
- [Contributing](#contributing)

---

## Overview

While memory mechanisms have emerged as the architectural cornerstone of LLM agents, current research remains fragmented between operating system engineering and cognitive science. This theoretical divide prevents a unified view of technological synthesis.

We propose a novel **Evolutionary Framework** that formalizes the development of LLM agent memory into three progressive stages:

| Stage | Core Idea | Key Transformation |
|:---:|:---|:---|
| **Storage** | Trajectory Preservation | Faithfully recording raw interaction traces via linear, vector, or structured storage |
| **Reflection** | Trajectory Refinement | Actively evaluating and correcting stored memories through introspection, environment feedback, or coordination |
| **Experience** | Trajectory Abstraction | Compressing redundant trajectories into transferable heuristic wisdom via cross-trajectory abstraction |

---

## Evolution Path

The agent's decision-making process forms a dynamic closed loop enabled by memory. During each task execution cycle, the agent leverages two core capabilities:

1. **Memory Read** &mdash; Actively retrieves relevant knowledge from the memory bank to supplement the current context.
2. **Memory Write** &mdash; Records generated interaction sequences as historical trajectories into the memory system.

Building upon this foundation, we conceptualize the memory mechanism as an evolutionary pathway structured into three stages:

<br>

<details open>
<summary><b>Storage (Trajectory Preservation)</b></summary>
<br>

Storage serves as the cornerstone of memory evolution, emphasizing the faithful preservation of interaction history.

| Paradigm | Characteristics | Strengths | Limitations |
|:---|:---|:---|:---|
| **Linear** | Token stream ordered chronologically | Minimal information loss, maximal logical completeness | Early critical information irreversibly forgotten |
| **Vector** | Embeddings in high-dimensional space | Massive storage capacity | High retrieval difficulty, limited relevance |
| **Structured** | Relational structures (tables, graphs, tiers) | Precise operations, multi-hop retrieval | Requires schema maintenance, less flexible at scale |

</details>

<details open>
<summary><b>Reflection (Trajectory Refinement)</b></summary>
<br>

<p align="center">
  <img src="./figures/figure2.PNG" alt="Drivers in Dynamic Environments" width="65%">
  <br>
  <em>Figure 2: Temporal Validity &amp; Causal Structure in Dynamic Environments.</em>
</p>

| Paradigm | Characteristics | Strengths | Limitations |
|:---|:---|:---|:---|
| **Introspection** | Internal knowledge for self-evaluation | Error correction without external feedback | Risk of reinforcing biases |
| **Environment** | Execution outcomes as refinement signals | Greater adaptability to dynamic environments | Sparse rewards, ambiguous settings |
| **Coordination** | Multi-agent collective reflection | Reduced hallucination, enriched perspectives | Communication overhead, memory conflicts |

</details>

<details open>
<summary><b>Experience (Trajectory Abstraction)</b></summary>
<br>

<p align="center">
  <img src="./figures/figure3.PNG" alt="Cross-Trajectory Abstraction" width="65%">
  <br>
  <em>Figure 3: Overview of Cross-Trajectory Abstraction Techniques.</em>
</p>

| Paradigm | Characteristics | Strengths | Limitations |
|:---|:---|:---|:---|
| **Explicit** | Human-readable patterns from trajectory clusters | Highly interpretable and editable | Lacks precision in complex boundaries |
| **Implicit** | Internalized into model parameters / latent variables | Near-zero retrieval overhead | Reduced interpretability, forgetting risk |
| **Hybrid** | Dynamic "accumulate&ndash;internalize" cycle | Balances interpretability with efficiency | Requires careful transfer coordination |

</details>

---

## Paper List

> Papers are organized following our three-stage evolutionary framework.

### Storage

#### Linear Storage

**Context Window Adaptation**

| Paper | Venue | Year |
|:---|:---:|:---:|
| [Parallel Context Windows for Large Language Models](https://arxiv.org/abs/2212.10947) | ACL | 2022 |
| [Efficient Streaming Language Models with Attention Sinks](https://arxiv.org/abs/2309.17453) | arXiv | 2023 |
| [LLM Maybe LongLM: Self-Extend LLM Context Window Without Tuning](https://arxiv.org/abs/2401.01325) | arXiv | 2024 |

**Information Sparsification**

| Paper | Venue | Year |
|:---|:---:|:---:|
| [H2O: Heavy-Hitter Oracle for Efficient Generative Inference of Large Language Models](https://arxiv.org/abs/2306.14048) | arXiv | 2023 |
| [LLMLingua: Compressing Prompts for Accelerated Inference of Large Language Models](https://arxiv.org/abs/2310.05736) | EMNLP | 2023 |
| [Quest: Query-Aware Sparsity for Efficient Long-Context LLM Inference](https://arxiv.org/abs/2406.10774) | arXiv | 2024 |
| [InfLLM: Training-Free Long-Context Extrapolation for LLMs with an Efficient Context Memory](https://arxiv.org/abs/2402.04617) | NeurIPS | 2024 |
| [LightThinker++: From Reasoning Compression to Memory Management](https://arxiv.org/abs/2604.03679) | arXiv | 2026 |
| [Understand and Accelerate Memory Processing Pipeline for Disaggregated LLM Inference](https://arxiv.org/abs/2603.29002) | arXiv | 2026 |
| [MemBoost: A Memory-Boosted Framework for Cost-Aware LLM Inference](https://arxiv.org/abs/2603.26557) | arXiv | 2026 |

#### Vector Storage

**Semantic Retrieval**

| Paper | Venue | Year |
|:---|:---:|:---:|
| [Enhancing LLM Intelligence with ARM-RAG: Auxiliary Rationale Memory for Retrieval Augmented Generation](https://arxiv.org/abs/2311.04177) | arXiv | 2023 |
| [Larimar: Large Language Models with Episodic Memory Control](https://arxiv.org/abs/2403.11901) | arXiv | 2024 |
| [MemLong: Memory-Augmented Retrieval for Long Text Modeling](https://arxiv.org/abs/2408.16967) | arXiv | 2024 |
| [SelRoute: Query-Type-Aware Routing for Long-Term Conversational Memory Retrieval](https://arxiv.org/abs/2604.02431) | arXiv | 2026 |
| [MemSifter: Offloading LLM Memory Retrieval via Outcome-Driven Proxy Reasoning](https://arxiv.org/abs/2603.03379) | arXiv | 2026 |
| [TA-Mem: Tool-Augmented Autonomous Memory Retrieval for LLM in Long-Term Conversational QA](https://arxiv.org/abs/2603.09297) | arXiv | 2026 |
| [Evoking User Memory: Personalizing LLM via Recollection-Familiarity Adaptive Retrieval](https://arxiv.org/abs/2603.09250) | arXiv | 2026 |

**Weighted Retrieval**

| Paper | Venue | Year |
|:---|:---:|:---:|
| [Generative Agents: Interactive Simulacra of Human Behavior](https://arxiv.org/abs/2304.03442) | UIST | 2023 |
| [MemoryBank: Enhancing Large Language Models with Long-Term Memory](https://arxiv.org/abs/2305.10250) | arXiv | 2023 |

#### Structured Storage

**Tabular Database**

| Paper | Venue | Year |
|:---|:---:|:---:|
| [ChatDB: Augmenting LLMs with Databases as Their Symbolic Memory](https://arxiv.org/abs/2306.03901) | arXiv | 2023 |
| [DB-GPT: Empowering Database Interactions with Private Large Language Models](https://arxiv.org/abs/2312.17449) | arXiv | 2023 |
| [Training a Team of Language Models as Options to Build an SQL-Based Memory](https://doi.org/10.3390/app152111399) | Applied Sciences | 2025 |

**Tiered Architectures**

| Paper | Venue | Year |
|:---|:---:|:---:|
| [RecurrentGPT: Interactive Generation of (Arbitrarily) Long Text](https://arxiv.org/abs/2305.13304) | arXiv | 2023 |
| [SwiftSage: A Generative Agent with Fast and Slow Thinking for Complex Interactive Tasks](https://arxiv.org/abs/2305.17390) | arXiv | 2023 |
| [MemoChat: Tuning LLMs to Use Memos for Consistent Long-Range Open-Domain Conversation](https://arxiv.org/abs/2308.08239) | arXiv | 2023 |
| [MemGPT: Towards LLMs as Operating Systems](https://arxiv.org/abs/2310.08560) | arXiv | 2023 |
| [MemOS: A Memory OS for AI System](https://arxiv.org/abs/2507.03724) | arXiv | 2025 |
| [Pancake: Hierarchical Memory System for Multi-Agent LLM Serving](https://arxiv.org/abs/2602.21477) | arXiv | 2026 |
| [Multi-Layered Memory Architectures for LLM Agents](https://arxiv.org/abs/2603.29194) | arXiv | 2026 |

**Semantic Graphs**

| Paper | Venue | Year |
|:---|:---:|:---:|
| [MemLLM: Finetuning LLMs to Use an Explicit Read-Write Memory](https://arxiv.org/abs/2404.11672) | arXiv | 2024 |
| [GraphReader: Building Graph-based Agent to Enhance Long-Context Abilities of Large Language Models](https://arxiv.org/abs/2406.14550) | EMNLP | 2024 |
| [AriGraph: Learning Knowledge Graph World Models with Episodic Memory for LLM Agents](https://arxiv.org/abs/2407.04363) | IJCAI | 2024 |
| [Codebase-Memory: Tree-Sitter-Based Knowledge Graphs for LLM Code Exploration via MCP](https://arxiv.org/abs/2603.27277) | arXiv | 2026 |

---

### Reflection

#### Introspection

**Error Rectification**

| Paper | Venue | Year |
|:---|:---:|:---:|
| [Reflexion: Language Agents with Verbal Reinforcement Learning](https://arxiv.org/abs/2303.11366) | NeurIPS | 2023 |
| [Think-in-Memory: Recalling and Post-Thinking Enable LLMs with Long-Term Memory](https://arxiv.org/abs/2311.08719) | arXiv | 2023 |
| [Constructing Coherent Spatial Memory in LLM Agents through Graph Rectification](https://arxiv.org/abs/2510.04195) | arXiv | 2025 |
| [Enhancing LLM Planning Capabilities through Intrinsic Self-Critique](https://arxiv.org/abs/2512.24103) | arXiv | 2025 |

**Dynamic Maintenance**

| Paper | Venue | Year |
|:---|:---:|:---:|
| [Zep: A Temporal Knowledge Graph Architecture for Agent Memory](https://arxiv.org/abs/2501.13956) | arXiv | 2025 |
| [Mem0: Building Production-Ready AI Agents with Scalable Long-Term Memory](https://arxiv.org/abs/2504.19413) | arXiv | 2025 |
| [CAMA: A Constructivist View of Agentic Memory for LLM-Based Reading Comprehension](https://arxiv.org/abs/2510.05520) | arXiv | 2025 |
| [Memory OS of AI Agent](https://arxiv.org/abs/2506.06326) | arXiv | 2025 |
| [Mem1: Learning to Synergize Memory and Reasoning for Efficient Long-Horizon Agents](https://arxiv.org/abs/2506.15841) | arXiv | 2025 |

**Knowledge Compression**

| Paper | Venue | Year |
|:---|:---:|:---:|
| [Coarse-to-Fine Grounded Memory for LLM Agent Planning](https://arxiv.org/abs/2508.15305) | arXiv | 2025 |
| [MemOrb: A Plug-and-Play Verbal-Reinforcement Memory Layer for E-Commerce Customer Service](https://arxiv.org/abs/2509.18713) | arXiv | 2025 |
| [LEGOMem: Modular Procedural Memory for Multi-Agent LLM Systems for Workflow Automation](https://arxiv.org/abs/2510.04851) | arXiv | 2025 |
| [Scaling Long-Horizon LLM Agent via Context-Folding](https://arxiv.org/abs/2510.11967) | arXiv | 2025 |
| [DeepAgent: A General Reasoning Agent with Scalable Toolsets](https://arxiv.org/abs/2510.21618) | arXiv | 2025 |
| [AgentFold: Long-Horizon Web Agents with Proactive Context Management](https://arxiv.org/abs/2510.24699) | arXiv | 2025 |

#### Environment

**Environment Modeling**

| Paper | Venue | Year |
|:---|:---:|:---:|
| [CLIN: A Continually Learning Language Agent for Rapid Task Adaptation and Generalization](https://arxiv.org/abs/2310.10134) | arXiv | 2023 |
| [Explicit Memory Learning with Expectation Maximization](https://aclanthology.org/2024.emnlp-main.927/) | EMNLP | 2024 |
| [DEAL: Enhancing Agent Learning through World Dynamics Modeling](https://arxiv.org/abs/2407.17695) | arXiv | 2024 |
| [ToolMem: Enhancing Multimodal Agents with Learnable Tool Capability Memory](https://arxiv.org/abs/2510.06664) | arXiv | 2025 |
| [Preference-Aware Memory Update for Long-Term LLM Agents](https://arxiv.org/abs/2510.09720) | arXiv | 2025 |

**Decision Optimization**

| Paper | Venue | Year |
|:---|:---:|:---:|
| [Self-Goal: Your Language Agents Already Know How to Achieve High-Level Goals](https://arxiv.org/abs/2406.04784) | arXiv | 2024 |
| [Memory-R1: Enhancing Large Language Model Agents to Manage and Utilize Memories via Reinforcement Learning](https://arxiv.org/abs/2508.19828) | arXiv | 2025 |
| [Memory-Driven Self-Improvement for Decision Making with Large Language Models](https://arxiv.org/abs/2509.26340) | arXiv | 2025 |

#### Coordination

**Multi-dimensional Calibration**

| Paper | Venue | Year |
|:---|:---:|:---:|
| [Reflective Multi-Agent Collaboration Based on Large Language Models](https://proceedings.neurips.cc/paper_files/paper/2024/hash/fa54b0edce5eef0bb07654e8ee800cb4-Abstract-Conference.html) | NeurIPS | 2024 |
| [GraphCoGent: Mitigating LLMs' Working Memory Constraints via Multi-Agent Collaboration](https://arxiv.org/abs/2508.12379) | arXiv | 2025 |
| [MAR: Multi-Agent Reflexion Improves Reasoning Abilities in LLMs](https://arxiv.org/abs/2512.20845) | arXiv | 2025 |
| [MIRIX: Multi-Agent Memory System for LLM-Based Agents](https://arxiv.org/abs/2507.07957) | arXiv | 2025 |
| [Narrative Memory in Machines: Multi-Agent Arc Extraction in Serialized TV](https://arxiv.org/abs/2508.07010) | arXiv | 2025 |

---

### Experience

#### Explicit Experience

**Heuristic Guidelines**

| Paper | Venue | Year |
|:---|:---:|:---:|
| [Dynamic Cheatsheet: Test-Time Learning with Adaptive Memory](https://arxiv.org/abs/2504.07952) | arXiv | 2025 |
| [G-Memory: Tracing Hierarchical Memory for Multi-Agent Systems](https://arxiv.org/abs/2506.07398) | arXiv | 2025 |
| [Agent KB: Leveraging Cross-Domain Experience for Agentic Problem Solving](https://arxiv.org/abs/2507.06229) | arXiv | 2025 |
| [SWE-Exp: Experience-Driven Software Issue Resolution](https://arxiv.org/abs/2507.23361) | arXiv | 2025 |
| [ArcMemo: Abstract Reasoning Composition with Lifelong LLM Memory](https://arxiv.org/abs/2509.04439) | arXiv | 2025 |
| [SEDM: Scalable Self-Evolving Distributed Memory for Agents](https://arxiv.org/abs/2509.09498) | arXiv | 2025 |
| [ReasoningBank: Scaling Agent Self-Evolving with Reasoning Memory](https://arxiv.org/abs/2509.25140) | arXiv | 2025 |
| [LightMem: Lightweight and Efficient Memory-Augmented Generation](https://arxiv.org/abs/2510.18866) | arXiv | 2025 |
| [Learning from Supervision with Semantic and Episodic Memory](https://arxiv.org/abs/2510.19897) | arXiv | 2025 |
| [FLEX: Continuous Agent Evolution via Forward Learning from Experience](https://arxiv.org/abs/2511.06449) | arXiv | 2025 |
| [Remember Me, Refine Me: A Dynamic Procedural Memory Framework](https://arxiv.org/abs/2512.10696) | arXiv | 2025 |
| [LoongFlow: Directed Evolutionary Search via Plan-Execute-Summarize](https://arxiv.org/abs/2512.24077) | arXiv | 2025 |

**Procedural Primitives**

| Paper | Venue | Year |
|:---|:---:|:---:|
| [Agent Workflow Memory](https://arxiv.org/abs/2409.07429) | arXiv | 2024 |
| [Inducing Programmatic Skills for Agentic Tasks](https://arxiv.org/abs/2504.06821) | arXiv | 2025 |
| [Automated Skill Discovery for Language Agents through Exploration and Iterative Feedback](https://arxiv.org/abs/2506.04287) | arXiv | 2025 |
| [MemP: Exploring Agent Procedural Memory](https://arxiv.org/abs/2508.06433) | arXiv | 2025 |
| [PolySkill: Learning Generalizable Skills through Polymorphic Abstraction](https://arxiv.org/abs/2510.15863) | arXiv | 2025 |
| [CASCADE: Cumulative Agentic Skill Creation through Autonomous Development and Evolution](https://arxiv.org/abs/2512.23880) | arXiv | 2025 |
| [AccelOpt: A Self-Improving LLM Agentic System for AI Accelerator Kernel Optimization](https://arxiv.org/abs/2511.15915) | arXiv | 2025 |
| [Contextual Experience Replay for Self-Improvement of Language Agents](https://arxiv.org/abs/2506.06698) | ACL | 2025 |
| [MemEvolve: Meta-Evolution of Agent Memory Systems](https://arxiv.org/abs/2512.18746) | arXiv | 2025 |
| [Youtu-Agent: Scaling Agent Productivity with Hybrid Policy Optimization](https://arxiv.org/abs/2512.24615) | arXiv | 2025 |

#### Implicit Experience

**Latent Modulation**

| Paper | Venue | Year |
|:---|:---:|:---:|
| [Titans: Learning to Memorize at Test Time](https://arxiv.org/abs/2501.00663) | arXiv | 2024 |
| [MemGen: Weaving Generative Latent Memory for Self-Evolving Agents](https://arxiv.org/abs/2509.24704) | arXiv | 2025 |
| [LatentEvolve: Self-Evolving Test-Time Scaling in Latent Space](https://arxiv.org/abs/2509.24771) | arXiv | 2025 |

**Parameter Internalization**

| Paper | Venue | Year |
|:---|:---:|:---:|
| [AgentRefine: Enhancing Agent Generalization through Refinement Tuning](https://arxiv.org/abs/2501.01702) | arXiv | 2025 |
| [Memento No More: Coaching AI Agents to Master Multiple Tasks via Hints Internalization](https://arxiv.org/abs/2502.01562) | arXiv | 2025 |
| [Group-in-Group Policy Optimization for LLM Agent Training](https://arxiv.org/abs/2505.10978) | arXiv | 2025 |
| [Agent Lightning: Train Any AI Agents with Reinforcement Learning](https://arxiv.org/abs/2508.03680) | arXiv | 2025 |
| [VerlTool: Towards Holistic Agentic Reinforcement Learning with Tool Use](https://arxiv.org/abs/2509.01055) | arXiv | 2025 |
| [From Correction to Mastery: Reinforced Distillation of Large Language Model Agents](https://arxiv.org/abs/2509.14257) | arXiv | 2025 |
| [Agent Learning via Early Experience](https://arxiv.org/abs/2510.08558) | arXiv | 2025 |
| [Analyzing and Internalizing Complex Policy Documents for LLM Agents](https://arxiv.org/abs/2510.11588) | arXiv | 2025 |
| [Internalizing World Models via Self-Play Finetuning for Agentic RL](https://arxiv.org/abs/2510.15047) | arXiv | 2025 |
| [AgentEvolver: Towards Efficient Self-Evolving Agent System](https://arxiv.org/abs/2511.10395) | arXiv | 2025 |
| [Agent-R1: Training Powerful LLM Agents with End-to-End Reinforcement Learning](https://arxiv.org/abs/2511.14460) | arXiv | 2025 |
| [Rethinking Expert Trajectory Utilization in LLM Post-Training](https://arxiv.org/abs/2512.11470) | arXiv | 2025 |
| [Guided Self-Evolving LLMs with Minimal Human Supervision](https://arxiv.org/abs/2512.02472) | arXiv | 2025 |
| [End-to-End Test-Time Training for Long Context](https://arxiv.org/abs/2512.23675) | arXiv | 2025 |

#### Hybrid Experience

**Experience Transfer**

| Paper | Venue | Year |
|:---|:---:|:---:|
| [ReasoningBank: Scaling Agent Self-Evolving with Reasoning Memory](https://arxiv.org/abs/2509.25140) | arXiv | 2025 |
| [EvolveR: Self-Evolving LLM Agents through an Experience-Driven Lifecycle](https://arxiv.org/abs/2510.16079) | arXiv | 2025 |
| [Exploratory Memory-Augmented LLM Agent via Hybrid On- and Off-Policy Optimization](https://arxiv.org/abs/2602.23008) | ICLR | 2026 |

---

## Benchmarks & Datasets

### Storage Stage

| Benchmark | Venue | Year | Focus |
|:---|:---:|:---:|:---|
| [HotpotQA](https://arxiv.org/abs/1809.09600) | EMNLP | 2018 | Multi-hop cross-document reasoning |
| [LongBench](https://arxiv.org/abs/2308.14508) | arXiv | 2023 | Bilingual, multitask long-context understanding |
| [MemoryBank](https://arxiv.org/abs/2305.10250) | arXiv | 2023 | Long-term dialog memory |
| [Multimodal Needle in a Haystack](https://arxiv.org/abs/2406.11230) | NAACL | 2024 | Long-context multimodal retrieval |
| [LongBench v2](https://arxiv.org/abs/2412.15204) | arXiv | 2024 | Realistic long-context reasoning |
| [RULER](https://arxiv.org/abs/2404.06654) | arXiv | 2024 | Effective context window measurement |
| [BABILong](https://arxiv.org/abs/2406.10149) | arXiv | 2024 | Synthetic long-context reasoning-in-a-haystack |
| [DialSim](https://arxiv.org/abs/2406.13144) | arXiv | 2024 | Real-time long-term dialogue simulation |
| [Evaluating Very Long-Term Conversational Memory of LLM Agents](https://arxiv.org/abs/2402.17753) | arXiv | 2024 | Very long-term conversational memory |
| [MADial-Bench](https://arxiv.org/abs/2409.15240) | NAACL | 2024 | Memory-augmented dialogue |
| [HELMET](https://arxiv.org/abs/2410.02694) | arXiv | 2024 | Comprehensive long-context evaluation |
| [Explicit vs. Implicit Memory](https://arxiv.org/abs/2508.13250) | arXiv | 2025 | Multi-hop personalized reasoning |
| [Evaluating the Long-Term Memory of Large Language Models](https://aclanthology.org/2025.findings-acl.1014/) | ACL | 2025 | Long-term memory evaluation protocol |
| [Beyond a Million Tokens](https://arxiv.org/abs/2510.27246) | arXiv | 2025 | Ultra-long memory (>1M tokens) |
| [LoCoBench-Agent](https://arxiv.org/abs/2511.13998) | arXiv | 2025 | Long-context software engineering agents |
| [MemoryRewardBench](https://arxiv.org/abs/2601.11969) | arXiv | 2026 | Reward models for long-term memory management |
| [AgentLongBench](https://arxiv.org/abs/2601.20730) | arXiv | 2026 | Dynamic long-context agent evaluation |

### Reflection Stage

| Benchmark | Venue | Year | Focus |
|:---|:---:|:---:|:---|
| [Personalized Large Language Model Assistant with Evolving Conditional Memory](https://arxiv.org/abs/2312.17257) | COLING | 2023 | Evolving conditional memory |
| [PerLTQA](https://arxiv.org/abs/2402.16288) | arXiv | 2024 | Personal long-term memory QA |
| [Evaluating Very Long-Term Conversational Memory of LLM Agents](https://arxiv.org/abs/2402.17753) | arXiv | 2024 | Conversational memory consistency |
| [On the Multi-Turn Instruction Following for Conversational Web Agents](https://arxiv.org/abs/2402.15057) | ACL | 2024 | Web agent multi-turn memory |
| [SHARE](https://arxiv.org/abs/2410.20682) | arXiv | 2024 | Shared memory in dialogue |
| [Minerva](https://arxiv.org/abs/2502.03358) | arXiv | 2025 | Programmable memory read-write tests |
| [Personalized Preference Following](https://arxiv.org/abs/2502.09597) | arXiv | 2025 | User preference memory |
| [Multi-Session Personalized Conversation](https://arxiv.org/abs/2503.07018) | arXiv | 2025 | Multi-session implicit reasoning |
| [PersonaMem-v2](https://arxiv.org/abs/2512.06688) | arXiv | 2025 | Implicit user persona memory |
| [Mem-PAL](https://arxiv.org/abs/2511.13410) | arXiv | 2025 | Personalized long-term dialogue |
| [WebChoreArena](https://arxiv.org/abs/2506.01952) | arXiv | 2025 | Web agent intermediate state memory |
| [StoryBench](https://arxiv.org/abs/2506.13356) | arXiv | 2025 | Long-term narrative tracking |
| [Evaluating Memory in LLM Agents via Incremental Multi-Turn Interactions](https://arxiv.org/abs/2507.05257) | arXiv | 2025 | Memory retention across turns |
| [LLM Self-Awareness via Internal Circuits](https://arxiv.org/abs/2510.17132) | arXiv | 2025 | Internal memory limit awareness |
| [HaluMem](https://arxiv.org/abs/2511.03506) | arXiv | 2025 | Hallucination in memory systems |
| [ConvoMem Benchmark](https://arxiv.org/abs/2511.10523) | arXiv | 2025 | Conversational memory (75K+ QA pairs) |
| [KnowMe-Bench](https://arxiv.org/abs/2601.04745) | arXiv | 2026 | Person understanding from narratives |
| [RealMem](https://arxiv.org/abs/2601.06966) | arXiv | 2026 | Real-world project-oriented memory |
| [StructMemEval](https://arxiv.org/abs/2602.11243) | arXiv | 2026 | Memory structure organization |

### Experience Stage

| Benchmark | Venue | Year | Focus |
|:---|:---:|:---:|:---|
| [StreamBench](https://arxiv.org/abs/2406.08747) | arXiv | 2024 | Continuous improvement over task streams |
| [LifelongAgentBench](https://arxiv.org/abs/2505.11942) | arXiv | 2025 | Lifelong learning agents |
| [MEMTRACK](https://arxiv.org/abs/2510.01353) | NeurIPS Workshop | 2025 | Multi-platform state tracking |
| [MemoryBench](https://arxiv.org/abs/2510.17281) | arXiv | 2025 | Memory and continual learning metrics |
| [Evo-Memory](https://arxiv.org/abs/2511.20857) | arXiv | 2025 | Test-time self-evolving memory |
| [MemoryArena](https://arxiv.org/abs/2602.16313) | arXiv | 2026 | Interdependent multi-session agentic tasks |
| [AMA-Bench](https://arxiv.org/abs/2602.22769) | arXiv | 2026 | Long-horizon agentic memory |

---

## Citation

If you find this survey useful in your research, please consider citing our paper:

```bibtex
@inproceedings{luo2026from,
  title   = {From Storage to Experience: A Survey on the Evolution of LLM Agent Memory Mechanisms},
  author  = {Luo, Jinghao and Tian, Yuchen and Cao, Chuxue and Luo, Ziyang and Lin, Hongzhan and Li, Kaixin and Kong, Chuyi and Yang, Ruichao and Ma, Jing},
  booktitle = {Findings of the Association for Computational Linguistics: ACL 2026},
  year    = {2026}
}
```

> The BibTeX entry will be updated with the official ACL 2026 proceedings metadata once available.

---

## Contributing

We welcome contributions from the community! Please see our [Contributing Guidelines](CONTRIBUTING.md) for how to:
- Suggest new papers
- Report broken links
- Propose new categories

---

<p align="center">
  This project is licensed under the <a href="LICENSE">MIT License</a>.
</p>
