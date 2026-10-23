---
layout: default
title: "Horizon Summary: 2026-10-23 (EN)"
date: 2026-10-23
lang: en
---

> From 37 items, 9 important content pieces were selected

---

**Technology News**
1. [LLMs are making formal software verification feasible at a much larger scale](#item-tech-news-1) ⭐️ 9.0/10
2. [Today, we hacked what we&\#x27;d set out to hack: the iPhone](#item-tech-news-2) ⭐️ 8.0/10
3. [Kimi K3.1 Pro and K3.1 Pro Highspeed](#item-tech-news-3) ⭐️ 8.0/10
4. [OpenSSL 4.1.0](#item-tech-news-4) ⭐️ 8.0/10
5. [Donating Agent Skills to the Agentic AI Foundation](#item-tech-news-5) ⭐️ 8.0/10

**Technology Blog**
1. [vLLM Day-0 Support for MiniMax-M3.1-Flash: NVFP4 and Sparse Attention Optimizations](#item-tech-blog-1) ⭐️ 8.0/10
2. [Performance Gains Come from Design, Not Language Rewrites](#item-tech-blog-2) ⭐️ 8.0/10

**Financial News**
1. [CSRC Approves Citibank&\#x27;s Full-Scope Securities Firm in China](#item-finance-news-1) ⭐️ 8.0/10
2. [China orders slower AI rollout in labor-heavy jobs to ease displacement](#item-finance-news-2) ⭐️ 8.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [LLMs are making formal software verification feasible at a much larger scale](https://www.anthropic.com/research/formal-verification) ⭐️ 9.0/10

Anthropic research demonstrates that LLMs make formal software verification feasible at a much larger scale, automating proof generation for critical software properties.

hackernews · johnbender · Oct 22, 22:54 · [Discussion](https://news.ycombinator.com/item?id=50202217)

**Tags**: `#formal-verification`, `#llm-applications`, `#software-engineering`, `#systems-reliability`, `#ai-research`

---

<a id="item-tech-news-2"></a>
### [Today, we hacked what we&\#x27;d set out to hack: the iPhone](https://blog.calif.io/p/iphone) ⭐️ 8.0/10

A blog post details a successful security research effort that hacked an iPhone, leading to significant discussion about mobile security and exploit resilience.

hackernews · pavel\_lishin · Oct 23, 16:21 · [Discussion](https://news.ycombinator.com/item?id=50211474)

**Tags**: `#Mobile Security`, `#Jailbreak`, `#Exploits`, `#iOS`

---

<a id="item-tech-news-3"></a>
### [Kimi K3.1 Pro and K3.1 Pro Highspeed](https://www.kimi.ai/blog/kimi-k3-1-pro) ⭐️ 8.0/10

Moonshot AI releases Kimi K3.1 Pro, a frontier-level model with intentional limitations on offensive cyber capabilities, now available with specific API pricing.

hackernews · Jowsey · Oct 23, 16:59 · [Discussion](https://news.ycombinator.com/item?id=50212065)

**Tags**: `#AI Models`, `#LLM Release`, `#API Pricing`, `#Cybersecurity Policy`

---

<a id="item-tech-news-4"></a>
### [OpenSSL 4.1.0](https://github.com/openssl/openssl/releases/tag/openssl-4.1.0) ⭐️ 8.0/10

OpenSSL releases version 4.1.0, introducing DTLS 1.3 support and dropping legacy Windows targets, prompting community discussion about its timing relative to the ecosystem shift towards other SSL stacks.

hackernews · petecooper · Oct 23, 12:42 · [Discussion](https://news.ycombinator.com/item?id=50208099)

**Tags**: `#OpenSSL`, `#Cryptographic Libraries`, `#Software Updates`, `#C Language`, `#Network Security`

---

<a id="item-tech-news-5"></a>
### [Donating Agent Skills to the Agentic AI Foundation](https://simonwillison.net/2026/Oct/22/donating-agent-skills/) ⭐️ 8.0/10

Anthropic has donated its Agent Skills standard to the Agentic AI Foundation to ensure the specification remains open and vendor-neutral.

rss · Simon Willison · Oct 22, 18:09

**Tags**: `#Agentic AI`, `#Standards`, `#Anthropic`, `#Open Source`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [vLLM Day-0 Support for MiniMax-M3.1-Flash: NVFP4 and Sparse Attention Optimizations](https://vllm.ai/blog/2026-10-23-minimax-m31-flash) ⭐️ 8.0/10

rss · vLLM Blog · Oct 23, 00:00

**「Background」** The MiniMax-M3.1-Flash model family prioritizes inference efficiency by replacing full attention with MiniMax Sparse Attention \(MSA\), which limits each query to the top 16 key-value blocks, and by natively quantizing the KV cache and Mixture-of-Experts \(MoE\) weights to NVFP4. This architectural shift significantly reduces memory bandwidth demands and checkpoint size compared to previous generations, but it requires specialized, precision-specific kernel optimizations to achieve peak performance across diverse hardware stacks.

**「Solution」** vLLM implemented day-0 support by developing a suite of hardware-specific kernels that bypass standard data type limitations. On NVIDIA Blackwell, kernels utilize the CUDA 13.4 QMUL4 instruction to dequantize NVFP4 data into FP8 in-kernel, accelerating the indexer and sparse attention decodes by up to 1.7× and 1.3× respectively. The NVFP4 MegaMoE extension introduces early TMEM release in the FC1 epilogue, reducing prefill latency by 20% and increasing throughput by 7%. To address long-context bottlenecks, Indexer Decode Context Parallelism \(DCP\) splits the scoring workload across GPUs, improving indexer speed by up to 3.3× at 512K contexts on 4× GB300s. For AMD MI350-series hardware, the absence of native NVFP4 dequantization is resolved via a 2 KB table lookup in local data share \(LDS\), while a single-launch mono kernel and sequence parallelism with dual-batch overlap reduce kernel launch overhead and communication traffic, yielding up to 2.5× faster sparse decode attention and doubling low-concurrency throughput. Additionally, a unified QKV GEMM, normalization, RoPE, and KV-insertion kernel on NVIDIA GPUs reduces time-to-first-token by 19%, and the DSpark speculative drafter is accelerated by 1.3–2× using the FlashInfer PrimiTS backend.

**「Takeaway」** The successful day-0 deployment of MiniMax-M3.1-Flash demonstrates that integrating model-specific quantization schemes like NVFP4 into LLM inference engines demands bespoke, hardware-aware kernel engineering rather than generic data type swaps. This alignment of model architecture with underlying GPU compute resources is essential for realizing the full memory bandwidth and throughput benefits of modern sparse and quantized models.

**Tags**: `#LLM Inference`, `#vLLM`, `#Kernel Optimization`, `#Hardware Acceleration`

---

<a id="item-tech-blog-2"></a>
### [Performance Gains Come from Design, Not Language Rewrites](https://seangoedecke.com/software-is-slow-because-of-bad-design-not-slow-languages/) ⭐️ 8.0/10

rss · Sean Goedecke · Oct 23, 00:00

**「Background」** A prevailing narrative suggests that AI agents can significantly accelerate software by rewriting it in faster languages like C or Rust. However, real-world programs are typically I/O-bound, spending most of their execution time waiting on databases, networks, or disk, which places a hard ceiling on the potential speedup offered by language-specific CPU efficiency.

**「Solution」** Goedecke argues that performance is fundamentally a matter of design rather than language choice, a conclusion supported by Amdahl’s law. In a typical CRUD application where 50% of time is spent on database queries, rewriting in C only optimizes the remaining computational time, capping the speedup at roughly 1.5x to 2x rather than an order of magnitude. Furthermore, modern slow languages already bridge this gap by delegating CPU-intensive tasks to highly optimized C or assembly libraries, meaning even language-specific bottlenecks are often already mitigated by ecosystem tooling. The author highlights a 2018 anecdote from Bryan Cantrill, where a naive Rust implementation outperformed a hand-optimized C program by 30% purely because of a better data structure choice \(a B-tree over a binary search tree\). Consequently, significant speedups are achieved through architectural redesigns such as fixing N+1 queries, caching external API calls, and parallelizing operations. Goedecke suggests that AI agents should focus on profiling hotspots and suggesting these design-level changes, with language rewrites reserved for the rare, unfixable CPU-bound core.

**「Takeaway」** Blind rewrites in faster languages yield only marginal returns because software performance is dominated by I/O constraints and architectural inefficiencies rather than language speed. Meaningful optimization requires redesigning the program to do less work or access data more effectively, a task better suited to algorithmic and structural analysis than wholesale language translation.

**Tags**: `#performance-optimization`, `#software-design`, `#aamdahl-law`, `#i-o-bound`, `#systems-engineering`

---

## Financial News

<a id="item-finance-news-1"></a>
### [CSRC Approves Citibank&\#x27;s Full-Scope Securities Firm in China](https://mp.weixin.qq.com/s/f_fCJUEObewqgAe5Ie7wHA) ⭐️ 8.0/10

China&\#x27;s securities regulator \(CSRC\) approved the creation of Citibank Securities \(China\), a 100%-owned foreign unit in Shanghai. The firm will hold RMB 1.2 billion in registered capital and is licensed for securities brokerage, investment advice, underwriting, and proprietary trading.

telegram · zaihuapd · Oct 23, 12:29

**「Background」** This is a regulatory permission from China&\#x27;s main securities authority; “full-scope” means the firm can offer core investment banking services without waiting for separate permits.

**「Impact」** Domestic securities firms will face a new foreign competitor, and Chinese investors gain direct access to a major international broker for listed-trading and corporate-issuance work.

**Tags**: `#Financial Sector`, `#Market Access`, `#Regulation`, `#Foreign Investment`

---

<a id="item-finance-news-2"></a>
### [China orders slower AI rollout in labor-heavy jobs to ease displacement](https://mp.weixin.qq.com/s/St8URoMYcV-voM7kLAK3Bw) ⭐️ 8.0/10

China’s State Council issued a new opinion on Oct. 23 to slow job losses from AI, mandating that employers prioritize deploying it in high-risk or labor-short roles rather than in labor-intensive industries. The policy requires companies to set up “unemployment buffer periods,” notify affected workers in advance, and provide transition support or retraining.

telegram · zaihuapd · Oct 23, 12:54

**「Background」** China’s central government had not previously issued a coordinated, national-level policy that specifically directs AI deployment to protect employment, leaving individual firms and local authorities to manage job displacement risks largely on their own.

**「Impact」** The policy creates a regulatory and operational shift for major Chinese tech firms and industries that deploy AI, specifically altering deployment strategies and compliance requirements in labor-intensive sectors to reduce immediate workforce displacement.

<details><summary>References</summary>
<ul>
<li><a href="https://www.gov.cn/gongbao/content/2011/content_1816011.htm">gov.cn/gongbao/content/2011/content_1816011.htm</a></li>
<li><a href="https://www.renmtrade.com/html/ghzj1618201803261086297.html">renmtrade.com/html/ghzj1618201803261086297.html</a></li>

</ul>
</details>

**Tags**: `#Labor Policy`, `#Artificial Intelligence`, `#Macroeconomics`, `#Corporate Strategy`, `#Regulation`

---