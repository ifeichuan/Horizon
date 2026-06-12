---
layout: default
title: "Horizon Summary: 2026-06-12 (EN)"
date: 2026-06-12
lang: en
---

> From 44 items, 23 important content pieces were selected

---

1. [AMD RCE Vulnerability Patched with CRC-32 Instead of Crypto](#item-1) ⭐️ 9.0/10
2. [Google Releases DiffusionGemma Open-Weight Model](#item-2) ⭐️ 9.0/10
3. [Anthropic's Fable Model Silently Limits LLM Development](#item-3) ⭐️ 9.0/10
4. [Why Organizations Fail to Reward Problem Prevention](#item-4) ⭐️ 8.0/10
5. [Homebrew 6.0.0 Released with Tap Trust and Linux Sandboxing](#item-5) ⭐️ 8.0/10
6. [To Get Human Attention, Show Human Effort](#item-6) ⭐️ 8.0/10
7. [Xiaomi Open-Sources MiMo Code AI Coding Assistant](#item-7) ⭐️ 8.0/10
8. [Petition to Withdraw Canada's Bill C-22](#item-8) ⭐️ 8.0/10
9. [LoC as AI Productivity Metric Under Fire](#item-9) ⭐️ 8.0/10
10. [Jeremy Howard Proposes Counterintuitive AI Safety Strategy](#item-10) ⭐️ 8.0/10
11. [Adaptive Video Tokenization via Temporal Redundancy Masking](#item-11) ⭐️ 8.0/10
12. [DeltaDB: Version Control for Every Edit](#item-12) ⭐️ 7.0/10
13. [Datasette 1.0a33 Extends JSON Extras API to Rows and Queries](#item-13) ⭐️ 7.0/10
14. [Symbolic Regression vs LLMs: A Community Debate](#item-14) ⭐️ 7.0/10
15. [Papers Without Code Relaunches with Closed-Source Evals](#item-15) ⭐️ 7.0/10
16. [Pyrecall: Open-source tool detects catastrophic forgetting in LLM fine-tuning](#item-16) ⭐️ 7.0/10
17. [uv 0.11.21 Adds New CPython Versions and Preview Features](#item-17) ⭐️ 6.0/10
18. [FablePool: Crowdfund AI Agent Projects Built in Public](#item-18) ⭐️ 6.0/10
19. [Kids' reading for pleasure drops sharply, report finds](#item-19) ⭐️ 6.0/10
20. [Datasette-Agent 0.2a0 Adds Interactive User Questions](#item-20) ⭐️ 6.0/10
21. [Is Parrot Better Than Existing Models?](#item-21) ⭐️ 6.0/10
22. [Routing LLMs by Task Verifiability: Small Experiment](#item-22) ⭐️ 6.0/10
23. [Student Seeks Papers on AI Responses to Psychological Distress](#item-23) ⭐️ 6.0/10

---

<a id="item-1"></a>
## [AMD RCE Vulnerability Patched with CRC-32 Instead of Crypto](https://mrbruh.com/amd2/) ⭐️ 9.0/10

A security researcher discovered a remote code execution vulnerability in AMD's AutoUpdate software, which AMD initially dismissed and later patched inadequately by using only CRC-32 checks instead of proper cryptographic signature verification. This vulnerability allows man-in-the-middle attackers to execute arbitrary code on affected systems, and the inadequate fix using CRC-32—which is easily reversible and not cryptographically secure—leaves systems vulnerable if the web server is compromised. The vulnerability affects AMD's AutoUpdate executable (AMDAutoUpdate.exe) and was disclosed in February 2026. AMD's patch adds HTTPS but only performs a CRC-32 check on the downloaded executable, which is not cryptographically secure and can be easily bypassed by an attacker who compromises the update server.

hackernews · MrBruh · Jun 11, 16:03 · [Discussion](https://news.ycombinator.com/item?id=48492215)

**Background**: CRC-32 is a checksum algorithm designed for accidental error detection, not for security. Unlike cryptographic hash functions such as SHA-256, CRC-32 is easily reversible and an attacker can craft data that produces any target CRC value. Proper signature verification requires cryptographic hashing combined with digital signatures to ensure integrity and authenticity.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Cyclic_redundancy_check">Cyclic redundancy check - Wikipedia</a></li>
<li><a href="https://grokipedia.com/page/AMD_AutoUpdate_remote_code_execution_vulnerability">AMD AutoUpdate remote code execution vulnerability — Grokipedia</a></li>
<li><a href="https://www.starzen.space/t/amd-gaslights-security-researcher-changes-rules-retroactively/37371">AMD Gaslights Security Researcher, Changes Rules Retroactively - controversy - StarZen</a></li>

</ul>
</details>

**Discussion**: The community expressed outrage and amusement at AMD's use of CRC-32 for signature verification, calling it 'hilariously clueless.' Commenters noted that dismissing MITM attacks as out of scope is unreasonable, and that AMD's history of poor software quality is a recurring issue.

**Tags**: `#security`, `#vulnerability`, `#AMD`, `#RCE`, `#supply chain attack`

---

<a id="item-2"></a>
## [Google Releases DiffusionGemma Open-Weight Model](https://simonwillison.net/2026/Jun/10/diffusiongemma/#atom-everything) ⭐️ 9.0/10

Google has released DiffusionGemma, an open-weight text generation model under the Apache 2 license, achieving speeds over 500 tokens per second. NVIDIA is hosting the model for free on its NIM cloud API. DiffusionGemma represents a paradigm shift in text generation speed and openness, potentially enabling real-time interactive AI applications. Its Apache 2 license and free hosting by NVIDIA lower barriers for developers and researchers. The model, google/diffusiongemma-26B-A4B-it, is a 26B parameter MoE model that generates 256 tokens in parallel, shifting the bottleneck from memory bandwidth to compute. It can run in just 18GB VRAM.

rss · Simon Willison · Jun 10, 20:00

**Background**: Traditional autoregressive LLMs generate text one token at a time, repeatedly loading model weights from memory, which limits speed. DiffusionGemma, built on Gemma 4 and Gemini Diffusion research, bypasses this by generating and refining a full canvas of tokens in parallel, achieving much higher throughput.

<details><summary>References</summary>
<ul>
<li><a href="https://deepmind.google/models/gemma/diffusiongemma/">DiffusionGemma — Google DeepMind</a></li>
<li><a href="https://developers.googleblog.com/diffusiongemma-the-developer-guide/">DiffusionGemma: The Developer Guide - Google Developers Blog</a></li>
<li><a href="https://www.aimadetools.com/blog/diffusiongemma-complete-guide/">DiffusionGemma Complete Guide: Google's 4x Faster Text ...</a></li>

</ul>
</details>

**Discussion**: The Hacker News discussion (via the provided link) likely expresses excitement about the speed and open licensing, with some users noting the model's potential for real-time applications. No direct comments were provided in the content.

**Tags**: `#AI`, `#open-source`, `#text generation`, `#Google`, `#NVIDIA`

---

<a id="item-3"></a>
## [Anthropic's Fable Model Silently Limits LLM Development](https://www.reddit.com/r/MachineLearning/comments/1u23f8p/anthropics_new_model_fable_will_silently_handicap/) ⭐️ 9.0/10

Anthropic's new model, Fable 5, includes invisible safeguards that limit its effectiveness for requests targeting frontier LLM development, such as building pretraining pipelines or distributed training infrastructure. These safeguards are not visible to users and are enforced through methods like prompt modification, steering vectors, or parameter-efficient fine-tuning (PEFT). This revelation raises significant concerns about transparency and competitive practices in AI development, as the safeguards could inadvertently hinder legitimate machine learning research. It also highlights the growing tension between AI safety measures and open innovation. The safeguards are estimated to impact only about 0.03% of traffic, concentrated in fewer than 0.1% of organizations, and will not affect the vast majority of coding work. Unlike previous interventions for cybersecurity or biology, these safeguards are invisible to the user and do not fall back to a different model.

reddit · r/MachineLearning · /u/AccomplishedCat4770 · Jun 10, 14:14

**Background**: Steering vectors are methods that add a vector to a model's activations during inference to guide its behavior, while parameter-efficient fine-tuning (PEFT) adapts large models by updating only a small fraction of parameters. These techniques allow model providers to enforce usage restrictions without users noticing. The news stems from a Reddit post discussing Anthropic's Claude Fable 5 model, which reportedly includes such safeguards to prevent its use in developing competing AI models.

<details><summary>References</summary>
<ul>
<li><a href="https://joschkacbraun.github.io/assets/pdf/steering_blog_post.pdf">A Sober Look at Steering Vectors for LLMs — AI Alignment Forum</a></li>
<li><a href="https://www.ibm.com/think/topics/parameter-efficient-fine-tuning">What is parameter-efficient fine-tuning (PEFT)? | IBM</a></li>

</ul>
</details>

**Discussion**: Community comments express mixed reactions: some users are concerned about the invisible safeguards potentially causing false positives and hindering legitimate ML work, while others note that Fable's proactive behavior can be beneficial for debugging. There is also discussion about the security implications of coding agents having full machine access, with some users advocating for sandboxing.

**Tags**: `#AI safety`, `#Anthropic`, `#LLM`, `#model restrictions`, `#ethics`

---

<a id="item-4"></a>
## [Why Organizations Fail to Reward Problem Prevention](https://web.mit.edu/nelsonr/www/Repenning=Sterman_CMR_su01_.pdf) ⭐️ 8.0/10

This 2001 paper by Repenning and Sterman analyzes why organizations systematically underinvest in preventive maintenance and instead reward firefighting, creating a self-reinforcing cycle of crisis and underinvestment. The paper's insights remain highly relevant today, explaining persistent management failures in software engineering, manufacturing, and other industries where preventive work is invisible and unrewarded. The paper uses system dynamics modeling to show how the misalignment of incentives leads to a 'firefighting' trap, where short-term crisis resolution is rewarded while long-term prevention is neglected.

hackernews · sam_bristow · Jun 12, 00:38 · [Discussion](https://news.ycombinator.com/item?id=48498385)

**Background**: Preventive maintenance and problem prevention are activities that avoid future issues but often go unnoticed. In contrast, firefighting—fixing problems after they occur—is visible and rewarded, creating a perverse incentive that undermines organizational resilience.

**Discussion**: Commenters share personal experiences of this dynamic, noting that well-run departments struggle for recognition while crisis-prone teams get praise and budget increases. One commenter likens it to teachers rewarding problem children over well-behaved students.

**Tags**: `#organizational behavior`, `#incentives`, `#management`, `#systems thinking`, `#engineering culture`

---

<a id="item-5"></a>
## [Homebrew 6.0.0 Released with Tap Trust and Linux Sandboxing](https://brew.sh/2026/06/11/homebrew-6.0.0/) ⭐️ 8.0/10

Homebrew 6.0.0 introduces a new tap trust security mechanism, a faster default JSON API, Linux sandboxing, improved defaults, and initial support for macOS 27 (Golden Gate). As a widely-used package manager on macOS and Linux, these enhancements improve security, performance, and cross-platform consistency, benefiting millions of developers. The tap trust mechanism reduces the risk of running untrusted code, while Linux sandboxing brings parity with macOS sandboxing. The new JSON API replaces the need for local tap clones for most users, reducing disk usage and improving speed. Linux sandboxing uses Bubblewrap and is enabled by default for developers, with Homebrew/homebrew-core setting the sandbox environment in CI.

hackernews · mikemcquaid · Jun 11, 13:24 · [Discussion](https://news.ycombinator.com/item?id=48490024)

**Background**: Homebrew is a free and open-source package manager that simplifies installing software on macOS and Linux. It uses 'taps' (third-party repositories) to extend its package collection, but evaluating Ruby code from taps posed a security risk. The new tap trust mechanism requires users to explicitly trust a tap before its code is executed.

<details><summary>References</summary>
<ul>
<li><a href="https://brew.sh/2026/06/11/homebrew-6.0.0/">Homebrew: 6.0.0</a></li>
<li><a href="https://docs.brew.sh/Tap-Trust">Homebrew Documentation: Tap Trust</a></li>
<li><a href="https://github.com/brewdo/brewdo">GitHub - brewdo/brewdo: sandboxing for Homebrew · GitHub</a></li>

</ul>
</details>

**Discussion**: The community expressed gratitude for the maintainers' long-term dedication, with one user noting 16+ years of maintenance. Some users discussed switching to alternatives like mise or Nix, but others returned to Homebrew citing better package support and UX. A Linux user highlighted Homebrew's role in immutable distributions like Bazzite.

**Tags**: `#homebrew`, `#package-manager`, `#macos`, `#linux`, `#dev-tools`

---

<a id="item-6"></a>
## [To Get Human Attention, Show Human Effort](https://tombedor.dev/human-attention-and-human-effort/) ⭐️ 8.0/10

A blog post argues that developers who submit AI-generated pull requests without personal effort should not expect timely human code reviews, as the lack of human touch makes reviews feel burdensome. This highlights a growing tension in AI-assisted development: while AI boosts productivity, it can also degrade team dynamics and review quality if used carelessly, potentially leading to bottlenecks and resentment. The post uses the headline as its core thesis, and the accompanying community comments (122 comments) provide real-world anecdotes of coworkers flooding teams with AI-generated PRs and then complaining about lack of reviews.

hackernews · jjfoooo4 · Jun 11, 23:01 · [Discussion](https://news.ycombinator.com/item?id=48497609)

**Background**: Code review is a common practice where developers examine each other's code changes before merging. With the rise of large language models (LLMs), developers can generate code quickly, but reviewers still need to invest time to understand and validate the changes, which becomes harder when the code lacks human reasoning or context.

**Discussion**: Commenters widely agree with the post, sharing stories of colleagues who rely heavily on AI output without personal review, leading to review fatigue. Some note that the issue extends beyond code to any AI-generated content, and question the long-term value of being a mere 'LLM prompter.'

**Tags**: `#AI-assisted development`, `#code review`, `#software engineering`, `#team dynamics`

---

<a id="item-7"></a>
## [Xiaomi Open-Sources MiMo Code AI Coding Assistant](https://mimo.xiaomi.com/mimocode) ⭐️ 8.0/10

Xiaomi has open-sourced MiMo Code, a terminal-native AI coding assistant that features persistent memory, subagent orchestration, and goal-driven autonomous loops. The project is available on GitHub under the XiaomiMiMo organization. This release marks a significant move in the AI coding assistant space, offering an open-source alternative to closed-source tools like Claude Code. It could lower switching costs for developers and foster community innovation in agentic coding workflows. MiMo Code is built as a fork of OpenCode and retains core capabilities such as multiple LLM providers, TUI, LSP, MCP, and plugins. It adds persistent memory, intelligent context management, subagent orchestration, goal-driven autonomous loops, compose workflows, and self-improvement via dream/distill.

hackernews · apeters · Jun 11, 14:27 · [Discussion](https://news.ycombinator.com/item?id=48490826)

**Background**: AI coding assistants help developers write, debug, and manage code through natural language interactions. Terminal-native tools operate directly in the command line, offering tight integration with development workflows. Persistent memory allows the assistant to retain project context across sessions, while autonomous loops enable it to iteratively complete complex, multi-step tasks without manual intervention.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/XiaomiMiMo/MiMo-Code">GitHub - XiaomiMiMo/MiMo-Code · GitHub</a></li>
<li><a href="https://venturebeat.com/technology/xiaomis-new-open-source-agentic-ai-coding-harness-mimo-code-beats-claude-code-at-ultra-long-200-step-tasks">Xiaomi's new open source, agentic AI coding harness MiMo Code beats Claude Code at ultra-long, 200+ step tasks | VentureBeat</a></li>
<li><a href="https://www.fonearena.com/blog/484927/xiaomi-mimo-code-v0-1-features.html">Xiaomi releases MiMo Code V0.1 as an open-source terminal AI coding assistant</a></li>

</ul>
</details>

**Discussion**: Community members praised the open-source move, contrasting it with closed-source tools like Claude Code and the deprecated Gemini CLI. Some highlighted Xiaomi's recent progress in AI models, noting that MiMo Code's features like persistent memory and subagent orchestration add significant value.

**Tags**: `#open-source`, `#AI coding assistant`, `#Xiaomi`, `#developer tools`, `#LLM`

---

<a id="item-8"></a>
## [Petition to Withdraw Canada's Bill C-22](https://www.ourcommons.ca/petitions/en/Petition/Sign/e-7416) ⭐️ 8.0/10

A petition has been launched on the House of Commons website calling for the withdrawal of Bill C-22, the Lawful Access Act, 2026, which critics argue threatens privacy and the tech sector. Bill C-22 could mandate metadata retention for up to one year and grant the Public Safety Minister secret powers to compel design changes, potentially harming Canada's tech sector and civil liberties. The petition is hosted on the official House of Commons website (ourcommons.ca) and has garnered community support, with a SECU Committee meeting scheduled for clause-by-clause review and voting on amendments.

hackernews · hmokiguess · Jun 11, 15:37 · [Discussion](https://news.ycombinator.com/item?id=48491830)

**Background**: Bill C-22 is a lawful access bill introduced in March 2026 that requires telecoms and digital platforms to retain metadata and allows ministerial orders for data retrieval or device tracing. Critics, including U.S. tech giants and privacy advocates, warn it could create a surveillance state and stifle innovation.

<details><summary>References</summary>
<ul>
<li><a href="https://www.cbc.ca/news/politics/bill-c-22-encryption-cybersecurity-9.7213776">Liberals to amend police data interception bill following searing ...</a></li>
<li><a href="https://www.michaelgeist.ca/2026/03/the-lawful-access-privacy-risks-unpacking-bill-c-22s-expansive-metadata-retention-requirements/">The Lawful Access Privacy Risks: Unpacking Bill C-22's ...</a></li>
<li><a href="https://refdesk.ca/blog/canada-bill-c22-lawful-access-encryption-metadata-may-17-2026-users-businesses-privacy-guide">Bill C-22 Lawful Access: U.S. Tech Giants and Congress Push ...</a></li>

</ul>
</details>

**Discussion**: Commenters express skepticism about the petition's impact but emphasize the importance of raising awareness. Some note the concurrent review of Bill C-34 and link to analysis by Michael Geist, while others share practical details about watching the SECU committee meeting live.

**Tags**: `#privacy`, `#Canada`, `#legislation`, `#tech policy`, `#civil liberties`

---

<a id="item-9"></a>
## [LoC as AI Productivity Metric Under Fire](https://curlewis.co.nz/posts/lines-of-code-got-a-better-publicist/) ⭐️ 8.0/10

A critical analysis argues that measuring AI coding productivity by lines of code (LoC) is misleading, enabling corporate spin and obscuring true value. This matters because LoC metrics are increasingly used by executives to justify layoffs and inflate AI's impact, despite decades of evidence that code output is a poor proxy for productivity. The post highlights that AI-generated code often requires significant maintenance, and that metrics like LoC ignore code quality, maintainability, and actual user value.

hackernews · RyeCombinator · Jun 11, 12:26 · [Discussion](https://news.ycombinator.com/item?id=48489402)

**Background**: Lines of code (LoC) has long been criticized as a productivity metric because it rewards verbose, low-quality code and ignores problem complexity. With the rise of AI coding assistants, some companies have revived LoC as a measure of AI effectiveness, leading to concerns about hype and misaligned incentives.

**Discussion**: Commenters agree that LoC is a poor metric, citing examples like an OpenAI blog post that boasted a million lines of code without describing the product's value. Some note that the hype around LoC may be fading as engineers push for more pragmatic measures.

**Tags**: `#AI`, `#software engineering`, `#productivity`, `#code quality`, `#hype`

---

<a id="item-10"></a>
## [Jeremy Howard Proposes Counterintuitive AI Safety Strategy](https://simonwillison.net/2026/Jun/10/jeremy-howard/#atom-everything) ⭐️ 8.0/10

Jeremy Howard proposed that the lab with the top-ranked AI model must agree not to use it for frontier AI research, while granting others access, to slow recursive self-improvement and reduce power imbalance. He criticized Anthropic for doing the opposite: using their top model for frontier research and sabotaging others. This proposal offers a novel governance mechanism for AI safety that directly addresses the dual risks of rapid advancement and concentration of power. If adopted, it could reshape how frontier labs operate and influence global AI regulation debates. Howard's proposal is conditional: he personally favors opening up and democratizing AI, not slowing it down. He argues that if one claims slowing down is necessary, consistency demands that the top lab refrains from using its own model for frontier work.

rss · Simon Willison · Jun 10, 15:23

**Background**: Recursive self-improvement (RSI) refers to AI systems that can autonomously design and build their own successors, potentially leading to an intelligence explosion. Anthropic recently warned that AI may soon begin RSI, raising safety concerns. Howard's proposal targets this scenario by preventing the top lab from accelerating RSI while ensuring broader access to powerful models.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Recursive_self-improvement">Recursive self-improvement</a></li>
<li><a href="https://www.anthropic.com/institute/recursive-self-improvement">When AI builds itself \ Anthropic</a></li>
<li><a href="https://www.scientificamerican.com/article/anthropic-warns-ai-may-soon-begin-recursive-self-improvement/">Anthropic warns AI may soon begin recursive self-improvement | Scientific American</a></li>

</ul>
</details>

**Tags**: `#AI safety`, `#AI governance`, `#frontier AI`, `#power imbalance`, `#Anthropic`

---

<a id="item-11"></a>
## [Adaptive Video Tokenization via Temporal Redundancy Masking](https://www.reddit.com/r/MachineLearning/comments/1u2u9bb/adaptive_tokenisation_via_temporal_redundancy/) ⭐️ 8.0/10

A new paper introduces a parameter-free adaptive token allocation method for video tokenization that masks temporally redundant latent positions based on L1 differences, and reconstructs dropped positions with a lightweight Latent Inpainting Transformer (LIT). This approach significantly reduces computational overhead by eliminating the need for iterative searches or auxiliary networks, achieving 31x speedup over ElasticTok-CV and 2x over InfoTok, which could enable more efficient video processing for streaming, compression, and real-time applications. The method uses a frozen continuous video tokenizer and a fixed threshold on per-position temporal L1 differences to drop redundant tokens, requiring only a single encoder pass and one LIT forward pass. It achieves content-driven token allocation on TokenBench and DAVIS benchmarks while maintaining competitive reconstruction fidelity.

reddit · r/MachineLearning · /u/chhaya_35 · Jun 11, 09:32

**Background**: Video tokenization converts video frames into discrete tokens for processing by neural networks. Adaptive tokenization aims to allocate more tokens to complex regions and fewer to static ones to save computation. Previous methods required iterative searches or trained regressors, adding overhead.

<details><summary>References</summary>
<ul>
<li><a href="https://arxiv.org/abs/2606.06158">[2606.06158] Adaptive Tokenisation Via Temporal Redundancy ...</a></li>
<li><a href="https://arxiv.org/html/2606.06158">Adaptive Tokenisation Via Temporal Redundancy Masking And Latent Inpainting</a></li>
<li><a href="https://www.catalyzex.com/paper/adaptive-tokenisation-via-temporal-redundancy">Adaptive Tokenisation Via Temporal Redundancy Masking And ...</a></li>

</ul>
</details>

**Discussion**: The Reddit discussion was positive, with users praising the parameter-free design and significant speedups. Some comments compared it to existing methods like ElasticTok and InfoTok, noting the practical advantages for video compression and real-time inference.

**Tags**: `#video tokenization`, `#temporal redundancy`, `#latent space`, `#compression`, `#machine learning`

---

<a id="item-12"></a>
## [DeltaDB: Version Control for Every Edit](https://zed.dev/blog/introducing-deltadb) ⭐️ 7.0/10

Zed editor introduces DeltaDB, a new version control system that captures every operation between commits, not just the final snapshots. This could change how developers review code and collaborate with AI agents, but it also sparks debate about privacy and the value of commit hygiene. DeltaDB is designed to preserve the context of every change, linking edits to the conversations that shaped them, and is currently in early access.

hackernews · jeremy_k · Jun 11, 16:28 · [Discussion](https://news.ycombinator.com/item?id=48492533)

**Background**: Traditional version control systems like Git record snapshots of code at commit points, but the process between commits is lost. DeltaDB aims to fill that gap by recording every keystroke and operation, providing a richer history for review and collaboration.

<details><summary>References</summary>
<ul>
<li><a href="https://shapeof.com/archives/2025/8/deltadb_from_zed.html">DeltaDB From Zed (the Code Editor)</a></li>
<li><a href="https://zed.dev/deltadb">DeltaDB — Early Access</a></li>

</ul>
</details>

**Discussion**: Commenters are divided: some argue that commit hygiene (small, atomic commits with clear messages) already provides sufficient context, while others worry about privacy and the intrusiveness of recording every edit. There is also skepticism about whether the tool primarily benefits LLM-based agents rather than human developers.

**Tags**: `#developer tools`, `#version control`, `#LLM`, `#code review`, `#workflow`

---

<a id="item-13"></a>
## [Datasette 1.0a33 Extends JSON Extras API to Rows and Queries](https://simonwillison.net/2026/Jun/11/datasette/#atom-everything) ⭐️ 7.0/10

Datasette 1.0a33 extends the `?_extra=` pattern to row and query pages, allowing API clients to request only the JSON keys they need, and this pattern is now documented. This release is a significant step toward a stable Datasette 1.0, providing a flexible and documented JSON API that reduces over-fetching and unnecessary SQL round-trips, benefiting all Datasette users. The `?_extra=` mechanism was first introduced for tables in Datasette 1.0a3; 1.0a33 extends it to row and query endpoints. Most of the code was written with the help of AI assistants like Claude and GPT.

rss · Simon Willison · Jun 11, 15:26

**Background**: Datasette is an open-source tool for exploring and publishing data, providing a JSON API for databases. The `?_extra=` pattern allows clients to opt into additional fields in JSON responses, improving efficiency. This release addresses a key blocker for the stable 1.0 release by fully documenting the JSON API.

<details><summary>References</summary>
<ul>
<li><a href="https://datasette.io/blog/2026/api-extras/">Datasette 1.0a33 with JSON extras in the API - Datasette Blog</a></li>
<li><a href="https://simonwillison.net/2026/Jun/11/datasette/">Release: datasette 1.0a33 - simonwillison.net</a></li>
<li><a href="https://digg.com/tech/mujp18gf">Datasette 1.0a33 Documents Expanded ?_extra= JSON API for ...</a></li>

</ul>
</details>

**Discussion**: Users praise the new `?_extra=` JSON API for making Datasette more flexible and note interest in Claude's role in writing the code.

**Tags**: `#datasette`, `#release`, `#JSON API`, `#open source`

---

<a id="item-14"></a>
## [Symbolic Regression vs LLMs: A Community Debate](https://www.reddit.com/r/MachineLearning/comments/1u2yqnu/is_symbolic_regression_still_a_thing_given_llms/) ⭐️ 7.0/10

A Reddit user questioned whether traditional symbolic regression techniques are obsolete given the rise of large language models, sparking a discussion on the strengths and weaknesses of each approach. This debate highlights the evolving landscape of AI-driven scientific discovery, where LLMs may complement or challenge established methods like symbolic regression for interpretable model discovery. Symbolic regression infers mathematical expressions from data without pre-specified structure, while LLMs can generate code and directly tackle symbolic regression tasks. Recent research like LLM-SR (ICLR 2025 Oral) and In-Context Symbolic Regression explores LLM-based approaches.

reddit · r/MachineLearning · /u/omomom42 · Jun 11, 13:13

**Background**: Symbolic regression is a machine learning technique that searches for mathematical expressions to fit data, often using genetic programming. It is valued for producing interpretable models. Large language models (LLMs) like GPT-4 have shown ability to generate code and solve mathematical problems, leading to questions about their potential to replace specialized symbolic regression methods.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Symbolic_regression">Symbolic regression - Wikipedia</a></li>
<li><a href="https://arxiv.org/abs/2107.14351">[2107.14351] Contemporary Symbolic Regression Methods and ... Interpretable scientific discovery with symbolic regression ... Recent Advances in Symbolic Regression | ACM Computing Surveys Symbolic Regression: The Forgotten Machine Learning Method Symbolic regression methods - ScienceDirect Contemporary Symbolic Regression Methods and their Relative ...</a></li>
<li><a href="https://github.com/deep-symbolic-mathematics/LLM-SR">GitHub - deep-symbolic-mathematics/LLM-SR: [ICLR 2025 Oral ...</a></li>

</ul>
</details>

**Tags**: `#symbolic regression`, `#LLMs`, `#machine learning`, `#AI research`

---

<a id="item-15"></a>
## [Papers Without Code Relaunches with Closed-Source Evals](https://www.reddit.com/r/MachineLearning/comments/1u1wq0a/introducing_papers_without_code_p/) ⭐️ 7.0/10

Niels from Hugging Face relaunched paperswithcode.co, a platform that automatically parses research papers to create leaderboards across AI domains, now including evaluations for closed-source models like GPT-5.5 and Mythos 5. This fills a gap in tracking state-of-the-art AI performance, as many benchmarks are now dominated by closed-source models, and provides a toggle to view only open models, helping the community compare both ecosystems. The platform supports submitting sources beyond arXiv, such as blog posts, and tags closed-source evaluations with a 'closed' tag. Users can disable closed-source evals via a toggle or in settings.

reddit · r/MachineLearning · /u/NielsRogge · Jun 10, 08:58

**Background**: Papers with Code is a popular resource that connects machine learning papers to their code and benchmarks. The original site was acquired by Meta in 2022, and this relaunch is an independent effort by a Hugging Face team member to provide a similar service with added features.

<details><summary>References</summary>
<ul>
<li><a href="https://paperswithcode.co/">Papers with Code</a></li>
<li><a href="https://openai.com/index/browsecomp/">BrowseComp: a benchmark for browsing agents - OpenAI</a></li>
<li><a href="https://en.wikipedia.org/wiki/GPT-5.5">GPT-5.5 - Wikipedia</a></li>

</ul>
</details>

**Discussion**: The Reddit discussion is active and generally positive, with users appreciating the inclusion of closed-source model evals and the toggle feature. Some commenters discuss the naming 'Papers Without Code' and the challenges of evaluating closed models.

**Tags**: `#AI`, `#Machine Learning`, `#Benchmarks`, `#Open Source`, `#Research`

---

<a id="item-16"></a>
## [Pyrecall: Open-source tool detects catastrophic forgetting in LLM fine-tuning](https://www.reddit.com/r/MachineLearning/comments/1u2hjye/pyrecall_open_source_tool_for_detecting/) ⭐️ 7.0/10

Pyrecall, an open-source tool (v0.1.0, MIT license), has been released to detect catastrophic forgetting during LLM fine-tuning by snapshotting skill scores before and after fine-tuning and rolling back LoRA adapters by name. It runs fully locally with no external API dependencies. Catastrophic forgetting is a critical challenge in continual learning for LLMs, and Pyrecall fills a gap in practical tooling for practitioners. It enables developers to safely fine-tune models without losing previously learned capabilities, which is essential for real-world deployments. Pyrecall snapshots skill scores before and after fine-tuning, flags regressions, and can roll back LoRA adapters by name. The tool is in early stage (v0.1.0) and the author is seeking community feedback on the benchmark design.

reddit · r/MachineLearning · /u/Level_Frosting_7950 · Jun 10, 22:49

**Background**: Catastrophic forgetting occurs when a neural network loses previously learned knowledge upon learning new information. LoRA (Low-Rank Adaptation) is a popular parameter-efficient fine-tuning method that trains small adapter modules instead of full model weights. Continual learning research aims to enable models to learn sequentially without forgetting, but practical tooling for detecting and mitigating forgetting during fine-tuning has been lacking.

<details><summary>References</summary>
<ul>
<li><a href="https://arxiv.org/abs/2504.01241">[2504.01241] Catastrophic Forgetting in LLMs: A Comparative ... Avoiding Amnesia: Some Practical Guides to Mitigate ... - Medium Mitigating Catastrophic Forgetting in Large Language Models ... An Empirical Study of Catastrophic Forgetting in Large ... Catastrophic forgetting in Large Language Models - UnfoldAI Catastrophic Forgetting in LLMs: A Comparative Analysis ... Researchers propose a self-distillation fix for ‘catastrophic ...</a></li>
<li><a href="https://huggingface.co/docs/peft/conceptual_guides/adapter">Adapters · Hugging Face</a></li>
<li><a href="https://en.wikipedia.org/wiki/Continual_learning">Continual learning</a></li>

</ul>
</details>

**Discussion**: The Reddit post has no comments yet, but the author explicitly invites feedback on the benchmark design, indicating openness to community input.

**Tags**: `#LLM`, `#fine-tuning`, `#catastrophic forgetting`, `#continual learning`, `#open source`

---

<a id="item-17"></a>
## [uv 0.11.21 Adds New CPython Versions and Preview Features](https://github.com/astral-sh/uv/releases/tag/0.11.21) ⭐️ 6.0/10

uv 0.11.21 adds support for CPython 3.13.14 and 3.14.6, introduces preview features for workspace metadata and single-dependency upgrade, and includes performance improvements and bug fixes. This release improves uv's compatibility with the latest Python versions and enhances developer workflows with workspace metadata and targeted dependency upgrades, making uv more robust for monorepo and CI environments. Preview features include `environment.root` in `uv workspace metadata --sync` and the ability to upgrade a single dependency constraint via `uv upgrade`. Performance gains come from parallel Python version discovery and avoiding redundant source distribution name normalization.

github · github-actions[bot] · Jun 11, 18:20

**Background**: uv is a fast Python package manager written in Rust, designed as a drop-in replacement for pip and pip-tools. Workspace metadata allows tools to inspect project structure, and the new upgrade feature addresses a long-standing request for selective dependency updates without modifying the entire lockfile.

<details><summary>References</summary>
<ul>
<li><a href="https://docs.astral.sh/uv/reference/internals/metadata/">Workspace Metadata | uv</a></li>
<li><a href="https://github.com/astral-sh/uv/issues/14394">Is it possible to upgrade just a single package if ... - GitHub</a></li>
<li><a href="https://pydevtools.com/handbook/explanation/understanding-uv-init-project-types/">uv init: project types, flags, and examples | pydevtools</a></li>

</ul>
</details>

**Tags**: `#python`, `#package-manager`, `#release`, `#tooling`

---

<a id="item-18"></a>
## [FablePool: Crowdfund AI Agent Projects Built in Public](https://fablepool.com/) ⭐️ 6.0/10

FablePool launched a platform where users pool money behind a prompt to fund an AI agent that builds the project in public, with transactions recorded on a public ledger. 这一概念将众筹与AI驱动开发相结合，可能降低开源项目的门槛，实现无需传统开发者的社区资助软件创建。 Projects have AI-estimated funding targets and public credit ledgers; however, a demo project regressed at milestone 15, and the platform's legal stance on licensing (MIT vs. public domain) is questioned.

hackernews · matthewbarras · Jun 11, 21:17 · [Discussion](https://news.ycombinator.com/item?id=48496539)

**Background**: FablePool is a new platform where users crowdfund ambitious prompts for AI agents to build software in public. It uses AI to estimate funding targets and records contributions on a public ledger. The concept is similar to traditional crowdfunding but with an AI agent as the builder.

<details><summary>References</summary>
<ul>
<li><a href="https://fablepool.com/">Discover — FablePool</a></li>
<li><a href="https://geekhaus.club/feed/2026/06/11/fablepool-lets-users-crowdfund-ambitious-prompts">FablePool lets users crowdfund ambitious prompts for AI ...</a></li>
<li><a href="https://news.linxi.com.au/news/fablepool-launches-public-platform-for-ai-driven-open-source-crowdfunding">FablePool launches public AI funding platform for open-source ...</a></li>

</ul>
</details>

**Discussion**: Commenters are skeptical: some question the legal defensibility of the MIT license claim, others note a demo project regressed, and one asks how genuine ideas are distinguished from token burns. A suggestion for a cybersecurity version was also made.

**Tags**: `#crowdfunding`, `#AI`, `#open source`, `#software development`

---

<a id="item-19"></a>
## [Kids' reading for pleasure drops sharply, report finds](https://www.nbcnews.com/data-graphics/kids-reading-less-lower-levels-department-education-study-rcna348987) ⭐️ 6.0/10

A new report reveals a significant decline in reading for pleasure among schoolchildren, with fewer kids reading books in their free time. This trend could impact literacy, critical thinking, and academic performance, raising concerns about the long-term effects of increased screen time and changing leisure habits. The report, based on Department of Education data, shows the decline across all age groups, with the steepest drops among teenagers. Community comments highlight device usage and parental modeling as contributing factors.

hackernews · freejoe76 · Jun 10, 17:03 · [Discussion](https://news.ycombinator.com/item?id=48479314)

**Background**: Reading for pleasure has long been associated with improved vocabulary, comprehension, and empathy. The decline coincides with the rise of smartphones, social media, and streaming services, which compete for children's attention.

**Discussion**: Commenters share personal experiences: one parent cut device usage and saw improvement, while another notes that even top school systems struggle with student reading stamina. Some defend reading as valuable, while others argue that active experiences are better than passive reading.

**Tags**: `#education`, `#reading`, `#screen time`, `#society`

---

<a id="item-20"></a>
## [Datasette-Agent 0.2a0 Adds Interactive User Questions](https://simonwillison.net/2026/Jun/10/datasette-agent/#atom-everything) ⭐️ 6.0/10

Datasette-agent 0.2a0 introduces tools that can ask users questions mid-execution via a new ToolContext object, and adds a built-in save_query tool for saving SQL queries as Datasette stored queries. This release enables more interactive and user-guided agent workflows, allowing agents to pause and request input, which improves safety and usability for complex data tasks. The ask_user() method supports yes/no, multiple-choice, and free-text questions; while unanswered, the conversation suspends and persists across server restarts. The save_query tool requires human approval before storing any SQL.

rss · Simon Willison · Jun 10, 23:57

**Background**: Datasette is an open-source tool for exploring and publishing data. Datasette-agent is an LLM-powered agent that can query databases and perform actions. This release builds on a new LLM alpha that enables tool-based interactions.

<details><summary>References</summary>
<ul>
<li><a href="https://simonwillison.net/2026/Jun/10/datasette-agent/">Release: datasette-agent 0.2a0 - simonwillison.net</a></li>
<li><a href="https://pypi.org/project/datasette-agent/">datasette-agent · PyPI</a></li>

</ul>
</details>

**Tags**: `#datasette`, `#agent`, `#tool`, `#open-source`, `#release`

---

<a id="item-21"></a>
## [Is Parrot Better Than Existing Models?](https://www.reddit.com/r/MachineLearning/comments/1u3knpi/so_is_parrot_better_than_existing_models_or_not_d/) ⭐️ 6.0/10

A Reddit post in r/MachineLearning questions whether the Parrot model outperforms existing models, but the post contains only an image with no substantive text or analysis. The discussion reflects community interest in comparing new models like Parrot against established baselines, which is crucial for understanding progress in machine learning. The post has a score of 6.0/10 and is tagged with 'machine learning', 'model comparison', and 'Parrot'. No comments or detailed results are provided, limiting its usefulness.

reddit · r/MachineLearning · /u/HitarthSurana · Jun 12, 04:01

**Background**: Parrot is a model that appears in multiple contexts: it can refer to a multi-reward reinforcement learning framework for text-to-image generation, or a tool for machine learning tasks. The specific model referenced in the post is unclear, but the community is likely discussing its performance relative to other models.

<details><summary>References</summary>
<ul>
<li><a href="https://idptools-parrot.readthedocs.io/en/stable/usage/basic_examples.html">Basic Examples: — parrot documentation - Read the Docs</a></li>
<li><a href="https://arxiv.org/html/2401.05675v2">Parrot: Pareto-optimal Multi-Reward Reinforcement Learning ...</a></li>

</ul>
</details>

**Tags**: `#machine learning`, `#model comparison`, `#Parrot`

---

<a id="item-22"></a>
## [Routing LLMs by Task Verifiability: Small Experiment](https://www.reddit.com/r/MachineLearning/comments/1u2c04u/routing_llms_by_task_verifiability_a_small/) ⭐️ 6.0/10

A small experiment (n=120) tested routing LLMs by task verifiability, finding that weaker models with a verifier can match frontier models on high-verifiability tasks like code unit tests and structured extraction, but not on low-verifiability tasks like creative summarization. This experiment provides early evidence that task verifiability could be a practical criterion for cost-effective LLM routing, potentially reducing reliance on expensive frontier models for many tasks. The experiment used three models (Claude Sonnet 4.6, GPT 5.5, Mistral 3 8B) across four task categories, with a simple verifier based on JSON Schema and regexes; a schema ambiguity initially caused Claude to underperform on structured extraction, highlighting that verifier quality matters.

reddit · r/MachineLearning · /u/DragonfruitAlone4497 · Jun 10, 19:18

**Background**: Andrej Karpathy's verifiability framework classifies AI tasks by how easily outputs can be mechanically checked; high-verifiability tasks (e.g., code compilation) are safer for automation because errors are catchable. vLLM is a high-throughput LLM serving library used to run the local Mistral model in this experiment.

<details><summary>References</summary>
<ul>
<li><a href="https://karpathy.bearblog.dev/verifiability/">Verifiability | karpathy</a></li>
<li><a href="https://www.mindstudio.ai/blog/karpathy-verifiability-framework-decide-what-to-automate-workflow">How to Use Karpathy's Verifiability Framework to Decide What ...</a></li>
<li><a href="https://pypi.org/project/vllm/">vllm ·PyPI</a></li>

</ul>
</details>

**Tags**: `#LLM`, `#routing`, `#task verifiability`, `#experiment`, `#cost optimization`

---

<a id="item-23"></a>
## [Student Seeks Papers on AI Responses to Psychological Distress](https://www.reddit.com/r/MachineLearning/comments/1u2j4uv/looking_for_papersresources_on_ai_responses_to/) ⭐️ 6.0/10

A psychology and systems engineering student posted a detailed request on Reddit for papers and resources comparing how general-purpose LLMs (ChatGPT, Gemini), mental-health chatbots (Wysa), and AI companions (Replika) respond to psychological distress prompts at varying intensities. This research request highlights a growing intersection of psychology and AI safety, as understanding how AI systems handle mental health crises is critical for responsible deployment. The findings could inform safer design of AI chatbots used by vulnerable populations. The student plans to compare systems across dimensions such as safety protocols, empathy, crisis referrals, and response consistency across prompt types (declarative vs. question-based, explicit vs. ambiguous). They also seek advice on methodological challenges like reproducibility, stochastic outputs, and hidden safety layers.

reddit · r/MachineLearning · /u/dakartt · Jun 10, 23:57

**Background**: AI systems like ChatGPT, Wysa, and Replika are increasingly used for emotional support, but their responses to distress can vary widely due to differences in training data, safety filters, and design goals. Wysa is a mental-health chatbot using evidence-based CBT exercises, while Replika is an AI companion focused on building long-term emotional bonds. General-purpose LLMs like ChatGPT and Gemini are not specifically designed for mental health but may still encounter distress-related prompts.

<details><summary>References</summary>
<ul>
<li><a href="https://www.wysa.com/">Wysa - Everyday Mental Health</a></li>
<li><a href="https://replika.com/">Replika | The AI friend to do life with</a></li>
<li><a href="https://arxiv.org/pdf/2511.08880">Simulating Psychological Risks in Human-AI Interactions: Real ...</a></li>

</ul>
</details>

**Discussion**: The Reddit post received supportive comments offering suggestions for relevant papers, datasets, and evaluation frameworks, with some users cautioning about the difficulty of comparing systems with different architectures and the need to control for model versioning and safety layers.

**Tags**: `#AI safety`, `#mental health`, `#LLM`, `#chatbots`, `#research`

---