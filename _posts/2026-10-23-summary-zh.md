---
layout: default
title: "Horizon Summary: 2026-10-23 (ZH)"
date: 2026-10-23
lang: zh
---

> 从 37 条内容中筛选出 9 条重要资讯。

---

**科技新闻**
1. [LLMs are making formal software verification feasible at a much larger scale](#item-tech-news-1) ⭐️ 9.0/10
2. [Today, we hacked what we&\#x27;d set out to hack: the iPhone](#item-tech-news-2) ⭐️ 8.0/10
3. [Kimi K3.1 Pro and K3.1 Pro Highspeed](#item-tech-news-3) ⭐️ 8.0/10
4. [OpenSSL 4.1.0](#item-tech-news-4) ⭐️ 8.0/10
5. [Donating Agent Skills to the Agentic AI Foundation](#item-tech-news-5) ⭐️ 8.0/10

**科技博客**
1. [vLLM 对 MiniMax-M3.1-Flash 的多平台内核优化](#item-tech-blog-1) ⭐️ 8.0/10
2. [软件性能瓶颈源于设计缺陷而非语言速度](#item-tech-blog-2) ⭐️ 8.0/10

**财经新闻**
1. [证监会核准花旗在上海设立全资证券公司](#item-finance-news-1) ⭐️ 8.0/10
2. [国办发文指导人工智能应用，强调就业友好](#item-finance-news-2) ⭐️ 8.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [LLMs are making formal software verification feasible at a much larger scale](https://www.anthropic.com/research/formal-verification) ⭐️ 9.0/10

Anthropic research demonstrates that LLMs make formal software verification feasible at a much larger scale, automating proof generation for critical software properties.

hackernews · johnbender · 10月22日 22:54 · [社区讨论](https://news.ycombinator.com/item?id=50202217)

**标签**: `#formal-verification`, `#llm-applications`, `#software-engineering`, `#systems-reliability`, `#ai-research`

---

<a id="item-tech-news-2"></a>
### [Today, we hacked what we&\#x27;d set out to hack: the iPhone](https://blog.calif.io/p/iphone) ⭐️ 8.0/10

A blog post details a successful security research effort that hacked an iPhone, leading to significant discussion about mobile security and exploit resilience.

hackernews · pavel\_lishin · 10月23日 16:21 · [社区讨论](https://news.ycombinator.com/item?id=50211474)

**标签**: `#Mobile Security`, `#Jailbreak`, `#Exploits`, `#iOS`

---

<a id="item-tech-news-3"></a>
### [Kimi K3.1 Pro and K3.1 Pro Highspeed](https://www.kimi.ai/blog/kimi-k3-1-pro) ⭐️ 8.0/10

Moonshot AI releases Kimi K3.1 Pro, a frontier-level model with intentional limitations on offensive cyber capabilities, now available with specific API pricing.

hackernews · Jowsey · 10月23日 16:59 · [社区讨论](https://news.ycombinator.com/item?id=50212065)

**标签**: `#AI Models`, `#LLM Release`, `#API Pricing`, `#Cybersecurity Policy`

---

<a id="item-tech-news-4"></a>
### [OpenSSL 4.1.0](https://github.com/openssl/openssl/releases/tag/openssl-4.1.0) ⭐️ 8.0/10

OpenSSL releases version 4.1.0, introducing DTLS 1.3 support and dropping legacy Windows targets, prompting community discussion about its timing relative to the ecosystem shift towards other SSL stacks.

hackernews · petecooper · 10月23日 12:42 · [社区讨论](https://news.ycombinator.com/item?id=50208099)

**标签**: `#OpenSSL`, `#Cryptographic Libraries`, `#Software Updates`, `#C Language`, `#Network Security`

---

<a id="item-tech-news-5"></a>
### [Donating Agent Skills to the Agentic AI Foundation](https://simonwillison.net/2026/Oct/22/donating-agent-skills/) ⭐️ 8.0/10

Anthropic has donated its Agent Skills standard to the Agentic AI Foundation to ensure the specification remains open and vendor-neutral.

rss · Simon Willison · 10月22日 18:09

**标签**: `#Agentic AI`, `#Standards`, `#Anthropic`, `#Open Source`

---

## 科技博客

<a id="item-tech-blog-1"></a>
### [vLLM 对 MiniMax-M3.1-Flash 的多平台内核优化](https://vllm.ai/blog/2026-10-23-minimax-m31-flash) ⭐️ 8.0/10

rss · vLLM Blog · 10月23日 00:00

**「背景」** MiniMax-M3.1-Flash 模型采用块稀疏注意力（MSA）、原生 NVFP4 KV 缓存及 DSpark 投机解码草案器。由于 NVFP4 量化格式缺乏通用的硬件张量核心指令支持，标准的低精度计算路径受阻，亟需针对特定硬件架构的底层内核级转换与调度优化。

**「方案」** vLLM 团队针对 NVIDIA 与 AMD 平台提供了多项内核级优化。在 Blackwell 架构上，利用 CUDA 13.4 的 QMUL4 指令实现 NVFP4 到 FP8 的快速反量化，结合提前释放 TMEM 的 MegaMoE 优化，显著降低计算延迟并提升预填充吞吐量。针对长上下文，团队引入解码器上下文并行（Indexer DCP），将稀疏索引工作分配至各 GPU 处理上下文分片以维持精确性。AMD 平台则利用预计算的查找表解决 NVFP4 反量化瓶颈，并通过 FlyDSL 实现 Mono kernel，将单层的近 1200 次内核启动合并为 1 次，从而大幅降低内核启动开销并提升低并发性能。

**「启示」** 通过针对前沿硬件架构（Blackwell/Rubin/MI350）的底层反量化指令映射与多批次并行调度优化，vLLM 成功实现了超低精度模型的 Day-0 支持，在极高并发与低延迟场景下显著提升了推理吞吐量与性价比。

**标签**: `#LLM Inference`, `#vLLM`, `#Kernel Optimization`, `#Hardware Acceleration`

---

<a id="item-tech-blog-2"></a>
### [软件性能瓶颈源于设计缺陷而非语言速度](https://seangoedecke.com/software-is-slow-because-of-bad-design-not-slow-languages/) ⭐️ 8.0/10

rss · Sean Goedecke · 10月23日 00:00

**「背景」** 当前主流观点认为 AI 可通过将代码重写为 C 或 Rust 等更快语言来显著提升软件性能，但这一假设忽略了系统优化的实际瓶颈分布，容易误导工程师将资源投入到低收益的语言迁移中。

**「方案」** 作者指出绝大多数实际程序是 I/O 密集型而非 CPU 密集型，例如 CRUD 网站中数据库查询占据约 50%的请求时间，根据阿姆达尔定律，重写其余 CPU 代码最多只能带来 1.5 至 2 倍加速，远非数量级提升；对于少数真正 CPU 密集型任务，现有慢语言（如 Python）已普遍通过调用 cmark-gfm 或 GPU 矩阵运算等高速库委托给 C/汇编实现优化，无需整体重写。作者强调，真正有效的加速来自程序重构设计：缓存外部 API 调用、将慢操作异步化、并行化顺序任务、修复 N+1 SQL 查询、用快查询替换慢查询、跳过非必要操作等。即使在使用熟练 C 语言的场景中，Bryan Cantrill 将 C 程序改写为 Rust 时，因 Rust 默认 B 树比二叉搜索树更缓存友好，反而获得 30%性能提升，证明数据结构和设计选择比语言本身更关键。慢语言还因可读性强更易识别瓶颈，重写为汇编反而增加优化难度。AI 代理应聚焦于剖析程序、定位热点并建议重构逻辑，而非盲目语言替换，仅在极少数无法通过减少工作量优化的 CPU 密集型热点才需局部语言重写。

**「启示」** 软件性能的根本杠杆在于算法与架构设计层面的工作量削减，语言选择仅是对原始速度的边际补充，优化实践应优先剖析重构而非语言迁移。

**标签**: `#performance-optimization`, `#software-design`, `#aamdahl-law`, `#i-o-bound`, `#systems-engineering`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [证监会核准花旗在上海设立全资证券公司](https://mp.weixin.qq.com/s/f_fCJUEObewqgAe5Ie7wHA) ⭐️ 8.0/10

10 月 23 日，中国证监会核准设立花旗证券（中国）有限公司，注册于上海，注册资本 12 亿元人民币，由花旗环球金融控股有限公司 100%出资。该公司业务涵盖证券经纪、咨询、承销保荐及自营。

telegram · zaihuapd · 10月23日 12:29

**「背景」** 这是花旗银行在中国设立的首家业务范围全面的外资控股证券公司，体现了中国金融领域对外开放的持续推进。

**「影响」** 该牌照的颁发将直接增加中国本土证券市场的国际竞争者，促使国内券商在经纪与投行业务方面提升服务能力。

**标签**: `#Financial Sector`, `#Market Access`, `#Regulation`, `#Foreign Investment`

---

<a id="item-finance-news-2"></a>
### [国办发文指导人工智能应用，强调就业友好](https://mp.weixin.qq.com/s/St8URoMYcV-voM7kLAK3Bw) ⭐️ 8.0/10

国务院办公厅印发关于构建就业友好型发展方式的文件，要求减缓人工智能应用对就业的替代影响。该文件指导企业优先在劳动力紧缺和高风险岗位推广 AI，并探索失业缓冲机制。

telegram · zaihuapd · 10月23日 12:54

**「政策背景」** 国务院办公厅近日印发《关于适应人工智能技术发展助力构建就业友好型发展方式的意见》，旨在通过政策指导缓解 AI 技术对就业市场的冲击，推动建立“就业友好型”的发展方式。

**「受影响群体」** 这一政策直接影响劳动密集型行业的从业者，企业将提前告知受影响的劳动者并提供转岗支持，同时调整在 AI 部署上的策略。

**标签**: `#Labor Policy`, `#Artificial Intelligence`, `#Macroeconomics`, `#Corporate Strategy`, `#Regulation`

---