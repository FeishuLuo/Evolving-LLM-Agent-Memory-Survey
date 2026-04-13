# Evolving-LLM-Agent-Memory-Survey
Paper list for "From Storage to Experience: A Survey on the Evolution of LLM Agent Memory Mechanisms".

## 📖 Introduction
While memory mechanisms have emerged as the architectural cornerstone of LLM agents, current research remains fragmented, oscillating between operating system engineering and cognitive science. This theoretical divide prevents a unified view of technological synthesis and a coherent evolutionary perspective. To bridge this gap, this repository maintains the paper list for our survey: [**"From Storage to Experience: A Survey on the Evolution of LLM Agent Memory Mechanisms"**](https://www.preprints.org/manuscript/202601.0618). We propose a novel **Evolutionary Framework** that formalizes the development of LLM agent memory into three distinct stages:
1. 💾 **Storage** (Trajectory Preservation): Focusing on the complete preservation and basic retrieval of raw interaction traces.
2. 🧠 **Reflection** (Trajectory Refinement): Introducing analysis mechanisms to refine and correct original memories through reflection.
3. 🌟 **Experience** (Trajectory Abstraction)：Transforming trajectory clusters into experience through cross-trajectory abstraction techniques.

By focusing on these pivotal technologies and their positions within the evolution path, this project aims to offer a unified roadmap to help the community research and design next-generation LLM Agent Memory systems.

## 🛤️ Evolution Path
![Evolution Path](./figures/figure1.PNG)
<p align="center"><i>Figure 1: The Evolutionary path of LLM Agent Memory.</i></p>

Before diving into the evolution of memory mechanisms, we first establish the standard workflow for an LLM Agent integrated with memory. Taking the classic ReAct paradigm as an example, the Agent's decision-making process forms a dynamic closed loop enabled by memory.
During each task execution cycle, the Agent leverages two core capabilities:
1. **Memory Read:** The Agent actively retrieves relevant knowledge from the memory bank to supplement the current context.
2. **Memory Write:** As the task progresses, the generated interaction sequences are recorded as historical trajectories and are written into the memory system in real-time.

Building upon this foundation, we conceptualize the memory mechanism as an evolutionary pathway. This framework is structured into three distinct stages, where each stage is further categorized into three representative paradigms based on their core characteristics.

💾 **Storage**   
Storage serves as the cornerstone of memory evolution, emphasizing the faithful preservation of interaction history. Based on differences in data organization structures, we categorize existing storage mechanisms into the following three types.
1. **Linear Storage**  
     - **Characteristics：** Linear storage treats interaction history as a token stream strictly ordered chronologically.  
     - **Primary Research Directions:** Expanding memory storage capacity through context window adaptation and information sparsification.  
     - **Advantages:** Minimal information loss and maximal logical completeness.  
     - **Limitations:** While ensuring coherence within recent context, early critical information is irreversibly forgotten.
2. **Vector Storage**
     - **Characteristics：** Vector storage encodes interaction trajectories into high-dimensional embedding space.  
     - **Primary Research Directions:** Optimizing retrieval strategies through semantic proximity matching and multi-dimensional weighted scoring that incorporates temporal decay and importance metrics.  
     - **Advantages:** Massive storage capacity.  
     - **Limitations:** High retrieval difficulty and limited memory relevance.
3. **Structured Storage**
     - **Characteristics：** Structured storage utilizes predefined relational structures to preserve interaction trajectories.  
     - **Primary Research Directions:** Leveraging tabular formats for structured queries, implementing tiered memory hierarchies to balance capacity and access speed, and modeling interaction history as topological networks of entities and relations.  
     - **Advantages:** Supports precise operations, logical reasoning, and efficient multi-hop retrieval across structured relationships.  
     - **Limitations:** Requires schema maintenance and lacks flexibility when handling massive interaction trajectories.  

🧠 **Reflection**
The Reflection stage transforms memory from passive recording to active evaluation, utilizing feedback signals to refine memory by correcting errors and reducing noise. Based on the source of reflection signals, we categorize mechanisms into three types.
1. **Introspection**  
     - **Characteristics：** Leverages the LLM agent's internal knowledge to autonomously evaluate and restructure memory.  
     - **Primary Research Directions:** Error rectification through self-critique, dynamic lifecycle management of memory content, and knowledge compression via multi-granularity abstraction.  
     - **Advantages:** Achieves trajectory-level error correction and integration without the need for external feedback.  
     - **Limitations:** Inherent risk of reinforcing model biases or hallucinations.
2. **Environment**  
     - **Characteristics：** Utilizes real-world execution outcomes or environmental feedback as signals for memory refinement.  
     - **Primary Research Directions:** Error rectification through self-critique, dynamic lifecycle management of memory content, and knowledge compression via multi-granularity abstraction.  
     - **Advantages:** Interaction trajectories refined based on facts exhibit greater adaptability to dynamic environments.  
     - **Limitations:** Sparse reward settings and ambiguous execution environments lead to implementation difficulties.
3. **Coordination**  
     - **Characteristics：** Extends reflection to multi-agent collectives by leveraging role specialization and consensus mechanisms.  
     - **Primary Research Directions:** Facilitates the reflection of memory through the construction of societies of heterogeneous agents.  
     - **Advantages:** Reduced hallucination risks and enriched memory perspectives.  
     - **Limitations:** Introduces additional communication overhead and potential memory conflicts across agents.  

🌟 **Experience**
Experience represents the highest cognitive layer, where memory mechanisms compress redundant trajectories into transferable heuristic wisdom through cross-trajectory abstraction. Based on the form of experience representation, we categorize this stage into three types.
1. **Explicit**  
     - **Characteristics：** Explicit experience extracts human-readable, comprehensible, and editable patterns from trajectory clusters.  
     - **Primary Research Directions:** Crystallizing implicit intuition into natural language heuristic guidelines, and encapsulating recurring behavioral patterns into executable procedural primitives.  
     - **Advantages:** Highly interpretable and editable, enabling transparent self-evolution.  
     - **Limitations:** Lacks precision in complex decision boundaries and is prone to conflicting experiences.
2. **Implicit**  
     - **Characteristics：** Implicit experience internalizes interaction histories into model parameters or latent variables.  
     - **Primary Research Directions:** Parameter internalization through fine-tuning techniques that embed trajectory distributions into network weights, and latent modulation that encodes experience into hidden-layer variables dynamically invoked during inference.  
     - **Advantages:** Extremely low retrieval overhead and near-intuitive instantaneous experience.  
     - **Limitations:** Reduced interpretability, high update costs, and the risk of catastrophic forgetting.
3. **Hybrid**
     - **Characteristics：** Hybrid experience establishes a dynamic "accumulate–internalize" cycle, treating explicit experience as a high-capacity cache that is periodically compressed and transferred into implicit model weights.  
     - **Primary Research Directions:** Experience transfer mechanisms that progressively internalize explicit experience repositories through gradient-based updates, combining the interpretability benefits of explicit storage with the efficiency of parameter internalization. 
     - **Advantages:** Balances interpretability with inference efficiency and restricts unbounded memory growth.  
     - **Limitations:** Requires coordination of accumulation and internalization cycles and control of transfer criteria, with potential knowledge degradation during conversion.

## 📜 Paper List

### 💾 Storage

#### Linear

##### Context Window Adaptation

- [Parallel Context Windows for Large Language Models](https://arxiv.org/abs/2212.10947) (2022) `*ACL`

    > Extends context-window memory by reusing positional encodings across parallel windows, enabling much longer usable context without retraining.

- [Efficient Streaming Language Models with Attention Sinks](https://arxiv.org/abs/2309.17453) (2023) `Arxiv`

    > Improves streaming memory by preserving “attention sink” tokens in the KV cache so unbounded streams still retain early context.

- [LLM Maybe LongLM: Self-Extend LLM Context Window Without Tuning](https://arxiv.org/abs/2401.01325) (2024) `Arxiv`

    > Extends effective memory span at inference time via bi-level attention, enabling long-context use without any extra training.

##### Information Sparsification

- [H2O: Heavy-Hitter Oracle for Efficient Generative Inference of Large Language Models](https://arxiv.org/abs/2306.14048) (2023) `Arxiv`

    > Models long-context memory as cache management, retaining only heavy-hitter tokens in the KV cache while safely evicting redundant history.

- [Quest: Query-Aware Sparsity for Efficient Long-Context LLM Inference](https://arxiv.org/abs/2406.10774) (2024) `Arxiv`

    > Improves memory reading by using query-aware sparse attention to select only the most relevant KV pages for long contexts.

- [LLMLingua: Compressing Prompts for Accelerated Inference of Large Language Models](https://arxiv.org/abs/2310.05736) (2023) `*EMNLP`

    > Treats context as compressible memory, learning to shrink prompts so more conversational history fits into a fixed-length window.

- [InfLLM: Training-Free Long-Context Extrapolation for LLMs with an Efficient Context Memory](https://arxiv.org/abs/2402.04617) (2024) `*NeurIPS`

    > Augments LLMs with an external context memory that retrieves only relevant long-range segments, enabling million-token usage without retraining.

- [LightThinker++: From Reasoning Compression to Memory Management](https://arxiv.org/abs/2604.03679) (2026) `Arxiv`

    > Dynamically compresses intermediate reasoning thoughts into compact semantic representations, with a reversible "memory management" mode that allows re-expansion when logical bottlenecks arise.

- [Understand and Accelerate Memory Processing Pipeline for Disaggregated LLM Inference](https://arxiv.org/abs/2603.29002) (2026) `Arxiv`

    > Unifies sparse attention, RAG, and compressed memory into a four-step pipeline (Prepare → Relevancy → Retrieval → Apply), identifying 22%–97% memory processing overhead and proposing systematic acceleration.

- [MemBoost: A Memory-Boosted Framework for Cost-Aware LLM Inference](https://arxiv.org/abs/2603.26557) (2026) `Arxiv`

    > Enables a lightweight model to reuse previously generated answers from memory, selectively escalating difficult queries to a stronger LLM for significant cost reduction.


---

#### Vector

##### Semantic Retrieval

- [Enhancing LLM Intelligence with ARM-RAG: Auxiliary Rationale Memory for Retrieval Augmented Generation](https://arxiv.org/abs/2311.04177) (2023) `Arxiv`

    > Augments retrieval memory with stored chains-of-thought, letting RAG systems retrieve not only facts but also successful reasoning traces.

- [MemLong: Memory-Augmented Retrieval for Long Text Modeling](https://arxiv.org/abs/2408.16967) (2024) `Arxiv`

    > Couples an external retrieval memory with a decoder-only LM so long documents are modeled via retrieved historical segments instead of full attention.

- [Larimar: Large Language Models with Episodic Memory Control](https://arxiv.org/abs/2403.11901) (2024) `Arxiv`

    > Adds a brain-inspired episodic memory layer that can insert, edit, and forget facts, enabling dynamic control over what the model remembers.

- [SelRoute: Query-Type-Aware Routing for Long-Term Conversational Memory Retrieval](https://arxiv.org/abs/2604.02431) (2026) `Arxiv`

    > Routes each query to a specialized retrieval pipeline (lexical, semantic, hybrid, or vocabulary-enriched) based on query type, achieving strong recall with compact models.

- [MemSifter: Offloading LLM Memory Retrieval via Outcome-Driven Proxy Reasoning](https://arxiv.org/abs/2603.03379) (2026) `Arxiv`

    > Introduces a lightweight proxy model to pre-filter memory candidates before the main LLM, balancing retrieval cost and accuracy.

- [TA-Mem: Tool-Augmented Autonomous Memory Retrieval for LLM in Long-Term Conversational QA](https://arxiv.org/abs/2603.09297) (2026) `Arxiv`

    > Treats memory retrieval as a tool-use problem, allowing the LLM to autonomously decide when and how to query its memory via episodic notes and graph representations.

- [EVOKING USER MEMORY:      Personalizing LLM via Recollection-Familiarity Adaptive Retrieval](https://arxiv.org/abs/2603.09250) (2026) `Arxiv`

    > Inspired by dual-process theory in cognitive science, combines fast "Familiarity" matching with deep "Recollection" retrieval for personalized memory access.


##### Weighted Retrieval

- [MemoryBank: Enhancing Large Language Models with Long-Term Memory](https://arxiv.org/abs/2305.10250) (2023) `Arxiv`

    > Builds a long-term memory bank that weights and decays user memories over time, mimicking human forgetting to keep dialog history relevant.

- [Generative Agents: Interactive Simulacra of Human Behavior](https://arxiv.org/abs/2304.03442) (2023) `*UIST`

    > Introduces an agent architecture that stores, weights, and aggregates episodic memories to drive believable long-term social behavior.

---

#### Structured

##### Tabular Database

- [ChatDB: Augmenting LLMs with Databases as Their Symbolic Memory](https://arxiv.org/abs/2306.03901) (2023) `Arxiv`

    > Treats SQL databases as symbolic long-term memory, letting LLMs issue read–write queries to store and retrieve precise structured facts.

- [DB-GPT: Empowering Database Interactions with Private Large Language Models](https://arxiv.org/abs/2312.17449) (2023) `Arxiv`

    > Engineers a private LLM + DB stack where retrieval-augmented agents use databases as secure, domain-specific memory stores.

- [Training a Team of Language Models as Options to Build an SQL-Based Memory](#) (2025) `*Applied Sciences`

    > Organizes multiple LMs as options whose experiences are consolidated into an SQL-backed memory for later reuse.

##### Tiered Architectures

- [MemGPT: Towards LLMs as Operating Systems](https://arxiv.org/abs/2310.08560) (2023) `Arxiv`

    > Frames the LLM as an OS kernel with tiered memory (short-term, long-term, external tools) and explicit read–write operations.

- [MemoChat: Tuning LLMs to Use Memos for Consistent Long-Range Open-Domain Conversation](https://arxiv.org/abs/2308.08239) (2023) `Arxiv`

    > Fine-tunes chat models to write and consult memo entries, turning conversation history into structured long-term memory.

- [MemOS: A Memory OS for AI System](https://arxiv.org/abs/2507.03724) (2025) `Arxiv`

    > Proposes an operating-system-like abstraction for scheduling, sharing, and garbage-collecting memories across AI components.

- [SwiftSage: A Generative Agent with Fast and Slow Thinking for Complex Interactive Tasks](https://arxiv.org/abs/2305.17390) (2023) `Arxiv`

    > Combines fast heuristic responses with slow reflective reasoning, supported by explicit memory to carry knowledge across interactions.

- [RecurrentGPT: Interactive Generation of (Arbitrarily) Long Text](https://arxiv.org/abs/2305.13304) (2023) `Arxiv`

    > Wraps an LLM in a recurrent loop that summarizes and stores past content, effectively creating a rolling external memory for arbitrarily long text.

- [Multi-Layered Memory Architectures for LLM Agents](https://arxiv.org/abs/2603.29194) (2026) `Arxiv`

    > Decomposes dialogue history into working, episodic, and semantic layers with adaptive retrieval gating and retention regularization to control cross-session drift.

- [Pancake: Hierarchical Memory System for Multi-Agent LLM Serving](https://arxiv.org/abs/2602.21477) (2026) `Arxiv`

    > A multi-tier memory system unifying multi-level index caching, coordinated cross-agent index management, and collaborative inter-agent memory sharing for efficient ANN search at scale.


##### Semantic Graphs

- [MemLLM: Finetuning LLMs to Use an Explicit Read-Write Memory](https://arxiv.org/abs/2404.11672) (2024) `Arxiv`

    > Finetunes LLMs to interact with explicit key–value memory slots, learning when and how to read and write external memories.

- [AriGraph: Learning Knowledge Graph World Models with Episodic Memory for LLM Agents](https://arxiv.org/abs/2407.04363) (2024) `*IJCAI`

    > Builds a knowledge-graph world model augmented with episodic memory so agents can reason over temporally grounded graph states.

- [GraphReader: Building Graph-based Agent to Enhance Long-Context Abilities of Large Language Models](https://arxiv.org/abs/2406.14550) (2024) `*EMNLP`

    > Represents long contexts as graphs and lets agents traverse them, turning unstructured history into structured graph memory.

- [Codebase-Memory: Tree-Sitter-Based Knowledge Graphs for LLM Code Exploration via MCP](https://arxiv.org/abs/2603.27277) (2026) `Arxiv`

    > Constructs persistent, language-agnostic knowledge graphs from source code using Tree-Sitter across 66 languages, exposed via Model Context Protocol for structural code understanding.

---

### 🧠 Reflection

#### Introspection

##### Error Rectification

- [Reflexion: Language Agents with Verbal Reinforcement Learning](https://arxiv.org/abs/2303.11366) (2023) `*NeurIPS`

    > Introduces verbal self-reflection as a memory update signal, storing critiques of past failures to guide future reasoning.

- [Think-in-Memory: Recalling and Post-Thinking Enable LLMs with Long-Term Memory](https://arxiv.org/abs/2311.08719) (2023) `Arxiv`

    > Proposes a recall-then-think loop where agents first retrieve long-term memories and then refine them via post-hoc reasoning.

- [Constructing Coherent Spatial Memory in LLM Agents through Graph Rectification](https://arxiv.org/abs/2510.04195) (2025) `Arxiv`

    > Builds coherent spatial memory by rectifying graph-structured observations, enabling consistent maps over long agent trajectories.

- [Enhancing LLM Planning Capabilities through Intrinsic Self-Critique](#) (2025) `Arxiv`

    > Uses intrinsic self-critique to continually rewrite planning memories, refining multi-step strategies over time.

##### Dynamic Maintenance

- [Zep: A Temporal Knowledge Graph Architecture for Agent Memory](https://arxiv.org/abs/2501.13956) (2025) `Arxiv`

    > Organizes memories as a temporal knowledge graph so agents can query facts along time and causal axes.

- [Mem0: Building Production-Ready AI Agents with Scalable Long-Term Memory](https://arxiv.org/abs/2504.19413) (2025) `Arxiv`

    > Provides a production-oriented long-term memory layer with pluggable storage, retrieval, and decay policies for agents.

- [CAMA: A Constructivist View of Agentic Memory for LLM-Based Reading Comprehension](https://arxiv.org/abs/2510.05520) (2025) `Arxiv`

    > Treats reading as constructing memory structures, incrementally building and updating comprehension memories over a document.

- [Memory OS of AI Agent](https://arxiv.org/abs/2506.06326) (2025) `Arxiv`

    > Envisions a unified memory OS that coordinates allocation, isolation, and sharing of memories across tasks and tools.

- [Mem1: Learning to Synergize Memory and Reasoning for Efficient Long-Horizon Agents](https://arxiv.org/abs/2506.15841) (2025) `Arxiv`

    > Jointly learns when to read/write memory and how to reason, optimizing the synergy between memory operations and planning.

##### Knowledge Compression

- [MemOrb: A Plug-and-Play Verbal-Reinforcement Memory Layer for E-Commerce Customer Service](https://arxiv.org/abs/2509.18713) (2025) `Arxiv`

    > Adds a reinforcement-shaped memory layer that selectively keeps customer interaction snippets most useful for future service.

- [LEGOMem: Modular Procedural Memory for Multi-Agent LLM Systems for Workflow Automation](https://arxiv.org/abs/2510.04851) (2025) `Arxiv`

    > Decomposes workflow experience into modular procedural memory blocks that agents can recombine like LEGO.

- [AgentFold: Long-Horizon Web Agents with Proactive Context Management](https://arxiv.org/abs/2510.24699) (2025) `Arxiv`

    > Proposes proactive folding and unfolding of context, compressing working memory while preserving key decision traces.

- [Coarse-to-Fine Grounded Memory for LLM Agent Planning](https://arxiv.org/abs/2508.15305) (2025) `Arxiv`

    > Organizes memories in a coarse-to-fine hierarchy so high-level plans can be grounded into detailed stateful traces.

- [Scaling Long-Horizon LLM Agent via Context-Folding](https://arxiv.org/abs/2510.11967) (2025) `Arxiv`

    > Scales long-horizon behavior by folding past context into compact summaries and unfolding it only when needed.

- [DeepAgent: A General Reasoning Agent with Scalable Toolsets](https://arxiv.org/abs/2510.21618) (2025) `Arxiv`

    > Maintains multi-level memories about tools, tasks, and outcomes to support general-purpose reasoning across domains.

---

#### Environment

##### Environment Modeling

- [DEAL: Enhancing Agent Learning through World Dynamics Modeling](https://arxiv.org/abs/2407.17695) (2024) `Arxiv`

    > Treats world models themselves as memory, learning dynamics that let agents store and reuse environment knowledge over long horizons.

- [ToolMem: Enhancing Multimodal Agents with Learnable Tool Capability Memory](https://arxiv.org/abs/2510.06664) (2025) `Arxiv`

    > Builds a dedicated memory of tool capabilities so agents remember which tools worked best in which multimodal contexts.

- [CLIN: A Continually Learning Language Agent for Rapid Task Adaptation and Generalization](https://arxiv.org/abs/2310.10134) (2023) `Arxiv`

    > Maintains and updates experience memories to support continual learning and fast adaptation to new tasks.

- [Preference-Aware Memory Update for Long-Term LLM Agents](https://arxiv.org/abs/2510.09720) (2025) `Arxiv`

    > Updates memory with an explicit model of user preferences, prioritizing storage of preference-relevant events.

- [Explicit Memory Learning with Expectation Maximization](#) (2024) `*EMNLP`

    > Applies an EM framework to decide which experiences become explicit memories and which should be pruned.

##### Decision Optimization

- [Memory-R1: Enhancing Large Language Model Agents to Manage and Utilize Memories via Reinforcement Learning](https://arxiv.org/abs/2508.19828) (2025) `Arxiv`

    > Optimizes memory management policies with RL, learning when to write, erase, and consult memories for better decisions.

- [Memory-Driven Self-Improvement for Decision Making with Large Language Models](https://arxiv.org/abs/2509.26340) (2025) `Arxiv`

    > Uses accumulated memory of past decisions to drive self-improvement, revising policies based on long-term outcomes.

- [Self-Goal: Your Language Agents Already Know How to Achieve High-Level Goals](https://arxiv.org/abs/2406.04784) (2024) `Arxiv`

    > Shows that with suitable memory and planning, LLM agents can decompose and pursue high-level goals over extended interactions.

---

#### Coordination

##### Multi-dimensional Calibration

- [MIRIX: Multi-Agent Memory System for LLM-Based Agents](https://arxiv.org/abs/2507.07957) (2025) `Arxiv`

    > Designs shared and private memory spaces for multi-agent systems, enabling both coordinated and personalized behaviors.

- [GraphCoGent: Mitigating LLMs' Working Memory Constraints via Multi-Agent Collaboration in Complex Graph Understanding](#) (2025) `Arxiv`

    > Splits complex graph memory across collaborating agents, each holding partial views that together reconstruct the full structure.

- [Reflective Multi-Agent Collaboration Based on Large Language Models](#) (2024) `*NeurIPS`

    > Adds collective reflection and shared memory updates so teams of agents can learn from past collaborations.

- [Narrative Memory in Machines: Multi-Agent Arc Extraction in Serialized TV](https://arxiv.org/abs/2508.07010) (2025) `Arxiv`

    > Builds narrative memories of characters and story arcs from long TV scripts using cooperating agents.

- [MAR: Multi-Agent Reflexion Improves Reasoning Abilities in LLMs](#) (2025) `Arxiv`

    > Extends Reflexion to multi-agent settings, where agents share reflective memories to collectively enhance reasoning.

---

### 🌟 Experience

#### Explicit

##### Heuristic Guidelines

- [FLEX: Continuous Agent Evolution via Forward Learning from Experience](#) (2025) `Arxiv`

    > Treats experience as forward-progress memory, continuously extracting and reusing heuristics from past tasks.

- [ArcMemo: Abstract Reasoning Composition with Lifelong LLM Memory](https://arxiv.org/abs/2509.04439) (2025) `Arxiv`

    > Leverages a lifelong memory of abstract reasoning patterns that can be composed to solve new problems.

- [LightMem: Lightweight and Efficient Memory-Augmented Generation](https://arxiv.org/abs/2510.18866) (2025) `Arxiv`

    > Proposes a lightweight memory module that cheaply injects retrieved context into generation for long sequences.

- [ReasoningBank: Scaling Agent Self-Evolving with Reasoning Memory](https://arxiv.org/abs/2509.25140) (2025) `Arxiv`

    > Constructs a bank of high-quality reasoning traces that agents can query as reusable experience.

- [Dynamic Cheatsheet: Test-Time Learning with Adaptive Memory](https://arxiv.org/abs/2504.07952) (2025) `Arxiv`

    > Organizes important facts encountered at test time into an adaptive “cheatsheet” memory for rapid reuse.

- [SEDM: Scalable Self-Evolving Distributed Memory for Agents](https://arxiv.org/abs/2509.09498) (2025) `Arxiv`

    > Introduces a distributed memory architecture where agents share and evolve experiences across nodes.

- [Learning from Supervision with Semantic and Episodic Memory: A Reflective Approach to Agent Adaptation](https://arxiv.org/abs/2510.19897) (2025) `Arxiv`

    > Combines semantic and episodic memory to reinterpret supervision, improving how agents adapt to new data.

- [G-Memory: Tracing Hierarchical Memory for Multi-Agent Systems](https://arxiv.org/abs/2506.07398) (2025) `Arxiv`

    > Traces memory at multiple hierarchy levels, from local agent views to global team state, for multi-agent systems.

- [Agent KB: Leveraging Cross-Domain Experience for Agentic Problem Solving](https://arxiv.org/abs/2507.06229) (2025) `Arxiv`

    > Builds a cross-domain knowledge base of agent experiences that can be transferred to new tasks.

- [SWE-Exp: Experience-Driven Software Issue Resolution](https://arxiv.org/abs/2507.23361) (2025) `Arxiv`

    > Stores past bug-fix trajectories as experience memory to guide future software issue resolution.

- [Remember Me, Refine Me: A Dynamic Procedural Memory Framework for Experience-Driven Agent Evolution](#) (2025) `Arxiv`

    > Maintains procedural memories that are continually refined as agents gain new experience.

- [LoongFlow: Directed Evolutionary Search via a Cognitive Plan-Execute-Summarize Paradigm](#) (2025) `Arxiv`

    > Uses a plan–execute–summarize loop to accumulate and evolve high-level experience memories over long task sequences.

##### Procedural Primitives

- [CASCADE: Cumulative Agentic Skill Creation through Autonomous Development and Evolution](#) (2025) `Arxiv`

    > Treats skills as procedural memory primitives that are discovered, combined, and reused over time.

- [Inducing Programmatic Skills for Agentic Tasks](https://arxiv.org/abs/2504.06821) (2025) `Arxiv`

    > Induces program-like skills from trajectories, turning implicit experience into explicit procedural memory.

- [AccelOpt: A Self-Improving LLM Agentic System for AI Accelerator Kernel Optimization](#) (2025) `Arxiv`

    > Accumulates optimization attempts as memory so the agent improves AI accelerator kernels over successive runs.

- [Agent Workflow Memory](https://arxiv.org/abs/2409.07429) (2024) `Arxiv`

    > Explicitly represents workflows as memory objects, letting agents recall and modify multi-step procedures.

- [MemP: Exploring Agent Procedural Memory](https://arxiv.org/abs/2508.06433) (2025) `Arxiv`

    > Systematically studies how agents can represent, store, and use procedural memories for complex behaviors.

- [PolySkill: Learning Generalizable Skills through Polymorphic Abstraction](https://arxiv.org/abs/2510.15863) (2025) `Arxiv`

    > Learns polymorphic skill abstractions that act as reusable memory units across diverse tasks.

- [Contextual Experience Replay for Self-Improvement of Language Agents](#) (2025) `*ACL`

    > Replays past experiences in similar contexts so agents can self-improve from their own memory.

- [Automated Skill Discovery for Language Agents through Exploration and Iterative Feedback](https://arxiv.org/abs/2506.04287) (2025) `Arxiv`

    > Automatically discovers and stores new skills as procedural memories via exploration and feedback.

- [MemEvolve: Meta-Evolution of Agent Memory Systems](#) (2025) `Arxiv`

    > Explores the design space of memory systems themselves, evolving which memory mechanisms work best.

- [Youtu-Agent: Scaling Agent Productivity with Automated Generation and Hybrid Policy Optimization](#) (2025) `Arxiv`

    > Aggregates experiences from large-scale agent runs into memory, then optimizes policies against this experience pool.

---

#### Implicit

##### Latent Modulation

- [MemGen: Weaving Generative Latent Memory for Self-Evolving Agents](https://arxiv.org/abs/2509.24704) (2025) `Arxiv`

    > Encodes experience as latent memory vectors that can be continually updated and recombined during self-evolution.

- [LatentEvolve: Self-Evolving Test-Time Scaling in Latent Space](https://arxiv.org/abs/2509.24771) (2025) `Arxiv`

    > Performs self-evolution in latent space, adapting the model’s implicit memory at test time without explicit context.

- [Titans: Learning to Memorize at Test Time](https://arxiv.org/abs/2501.00663) (2024) `Arxiv`

    > Treats memorization itself as a test-time learning problem, building task-specific memory online during inference.

##### Parameter Internalization

- [AgentEvolver: Towards Efficient Self-Evolving Agent System](#) (2025) `Arxiv`

    > Provides a framework where accumulated experience is periodically distilled into parameters, internalizing memory.

- [Agent Learning via Early Experience](https://arxiv.org/abs/2510.08558) (2025) `Arxiv`

    > Highlights the role of early experiences as priors that shape long-term internalized memory in agents.

- [VerlTool: Towards Holistic Agentic Reinforcement Learning with Tool Use](https://arxiv.org/abs/2509.01055) (2025) `Arxiv`

    > Unifies RL and tool-use memory, so agents internalize how and when to call external tools.

- [Memento No More: Coaching AI Agents to Master Multiple Tasks via Hints Internalization](https://arxiv.org/abs/2502.01562) (2025) `Arxiv`

    > Internalizes human-provided hints into parameters, turning external guidance into lasting multi-task memory.

- [Analyzing and Internalizing Complex Policy Documents for LLM Agents](https://arxiv.org/abs/2510.11588) (2025) `Arxiv`

    > Studies how agents can parse and encode long policy documents as internal decision-making memory.

- [From Correction to Mastery: Reinforced Distillation of Large Language Model Agents](https://arxiv.org/abs/2509.14257) (2025) `Arxiv`

    > Uses reinforcement-guided distillation to move corrected behaviors from episodic memory into the model weights.

- [Group-in-Group Policy Optimization for LLM Agent Training](https://arxiv.org/abs/2505.10978) (2025) `Arxiv`

    > Structures training as nested policy groups so different experience shards can be internalized efficiently.

- [Agent-R1: Training Powerful LLM Agents with End-to-End Reinforcement Learning](#) (2025) `Arxiv`

    > Directly optimizes agent behavior via end-to-end RL, internalizing long-horizon experience into the base model.

- [Agent Lightning: Train Any AI Agents with Reinforcement Learning](https://arxiv.org/abs/2508.03680) (2025) `Arxiv`

    > Offers a generic RL training stack that turns experience trajectories into parametric agent memory.

- [Internalizing World Models via Self-Play Finetuning for Agentic RL](https://arxiv.org/abs/2510.15047) (2025) `Arxiv`

    > Uses self-play finetuning to internalize world models, shifting environment knowledge from external logs into parameters.

- [Rethinking Expert Trajectory Utilization in LLM Post-Training](#) (2025) `Arxiv`

    > Reexamines how expert trajectories should be used so that their information becomes robust internal memory.

- [Guided Self-Evolving LLMs with Minimal Human Supervision](#) (2025) `Arxiv`

    > Lets LLMs self-evolve with sparse guidance, gradually folding external experience back into the model weights.

- [End-to-End Test-Time Training for Long Context](#) (2025) `Arxiv`

    > Adapts models at test time on long-context tasks, turning fresh interaction data into immediate internal memory updates.

- [AgentRefine: Enhancing Agent Generalization through Refinement Tuning](https://arxiv.org/abs/2501.01702) (2025) `Arxiv`

    > Refines agent parameters using feedback from diverse tasks, consolidating experience into more general internal memory.

---

#### Hybrid

##### Experience Transfer

- [EvolveR: Self-Evolving LLM Agents through an Experience-Driven Lifecycle](https://arxiv.org/abs/2510.16079) (2025) `Arxiv`

    > Structures agents around an experience-driven lifecycle where memories are collected, abstracted, and internalized in cycles.

- [Exploratory Memory-Augmented LLM Agent via Hybrid On- and Off-Policy Optimization](#) (2025) `Under Review`

    > Combines on- and off-policy RL to update both policy and memory, leveraging stored trajectories more fully.

- [ReasoningBank: Scaling Agent Self-Evolving with Reasoning Memory](https://arxiv.org/abs/2509.25140) (2025) `Arxiv` *(also listed under Heuristic Guidelines)*

    > Treats stored reasoning traces as a scalable bank of experience that powers self-evolving agents.

---
### 📊 Benchmarks & Datasets

#### Storage Stage

- [LongBench: A Bilingual, Multitask Benchmark for Long Context Understanding](https://arxiv.org/abs/2308.14508) (2023) `Arxiv`

    > Provides a bilingual, multitask benchmark to evaluate how well models store and use long textual context.

- [LongBench v2: Towards Deeper Understanding and Reasoning on Realistic Long-Context Multitasks](https://arxiv.org/abs/2412.15204) (2024) `Arxiv`

    > Extends LongBench with more realistic tasks to stress-test long-context memory and reasoning.

- [RULER: What's the Real Context Size of Your Long-Context Language Models?](https://arxiv.org/abs/2404.06654) (2024) `Arxiv`

    > Benchmarks the effective context window of long-context LMs, revealing how much past information they truly remember.

- [Multimodal Needle in a Haystack: Benchmarking Long-Context Capability of Multimodal Large Language Models](#) (2024) `*NAACL`

    > Evaluates multimodal models’ ability to retrieve “needle” signals from very long mixed-text–image memories.

- [HotpotQA: A Dataset for Diverse, Explainable Multi-Hop Question Answering](#) (2018) `*EMNLP`

    > Serves as an early benchmark for multi-hop reasoning over multiple documents, stressing cross-document memory.

- [MemoryBank: Enhancing Large Language Models with Long-Term Memory](https://arxiv.org/abs/2305.10250) (2023) `Arxiv`

    > Includes datasets and evaluations for how well long-term memory modules help dialog agents remember users.

- [BABILong: Testing the Limits of LLMs with Long Context Reasoning-in-a-Haystack](https://arxiv.org/abs/2406.10149) (2024) `Arxiv`

    > Creates synthetic long-context tasks to probe how far LLM reasoning-in-a-haystack memory can scale.

- [DialSim: A Real-Time Simulator for Evaluating Long-Term Dialogue Understanding of Conversational Agents](https://arxiv.org/abs/2406.13144) (2024) `Arxiv`

    > Provides a simulator to benchmark agents’ long-term dialogue memory and context tracking in real time.

- [Evaluating Very Long-Term Conversational Memory of LLM Agents](https://arxiv.org/abs/2402.17753) (2024) `Arxiv`

    > Proposes evaluation setups focused specifically on how agents retain and use very long-term conversational memories.

- [Beyond a Million Tokens: Benchmarking and Enhancing Long-Term Memory in LLMs](https://arxiv.org/abs/2510.27246) (2025) `Arxiv`

    > Benchmarks LLM memory beyond million-token contexts and studies methods to enhance such ultra-long memory.

- [Explicit v.s. Implicit Memory: Exploring Multi-Hop Complex Reasoning over Personalized Information](https://arxiv.org/abs/2508.13250) (2025) `Arxiv`

    > Compares benchmarks for explicit vs. implicit memory in multi-hop reasoning over personalized user information.

- [Evaluating the Long-Term Memory of Large Language Models](#) (2025) `*ACL`

    > Presents a dedicated benchmark protocol to measure the long-term memory capabilities of LLMs.

- [MADial-Bench: Towards Real-World Evaluation of Memory-Augmented Dialogue Generation](#) (2024) `*NAACL`

    > Benchmarks memory-augmented dialogue systems on realistic multi-session conversational scenarios.

- [HELMET: How to Evaluate Long-Context Language Models Effectively and Thoroughly](https://arxiv.org/abs/2410.02694) (2024) `Arxiv`

    > Proposes a comprehensive evaluation framework for long-context LMs, covering storage, retrieval, and usage of context.

- [AgentLongBench: A Controllable Long Benchmark For Long-Contexts Agents via Environment Rollouts](https://arxiv.org/abs/2601.20730) (2026) `Arxiv`

    > Evaluates LLM agents' ability to handle dynamic, evolving long contexts through simulated environment rollouts, exposing struggles with dynamic information synthesis despite proficiency at static retrieval.

- [LoCoBench-Agent: An Interactive Benchmark for LLM Agents in Long-Context Software Engineering](https://arxiv.org/abs/2511.13998) (2025) `Arxiv`

    > Evaluates LLM agents in realistic long-context software engineering workflows with multi-turn interactive conversations, tool usage, and error recovery across context lengths from 10K to 1M tokens.

- [MemoryRewardBench: Benchmarking Reward Models for Long-Term Memory Management in Large Language Models](https://arxiv.org/abs/2601.11969) (2026) `Arxiv`

    > Benchmarks 13 reward models on their ability to evaluate intermediate long-term memory management quality across 10 settings with context lengths from 8K to 128K tokens.

#### Reflection Stage

- [Minerva: A Programmable Memory Test Benchmark for Language Models](https://arxiv.org/abs/2502.03358) (2025) `Arxiv`

    > Offers programmable tasks to test whether models can follow precise memory read–write operations.

- [HaluMem: Evaluating Hallucinations in Memory Systems of Agents](https://arxiv.org/abs/2511.03506) (2025) `Arxiv`

    > Benchmarks how often and how severely agents hallucinate when reading or updating their memories.

- [Evaluating Memory in LLM Agents via Incremental Multi-Turn Interactions](https://arxiv.org/abs/2507.05257) (2025) `Arxiv`

    > Designs incremental multi-turn tasks to evaluate memory retention and update dynamics in agents.

- [Personalized Large Language Model Assistant with Evolving Conditional Memory](#) (2023) `*COLING`

    > Introduces datasets and setups for evaluating assistants with evolving, conditional personalized memory.

- [PersonaMem-v2: Towards Personalized Intelligence via Learning Implicit User Personas and Agentic Memory](#) (2025) `Arxiv`

    > Benchmarks systems that infer implicit user personas and maintain agentic memory for personalization.

- [Evaluating Very Long-Term Conversational Memory of LLM Agents](https://arxiv.org/abs/2402.17753) (2024) `Arxiv`

    > (Same paper) Used here as a reflection-stage benchmark of conversational memory consistency over time.

- [WebChoreArena: Evaluating Web Browsing Agents on Realistic Tedious Web Tasks](https://arxiv.org/abs/2506.01952) (2025) `Arxiv`

    > Benchmarks web agents on long, tedious tasks that require remembering intermediate states across pages.

- [On the Multi-Turn Instruction Following for Conversational Web Agents](#) (2024) `*ACL`

    > Evaluates whether web agents can follow instructions over many turns while maintaining relevant memory.

- [StoryBench: A Dynamic Benchmark for Evaluating Long-Term Memory with Multi Turns](https://arxiv.org/abs/2506.13356) (2025) `Arxiv`

    > Uses evolving stories to test agents’ ability to track and recall long-term narrative information.

- [PerLTQA: A Personal Long-Term Memory Dataset for Memory Classification, Retrieval, and Synthesis in Question Answering](https://arxiv.org/abs/2402.16288) (2024) `Arxiv`

    > Provides a dataset to benchmark classification, retrieval, and synthesis over personal long-term memories.

- [Toward Multi-Session Personalized Conversation: A Large-Scale Dataset and Hierarchical Tree Framework for Implicit Reasoning](https://arxiv.org/abs/2503.07018) (2025) `Arxiv`

    > Benchmarks multi-session dialogues that require implicit reasoning over long-lived user memory.

- [SHARE: Shared Memory-Aware Open-Domain Long-Term Dialogue Dataset Constructed from Movie Script](https://arxiv.org/abs/2410.20682) (2024) `Arxiv`

    > Builds a long-term dialogue dataset grounded in movie scripts to study shared memory among agents.

- [Mem-PAL: Towards Memory-Based Personalized Dialogue Assistants for Long-Term User-Agent Interaction](#) (2025) `Arxiv`

    > Provides benchmarks for personalized dialogue assistants that rely heavily on long-term memory.

- [Do LLMs Recognize Your Preferences? Evaluating Personalized Preference Following in LLMs](https://arxiv.org/abs/2502.09597) (2025) `Arxiv`

    > Evaluates how well LLMs remember and follow user preferences across interactions.

- [Do LLMs Predict Their Own Failures? Self-Awareness via Internal Circuits](https://arxiv.org/abs/2510.17132) (2025) `Arxiv`

    > Benchmarks self-awareness by testing whether models can anticipate failures rooted in their own memory limits.

- [ConvoMem Benchmark: Why Your First 150 Conversations Don't Need RAG](https://arxiv.org/abs/2511.10523) (2025) `Arxiv`

    > Benchmarks conversational memory with 75,336 QA pairs across user facts, assistant recall, preferences, and temporal changes, finding simple full-context approaches outperform RAG-based memory systems for early conversations.

- [KnowMe-Bench: Benchmarking Person Understanding for Lifelong Digital Companions](https://arxiv.org/abs/2601.04745) (2026) `Arxiv`

    > Benchmarks person understanding from long-form autobiographical narratives with evidence-linked questions spanning factual recall, subjective state attribution, and principle-level reasoning.

- [RealMem: Benchmarking LLMs in Real-World Memory-Driven Interaction](https://arxiv.org/abs/2601.06966) (2026) `Arxiv`

    > Benchmarks LLM memory systems in realistic long-term project-oriented interactions with over 2,000 cross-session dialogues, revealing struggles with dynamic state evolution and proactive contextual alignment.

- [StructMemEval: Evaluating Memory Structure in LLM Agents](https://arxiv.org/abs/2602.11243) (2026) `Arxiv`

    > Benchmarks LLM agents' ability to organize long-term memory into appropriate structures (ledgers, to-do lists, trees), finding that agents succeed only when explicitly prompted on structure.


#### Experience Stage

- [StreamBench: Towards Benchmarking Continuous Improvement of Language Agents](https://arxiv.org/abs/2406.08747) (2024) `Arxiv`

    > Benchmarks agents’ ability to improve over a stream of tasks, focusing on how experience accumulates as memory.

- [MemoryBench: A Benchmark for Memory and Continual Learning in LLM Systems](https://arxiv.org/abs/2510.17281) (2025) `Arxiv`

    > Provides standardized tasks and metrics for evaluating memory and continual learning in LLM systems.

- [Evo-Memory: Benchmarking LLM Agent Test-Time Learning with Self-Evolving Memory](#) (2025) `Arxiv`

    > Evaluates test-time learning setups where agents’ memories evolve during deployment.

- [LifelongAgentBench: Evaluating LLM Agents as Lifelong Learners](https://arxiv.org/abs/2505.11942) (2025) `Arxiv`

    > Benchmarks LLM agents on lifelong learning scenarios that stress long-term experience and memory reuse.

- [AMA-Bench: Evaluating Long-Horizon Memory for Agentic Applications](https://arxiv.org/abs/2602.22769) (2026) `Arxiv`

    > Benchmarks long-horizon memory systems for LLM agents in real agentic applications (web navigation, code editing, web search), revealing that existing systems underperform due to lack of causality-aware retrieval.

- [MEMTRACK: Evaluating Long-Term Memory and State Tracking in Multi-Platform Dynamic Agent Environments](https://arxiv.org/abs/2510.01353) (2025) `*NeurIPS Workshop`

    > Benchmarks long-term memory and state tracking across multi-platform enterprise environments (Slack, Linear, Git) with chronologically interleaved, noisy, conflicting information.

- [MemoryArena: Benchmarking Agent Memory in Interdependent Multi-Session Agentic Tasks](https://arxiv.org/abs/2602.16313) (2026) `Arxiv`

    > Evaluates agent memory in multi-session Memory-Agent-Environment loops with interdependent subtasks, revealing that agents with near-saturated performance on existing benchmarks perform poorly in agentic settings.

