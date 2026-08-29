**简体中文** · [English](README_EN.md)

![Awesome Embodied Trustworthy Execution banner](assets/banner.svg)
[![Awesome](https://awesome.re/badge.svg)](https://awesome.re) ![43 papers](https://img.shields.io/badge/Papers-43-2563eb?style=flat-square) ![VLA WAM VLN](https://img.shields.io/badge/Embodied_AI-VLA%20%7C%20WAM%20%7C%20VLN-0f766e?style=flat-square) ![Trustworthy Execution](https://img.shields.io/badge/Focus-Trustworthy_Execution-b45309?style=flat-square) ![Updated 2026-08-29](https://img.shields.io/badge/Updated-2026--08--29-64748b?style=flat-square) ![PRs welcome](https://img.shields.io/badge/PRs-Welcome-16a34a?style=flat-square)

**A curated research map for security, reliability, and decision assurance in embodied AI.**

`Trust` · `Detect` · `Verify` · `Mitigate` · `Recover`

## 👥 作者

[郑子豪](https://github.com/zhengzihaoPKU) · [曹航语](https://github.com/i6bimua) · [毛郅皓](https://github.com/lusunn111)

> [!NOTE]
> **核心组织原则：按“非可信从哪里来”分类，而不是把攻击面、评测方法、训练策略和运行时机制混成同一层级。** 这使 malicious attack、soft/hardware error 和 model-originated decision anomaly 三条主线能够清楚对应到不同的研究问题。

## ✨ Why this list?

具身智能与普通数字 AI 的关键区别，是模型输出会进入真实的 **perception → reasoning → action → physical feedback** 闭环。一个很小的视觉偏差、计算近似或决策异常，都可能在连续执行中传播并放大。因此，本仓库关注的不是泛化的 “AI Safety”，而是更具体的 **Trustworthy Embodied Execution**：如何识别非可信状态、阻止风险进入执行链，并在必要时修正、重规划或恢复。

![source-first taxonomy](assets/taxonomy.svg)

### Three sources of non-trustworthiness

| Layer                                    | Core question                              | Typical causes                                                               | Typical response                                           |
| ---------------------------------------- | ------------------------------------------ | ---------------------------------------------------------------------------- | ---------------------------------------------------------- |
| 🛡️**I. Malicious Attacks**       | 系统是否被攻击者主动操纵？                 | patch / 3D texture, jailbreak, prompt injection, WAM integrity attack        | red teaming, attack detection, adversarial defense         |
| ⚙️**II. Soft / Hardware Errors** | 没有攻击者时，系统误差会不会破坏闭环？     | sensor noise, viewpoint shift, pruning/quantization, hardware/actuator fault | robustness, fault tolerance, recovery                      |
| 🧠**III. Decision Anomalies**      | 输入和硬件正常时，模型自己是否正在做错事？ | oscillation, task drift, imagination–reality mismatch, long-horizon failure | monitoring, verification, constraint, replanning, recovery |

> [!IMPORTANT]
> **Black-box attack ≠ black-box anomaly monitoring.** 例如 AdvNav / BadWAM 的 *black-box* 指攻击者拿不到梯度；而 *How VLAs Fail Differently* 的 black-box monitoring 指部署侧完全不读取模型内部状态、只观察 action output。

## 🔥 Featured Papers

|            ID | Paper                                                                                                                                           | Why it is worth reading first    |
| ------------: | ----------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------- |
| **P01** | [Safety in Embodied AI: A Survey of Risks, Attacks, and Defenses](https://arxiv.org/abs/2605.02900)                                                | 最完整的具身安全全景入口         |
| **P04** | [JailWAM: Jailbreaking World Action Models in Robot Control](https://arxiv.org/abs/2604.05498)                                                     | WAM jailbreak + 物理后果评测     |
| **P07** | [When to Trust Imagination: Adaptive Action Execution for World Action Models](https://arxiv.org/abs/2605.06222)                                   | WAM 想象–现实闭环自验证         |
| **P08** | [Tex3D: Objects as Attack Surfaces via Adversarial 3D Textures for Vision-Language-Action Models](https://arxiv.org/abs/2604.01618)                | 从 2D patch 走向 3D 物理攻击     |
| **P19** | [RedVLA: Physical Red Teaming for Vision-Language-Action Models](https://arxiv.org/abs/2604.22591)                                                 | trajectory-guided 物理红队       |
| **P20** | [LIBERO-Plus: In-depth Robustness Analysis of Vision-Language-Action Models](https://arxiv.org/abs/2510.13626)                                     | 七维真实扰动下的 VLA 鲁棒性      |
| **P23** | [How VLAs Fail Differently: Black-Box Action Monitoring Reveals Architecture-Specific Failure Signatures](https://arxiv.org/abs/2605.28726)        | 最纯粹的黑盒动作监测之一         |
| **P26** | [Foresight: Failure Detection for Long-Horizon Robotic Manipulation with Action-Conditioned World Model Latents](https://arxiv.org/abs/2606.23085) | 世界模型 latent 的长时程失效预测 |
| **P37** | [Pre-VLA: Preemptive Runtime Verification for Reliable Vision-Language-Action and World-Model Rollouts](https://arxiv.org/abs/2605.22446)          | 执行前验证与预算化重采样         |
| **P38** | [Don&#39;t Run with Scissors: Pruning Breaks VLA Models but They Can Be Recovered](https://arxiv.org/abs/2510.08464)                               | 系统压缩如何破坏闭环可靠性       |

## 🧭 Quick Navigation

- [Surveys and Frameworks](#surveys-and-frameworks)
- [I. Malicious Attacks and Defense](#i-malicious-attacks-and-defense)
- [II. Software and Hardware Errors and Robustness](#ii-software-and-hardware-errors-and-robustness)
- [III. Decision Anomaly Detection and Runtime Assurance](#iii-decision-anomaly-detection-and-runtime-assurance)
- [Research Landscape](#research-landscape)
- [Open Research Gaps](#open-research-gaps)
- [Contributing](#contributing)

## 🗺️ Research Landscape

### Open the 43-paper landscape table

|  ID | Paper                                                                                                                                              | Layer            | Role / intervention        |
| --: | -------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------- | -------------------------- |
| P01 | [Safety in Embodied AI: A Survey of Risks, Attacks, and Defenses](https://arxiv.org/abs/2605.02900)                                                   | 🧭 Framework     | Survey                     |
| P02 | [Safe Embodied AI for Long-horizon Tasks: A Cross-layer Analysis of Robotic Manipulation](https://arxiv.org/abs/2606.05660)                           | 🧭 Framework     | Survey / Framework         |
| P03 | [What Breaks Embodied AI Security: LLM Vulnerabilities, CPS Flaws, or Something Else?](https://arxiv.org/abs/2602.17345)                              | 🧭 Framework     | Survey / System View       |
| P04 | [JailWAM: Jailbreaking World Action Models in Robot Control](https://arxiv.org/abs/2604.05498)                                                        | 🛡️ Security    | Attack + Evaluation        |
| P05 | [BadWAM: When World-Action Models Dream Right but Act Wrong](https://arxiv.org/abs/2607.15207)                                                        | 🛡️ Security    | Attack                     |
| P06 | [Attacking the Trusted Imagination: Oracle-Level Integrity Attacks on Imagine-then-Act World Models](https://arxiv.org/abs/2606.22966)                | 🛡️ Security    | Attack + Detection         |
| P07 | [When to Trust Imagination: Adaptive Action Execution for World Action Models](https://arxiv.org/abs/2605.06222)                                      | 🧠 Assurance     | Runtime Verification       |
| P08 | [Tex3D: Objects as Attack Surfaces via Adversarial 3D Textures for Vision-Language-Action Models](https://arxiv.org/abs/2604.01618)                   | 🛡️ Security    | Physical Attack            |
| P09 | [TRAP: Hijacking VLA CoT-Reasoning via Adversarial Patches](https://arxiv.org/abs/2603.23117)                                                         | 🛡️ Security    | Physical Attack            |
| P10 | [VLA-Hijack: A Transferable Patch Attack against Vision-Language-Action Models via Visual Proprioception Hijacking](https://arxiv.org/abs/2605.28083) | 🛡️ Security    | Physical Attack            |
| P11 | [FreezeVLA: Action-Freezing Attacks against Vision-Language-Action Models](https://arxiv.org/abs/2509.19870)                                          | 🛡️ Security    | Attack                     |
| P12 | [When Alignment Fails: Multimodal Adversarial Attacks on Vision-Language-Action Models](https://arxiv.org/abs/2511.16203)                             | 🛡️ Security    | Attack Toolbox             |
| P13 | [Exploring the Adversarial Vulnerabilities of Vision-Language-Action Models in Robotics](https://arxiv.org/abs/2411.13587)                            | 🛡️ Security    | Attack                     |
| P14 | [AdvNav: Behavior-Guided Black-Box Adversarial Attacks on Vision-Language Navigation](https://arxiv.org/abs/2607.11063)                               | 🛡️ Security    | Black-box Attack           |
| P15 | [Adversarial Attacks on Robotic Vision Language Action Models](https://arxiv.org/abs/2506.03350)                                                      | 🛡️ Security    | Attack                     |
| P16 | [Manipulating Multimodal Agents via Cross-Modal Prompt Injection](https://arxiv.org/abs/2504.14348)                                                   | 🛡️ Security    | Attack                     |
| P17 | [Hijacking Robots with a Piece of Paper: A Systematic Study of Physical Prompt Injection in VLM-Controlled Robots](https://arxiv.org/abs/2608.05715)  | 🛡️ Security    | Physical Prompt Injection  |
| P18 | [ANNIE: Be Careful of Your Robots](https://arxiv.org/abs/2509.03383)                                                                                  | 🛡️ Security    | Benchmark + Attack         |
| P19 | [RedVLA: Physical Red Teaming for Vision-Language-Action Models](https://arxiv.org/abs/2604.22591)                                                    | 🛡️ Security    | Red Team + Guard           |
| P20 | [LIBERO-Plus: In-depth Robustness Analysis of Vision-Language-Action Models](https://arxiv.org/abs/2510.13626)                                        | ⚙️ Reliability | Robustness Benchmark       |
| P21 | [LIBERO-Safety: A Comprehensive Benchmark for Physical and Semantic Safety in Vision-Language-Action Models](https://arxiv.org/abs/2606.23686)        | ⚙️ Reliability | Safety Benchmark           |
| P22 | [ForesightSafety-VLA: A Unified Diagnostic Safety Benchmark for Vision-Language-Action Models](https://arxiv.org/abs/2606.27079)                      | 🧠 Assurance     | Diagnostic Benchmark       |
| P23 | [How VLAs Fail Differently: Black-Box Action Monitoring Reveals Architecture-Specific Failure Signatures](https://arxiv.org/abs/2605.28726)           | 🧠 Assurance     | Black-box Runtime Monitor  |
| P24 | [When and How Severely: Scenario-Specific Safety Envelopes for Driving VLAs](https://arxiv.org/abs/2606.14238)                                        | ⚙️ Reliability | Safety Envelope            |
| P25 | [SAFE: Multitask Failure Detection for Vision-Language-Action Models](https://arxiv.org/abs/2506.09937)                                               | 🧠 Assurance     | Runtime Failure Detection  |
| P26 | [Foresight: Failure Detection for Long-Horizon Robotic Manipulation with Action-Conditioned World Model Latents](https://arxiv.org/abs/2606.23085)    | 🧠 Assurance     | Runtime Failure Detection  |
| P27 | [SafeVLA: Towards Safety Alignment of Vision-Language-Action Model via Constrained Learning](https://arxiv.org/abs/2503.03480)                        | 🧠 Assurance     | Training-time Alignment    |
| P28 | [SafeDojo: Safe Reinforcement Learning for VLA via Interactive World Model](https://arxiv.org/abs/2606.20698)                                         | 🧠 Assurance     | Training-time Safe RL      |
| P29 | [SafeAlign-VLA: A Negative-Enhanced Safe Alignment Framework for Risk-Aware Autonomous Driving](https://arxiv.org/abs/2605.19524)                     | 🧠 Assurance     | Safety Alignment           |
| P30 | [SafeBimanual: Diffusion-based Trajectory Optimization for Safe Bimanual Manipulation](https://arxiv.org/abs/2508.18268)                              | 🧠 Assurance     | Test-time Constraint       |
| P31 | [Neuro-Symbolic Safety Guidance for Vision-Language-Action Models via Constrained Flow Matching](https://arxiv.org/abs/2607.01378)                    | 🧠 Assurance     | Generation-time Constraint |
| P32 | [Safe Vision Language Action Models via Barrier Enhanced Flow Matching](https://arxiv.org/abs/2607.29569)                                             | 🧠 Assurance     | Generation-time Constraint |
| P33 | [ProbeAct: Probe-Guided Training-Free Failure Recovery in Vision-Language-Action Models](https://arxiv.org/abs/2606.09740)                            | 🧠 Assurance     | Runtime Recovery           |
| P34 | [Modular Safety Guardrails Are Necessary for Foundation-Model-Enabled Robots in the Real World](https://arxiv.org/abs/2602.04056)                     | 🧠 Assurance     | System Guardrail           |
| P35 | [Verifiable Foundation Models for Robot Safety](https://arxiv.org/abs/2606.23754)                                                                     | 🧠 Assurance     | Formal Verification        |
| P36 | [LabGuard: Grounding Natural-Language Laboratory Rules into Runtime Guards for Embodied Laboratory Agents](https://arxiv.org/abs/2606.31045)          | 🧠 Assurance     | Runtime Guard              |
| P37 | [Pre-VLA: Preemptive Runtime Verification for Reliable Vision-Language-Action and World-Model Rollouts](https://arxiv.org/abs/2605.22446)             | 🧠 Assurance     | Pre-execution Verification |
| P38 | [Don&#39;t Run with Scissors: Pruning Breaks VLA Models but They Can Be Recovered](https://arxiv.org/abs/2510.08464)                                  | ⚙️ Reliability | Compression Reliability    |
| P39 | [Security of World-Model-Based Embodied AI: A Lifecycle of Threats, Defenses, and Evaluation](https://arxiv.org/abs/2607.28226)                       | 🧭 Framework     | Lifecycle Security Survey  |
| P40 | [VLAGuard: A Framework for Evaluating and Mitigating Physical Attention Hijacking in Vision-Language-Action Robots within Wireless Sensor Networks](https://arxiv.org/abs/2608.01028) | 🛡️ Security | Attack + Defense |
| P41 | [Hidden in Plain Sight: Diffusion-Based Unrestricted Robotic Attacks on Vision-Language-Action Models](https://arxiv.org/abs/2608.10393)               | 🛡️ Security    | Physical Attack            |
| P42 | [Bit-Flip Attacks on Vision-Language-Action Models: Action-Decoding Architecture Shapes the Vulnerability](https://arxiv.org/abs/2608.15475)          | 🛡️ Security    | Weight-Integrity Attack    |
| P43 | [Security of Foundation-Model-Powered Embodied Agents: Attack Surfaces, Attacks, Defenses, and Evaluation](https://arxiv.org/abs/2608.16843)          | 🧭 Framework     | Trust-Boundary Survey      |

---

## 🧭 Surveys and Frameworks

用于定义问题空间、跨层闭环安全与“为什么具身系统会失信”。

### P01 · Safety in Embodied AI: A Survey of Risks, Attacks, and Defenses

`Survey` `Taxonomy` `Embodied AI`   **Survey**

![Representative figure for P01](assets/figures/01_safety-in-embodied-ai-a-survey-of-risks-attacks-and-defenses.png)

**🎯 问题**
具身安全研究横跨感知、推理、规划、动作和智能体系统，攻击与防御类型又彼此交织，缺少统一入口。

**💡 核心思路**
系统梳理 500 余篇工作，将具身能力层与 adversarial attack、backdoor、jailbreak、sensor attack、defense 等风险/方法对应起来。

**🔎 为什么重要**
适合作为整个方向的“地图”：先建立全景，再定位某个具体攻击面或保障机制。

[Paper](https://arxiv.org/abs/2605.02900) · [PDF](https://arxiv.org/pdf/2605.02900.pdf)   `arXiv:2605.02900`

### P02 · Safe Embodied AI for Long-horizon Tasks: A Cross-layer Analysis of Robotic Manipulation

`Long-horizon` `Cross-layer` `Manipulation`   **Survey / Framework**

![Representative figure for P02](assets/figures/02_safe-embodied-ai-for-long-horizon-tasks-a-cross-layer-analysis-of-roboti.png)

**🎯 问题**
长时程操作中的风险往往不是单点故障，而是早期 grounding / planning 小误差在后续接触执行中逐步累积。

**💡 核心思路**
按干预位置把研究组织为 planning-time、policy-time、execution-time，并区分 formal guarantee、statistical support 与 empirical heuristic。

**🔎 为什么重要**
把“安全机制放在哪里”与“证据有多强”同时纳入 taxonomy，特别适合分析闭环可信执行。

[Paper](https://arxiv.org/abs/2606.05660) · [PDF](https://arxiv.org/pdf/2606.05660.pdf)   `arXiv:2606.05660`

### P03 · What Breaks Embodied AI Security: LLM Vulnerabilities, CPS Flaws, or Something Else?

`LLM` `CPS` `Closed-loop`   **Survey / System View**

![Representative figure for P03](assets/figures/03_what-breaks-embodied-ai-security-llm-vulnerabilities-cps-flaws-or-someth.png)

**🎯 问题**
只用 LLM 安全或传统 CPS 安全解释具身系统都不够：语义正确的动作仍可能在物理世界造成危险。

**💡 核心思路**
从感知—决策/推理—规划/控制—物理本体四层系统出发，归纳 semantic–physical mismatch、state-dependent consequences、误差闭环放大、非组合安全四个根因。

**🔎 为什么重要**
把具身安全从“组件是否正确”提升到“跨层系统是否可信”，是三层分类的理论基础。

[Paper](https://arxiv.org/abs/2602.17345) · [PDF](https://arxiv.org/pdf/2602.17345.pdf)   `arXiv:2602.17345`

### P39 · Security of World-Model-Based Embodied AI: A Lifecycle of Threats, Defenses, and Evaluation

`World Model` `Lifecycle` `Security`   **Lifecycle Security Survey**

**🎯 问题**
世界模型既承担状态压缩、未来预测与规划，又可能把数据、传感、提示或反馈中的破坏沿闭环传播到真实动作；仅按单个攻击机制分类难以描述这种生命周期风险。

**💡 核心思路**
沿数据构建与表征学习、状态落地与想象、轨迹评估与执行、记忆和工具驱动的长期适应梳理威胁，并把 provenance、鲁棒 grounding、uncertainty-aware prediction、trajectory gating 与 feedback auditing 等防御对应到各阶段。

**🔎 为什么重要**
把世界模型从孤立预测组件提升为具身系统的安全边界，便于分析攻击如何跨阶段传播，以及保障机制应部署在何处。

[Paper](https://arxiv.org/abs/2607.28226) · [PDF](https://arxiv.org/pdf/2607.28226.pdf)   `arXiv:2607.28226`

### P43 · Security of Foundation-Model-Powered Embodied Agents: Attack Surfaces, Attacks, Defenses, and Evaluation

`Embodied Agent` `Trust Boundary` `Security`   **Trust-Boundary Survey**

**🎯 问题**
按 jailbreak、prompt injection 或 adversarial example 等机制组织攻击，往往无法说明攻击者最先突破了具身闭环中的哪条信任边界，也难以定位跨层传播路径。

**💡 核心思路**
采用 first-compromised-trust-boundary 原则，将系统组织为五层十二类攻击面，并基于 58 条攻击记录和 61 条防御记录分析攻击传播、防御位置与评测实践。

**🔎 为什么重要**
这种边界优先的视角有助于把防御放到正确接口，同时揭示 context / memory、middleware、world-state integrity 与 multi-agent trust 等研究缺口。

[Paper](https://arxiv.org/abs/2608.16843) · [PDF](https://arxiv.org/pdf/2608.16843.pdf)   `arXiv:2608.16843`

---

## 🛡️ I. Malicious Attacks and Defense

攻击者主动操纵视觉、语言、世界模型或物理环境。判据很简单：**是否存在有意、对抗性的外部操纵。**

### P04 · JailWAM: Jailbreaking World Action Models in Robot Control

`WAM` `Jailbreak` `Physical Risk`   **Attack + Evaluation**

![Representative figure for P04](assets/figures/04_jailwam-jailbreaking-world-action-models-in-robot-control.png)

**🎯 问题**
传统越狱评测只判断文本/图像是否违规，无法直接说明 WAM 产生的机器人动作是否真的危险。

**💡 核心思路**
把不同动作格式统一恢复为三维轨迹并可视化，用 VLM 风险判别器分级，再以开环筛选 + 闭环验证降低评测成本。

**🔎 为什么重要**
将 jailbreak 的成功标准从“模型被说服”推进到“物理轨迹产生真实风险”。

[Paper](https://arxiv.org/abs/2604.05498) · [PDF](https://arxiv.org/pdf/2604.05498.pdf)   `arXiv:2604.05498`

### P05 · BadWAM: When World-Action Models Dream Right but Act Wrong

`WAM` `Black-box Attack` `Integrity`   **Attack**

![Representative figure for P05](assets/figures/05_badwam-when-world-action-models-dream-right-but-act-wrong.png)

**🎯 问题**
WAM 可能“想象得对、动作却错”，因此只检查预测未来并不能保证执行安全。

**💡 核心思路**
在黑盒查询条件下优化视觉扰动：最大化动作偏差，同时约束 imagined future 尽量保持与 clean prediction 一致。

**🔎 为什么重要**
揭示 world prediction 与 action generation 之间存在新的完整性攻击面，也提醒未来画面不能成为唯一 safety signal。

[Paper](https://arxiv.org/abs/2607.15207) · [PDF](https://arxiv.org/pdf/2607.15207.pdf)   `arXiv:2607.15207`

### P06 · Attacking the Trusted Imagination: Oracle-Level Integrity Attacks on Imagine-then-Act World Models

`WAM` `World Model` `Oracle`   **Attack + Detection**

![Representative figure for P06](assets/figures/06_attacking-the-trusted-imagination-oracle-level-integrity-attacks-on-imag.png)

**🎯 问题**
同一个 imagined future 对 reactive policy 可能只是内部特征，但对 MPC / safety gate / verifier 却可能是被直接信任的“未来事实”。

**💡 核心思路**
对白盒 observation→imagination 通路做 PGD 完整性攻击，并利用被污染 imagination 的 off-manifold 特性构造无需额外训练的 denoiser consistency detector。

**🔎 为什么重要**
最关键的结论是 policy robust ≠ oracle robust：依赖世界模型想象的下游模块需要独立可信保障。

[Paper](https://arxiv.org/abs/2606.22966) · [PDF](https://arxiv.org/pdf/2606.22966.pdf)   `arXiv:2606.22966`

### P08 · Tex3D: Objects as Attack Surfaces via Adversarial 3D Textures for Vision-Language-Action Models

`VLA` `3D Texture` `Physical Attack`   **Physical Attack**

![Representative figure for P08](assets/figures/08_tex3d-objects-as-attack-surfaces-via-adversarial-3d-textures-for-vision-.png)

**🎯 问题**
传统 2D patch 容易随视角、遮挡和物体姿态变化失效，难以在真实操作轨迹中持续攻击。

**💡 核心思路**
将被操作物体表面作为攻击载体，用 foreground/background decoupling 建立可微渲染通路，并进行 trajectory-aware 关键帧加权优化。

**🔎 为什么重要**
把 VLA adversarial attack 从数字像素扰动推进到可跨视角、可打印/可实现的 3D 物理攻击。

[Paper](https://arxiv.org/abs/2604.01618) · [PDF](https://arxiv.org/pdf/2604.01618.pdf)   `arXiv:2604.01618`

### P09 · TRAP: Hijacking VLA CoT-Reasoning via Adversarial Patches

`VLA` `CoT` `Adversarial Patch`   **Physical Attack**

![Representative figure for P09](assets/figures/09_trap-hijacking-vla-cot-reasoning-via-adversarial-patches.png)

**🎯 问题**
让 VLA 随机失败并不等于获得行为控制；推理型 VLA 的 CoT / 中间计划本身可能是更强的劫持入口。

**💡 核心思路**
优化可打印 patch，使模型先生成攻击者指定的目标物体、子任务或轨迹，再同时约束底层 action 跟随被劫持的推理。

**🔎 为什么重要**
说明“可解释的中间推理”也可能成为攻击面：一旦 CoT 被改写，动作头会继续执行错误计划。

[Paper](https://arxiv.org/abs/2603.23117) · [PDF](https://arxiv.org/pdf/2603.23117.pdf)   `arXiv:2603.23117`

### P10 · VLA-Hijack: A Transferable Patch Attack against Vision-Language-Action Models via Visual Proprioception Hijacking

`VLA` `Proprioception` `Transferability`   **Physical Attack**

![Representative figure for P10](assets/figures/10_vla-hijack-a-transferable-patch-attack-against-vision-language-action-mo.png)

**🎯 问题**
直接对动作头做 patch attack 容易过拟合具体架构，跨模型迁移性有限。

**💡 核心思路**
压制真实机械臂区域的视觉特征，同时把攻击 patch 对齐到“robot arm”的语义和视觉原型，让模型把 patch 当成虚假的自身位置。

**🔎 为什么重要**
利用不同 VLA 共享的视觉本体定位需求，攻击更接近架构共性而非特定 action head。

[Paper](https://arxiv.org/abs/2605.28083) · [PDF](https://arxiv.org/pdf/2605.28083.pdf)   `arXiv:2605.28083`

### P11 · FreezeVLA: Action-Freezing Attacks against Vision-Language-Action Models

`VLA` `DoS` `Freezing`   **Attack**

![Representative figure for P11](assets/figures/11_freezevla-action-freezing-attacks-against-vision-language-action-models.png)

**🎯 问题**
机器人“不行动”也可能造成生产线停摆或紧急操作失败，而且停止后相机视角固定会让视觉攻击更持久。

**💡 核心思路**
用 min-max 双层优化：内层寻找最难被冻结的指令表达，外层优化同一张图像去击败这些指令并持续诱导 stop / no-op。

**🔎 为什么重要**
把安全风险从“错误动作”扩展到“持续拒绝动作”，揭示紧急干预指令也可能被攻击覆盖。

[Paper](https://arxiv.org/abs/2509.19870) · [PDF](https://arxiv.org/pdf/2509.19870.pdf)   `arXiv:2509.19870`

### P12 · When Alignment Fails: Multimodal Adversarial Attacks on Vision-Language-Action Models

`VLA` `Multimodal` `Alignment`   **Attack Toolbox**

![Representative figure for P12](assets/figures/12_when-alignment-fails-multimodal-adversarial-attacks-on-vision-language-a.png)

**🎯 问题**
只攻击图像或文本无法解释 VLA 的整体脆弱性，因为真正的决策建立在视觉对象、语言指代与动作之间的对齐上。

**💡 核心思路**
统一比较文本扰动、视觉 patch / noise 与 cross-modal mismatch，主动破坏“看见什么—指令说什么—动作做什么”的对应关系。

**🔎 为什么重要**
把攻击面从单一 modality 扩展为 alignment chain，有助于理解跨模态错误如何传递到动作。

[Paper](https://arxiv.org/abs/2511.16203) · [PDF](https://arxiv.org/pdf/2511.16203.pdf)   `arXiv:2511.16203`

### P13 · Exploring the Adversarial Vulnerabilities of Vision-Language-Action Models in Robotics

`VLA` `Action Space` `Physical Patch`   **Attack**

![Representative figure for P13](assets/figures/13_exploring-the-adversarial-vulnerabilities-of-vision-language-action-mode.png)

**🎯 问题**
离散 action token 被改变并不代表机械臂在物理空间中真的产生显著偏移。

**💡 核心思路**
直接优化动作幅值、三维方向和目标错误轨迹，并在物理 patch 中加入视角/颜色变换以增强现实鲁棒性。

**🔎 为什么重要**
把攻击目标从“输出变了”改成“物理轨迹偏了多少”，更符合闭环机器人攻击的评价需求。

[Paper](https://arxiv.org/abs/2411.13587) · [PDF](https://arxiv.org/pdf/2411.13587.pdf)   `arXiv:2411.13587`

### P14 · AdvNav: Behavior-Guided Black-Box Adversarial Attacks on Vision-Language Navigation

`VLN` `Black-box` `Evolutionary Search`   **Black-box Attack**

![Representative figure for P14](assets/figures/14_advnav-behavior-guided-black-box-adversarial-attacks-on-vision-language-.png)

**🎯 问题**
VLN 是多步闭环任务，攻击者通常拿不到模型梯度，单步分类式黑盒攻击信号又太弱。

**💡 核心思路**
用最终导航误差、路径效率和逐步错误动作倾向构造双粒度行为反馈，通过选择、交叉、变异进化视觉噪声。

**🔎 为什么重要**
展示了“只看行为结果”也能驱动长时程黑盒攻击；这里的 black-box 指攻击者不可见模型内部。

[Paper](https://arxiv.org/abs/2607.11063) · [PDF](https://arxiv.org/pdf/2607.11063.pdf)   `arXiv:2607.11063`

### P15 · Adversarial Attacks on Robotic Vision Language Action Models

`VLA` `Text Attack` `Action Hijack`   **Attack**

![Representative figure for P15](assets/figures/15_adversarial-attacks-on-robotic-vision-language-action-models.png)

**🎯 问题**
VLA 的离散动作 token 可能继承语言模型的 adversarial suffix / jailbreak 脆弱性。

**💡 核心思路**
把 GCG 类文本梯度搜索的目标从词 token 改为机器人动作 token，并对连续多帧联合优化同一恶意后缀。

**🔎 为什么重要**
说明语言接口不仅能改变高层语义，还可能直接获得低层 7-DoF 动作的控制权。

[Paper](https://arxiv.org/abs/2506.03350) · [PDF](https://arxiv.org/pdf/2506.03350.pdf)   `arXiv:2506.03350`

### P16 · Manipulating Multimodal Agents via Cross-Modal Prompt Injection

`Multimodal Agent` `Prompt Injection` `Cross-modal`   **Attack**

![Representative figure for P16](assets/figures/16_manipulating-multimodal-agents-via-cross-modal-prompt-injection.png)

**🎯 问题**
单独把恶意语义藏进图像可能不够可解释，单独文字注入又容易被 system prompt 防御。

**💡 核心思路**
让视觉潜空间与恶意目标对齐，同时搜索能绕过防御提示的文本命令，使两个模态共同指向同一未授权任务。

**🔎 为什么重要**
揭示跨模态“互相增强”会放大 prompt injection 风险，对能读取网页/文档的多模态智能体尤其重要。

[Paper](https://arxiv.org/abs/2504.14348) · [PDF](https://arxiv.org/pdf/2504.14348.pdf)   `arXiv:2504.14348`

### P17 · Hijacking Robots with a Piece of Paper: A Systematic Study of Physical Prompt Injection in VLM-Controlled Robots

`VLM Robot` `Prompt Injection` `Real World`   **Physical Prompt Injection**

![Representative figure for P17](assets/figures/17_hijacking-robots-with-a-piece-of-paper-a-systematic-study-of-physical-pr.png)

**🎯 问题**
机器人高层规划器会同时读取操作员指令和环境文字，却未必能区分可信指令与不可信场景文本。

**💡 核心思路**
设计间接标牌、任务重定义、权限冒充、冲突注入四类攻击，在多模型/布局/任务上系统测试，并比较提示防御、二次核验和文字遮蔽。

**🔎 为什么重要**
最直观地说明“一张纸”就能成为现实世界的 prompt injection 载体。

[Paper](https://arxiv.org/abs/2608.05715) · [PDF](https://arxiv.org/pdf/2608.05715.pdf)   `arXiv:2608.05715`

### P18 · ANNIE: Be Careful of Your Robots

`Benchmark` `Physical Safety` `Risk`   **Benchmark + Attack**

![Representative figure for P18](assets/figures/18_annie-be-careful-of-your-robots.png)

**🎯 问题**
任务成功率无法区分“安全失败”和“不安全成功”，也缺少可操作的物理风险目标。

**💡 核心思路**
依据人机交互安全标准建立多级风险、9 类场景和 2400 条序列，并训练攻击 leader 逐帧给出风险方向与强度，配合稀疏攻击。

**🔎 为什么重要**
把抽象安全概念转成可度量的轨迹风险，为后续检测、红队和安全训练提供统一数据入口。

[Paper](https://arxiv.org/abs/2509.03383) · [PDF](https://arxiv.org/pdf/2509.03383.pdf)   `arXiv:2509.03383`

### P19 · RedVLA: Physical Red Teaming for Vision-Language-Action Models

`VLA` `Red Teaming` `Runtime Guard`   **Red Team + Guard**

![Representative figure for P19](assets/figures/19_redvla-physical-red-teaming-for-vision-language-action-models.png)

**🎯 问题**
固定安全场景只能被动测模型，难以主动找到最容易触发危险的环境状态。

**💡 核心思路**
从正常轨迹识别抓取/运输/振荡区域，放入风险物体，再依据闭环轨迹用无梯度优化移动风险物体；最终用红队数据训练轻量 guard。

**🔎 为什么重要**
把具身红队从“随机放危险物”升级成 trajectory-guided risk amplification。

[Paper](https://arxiv.org/abs/2604.22591) · [PDF](https://arxiv.org/pdf/2604.22591.pdf)   `arXiv:2604.22591`

### P40 · VLAGuard: A Framework for Evaluating and Mitigating Physical Attention Hijacking in Vision-Language-Action Robots within Wireless Sensor Networks

`VLA` `Physical Patch` `Attention Defense`   **Attack + Defense**

**🎯 问题**
可打印物理补丁能够劫持 VLA 的 action-conditioned cross-attention，使机器人在真实闭环中忽略与任务相关的视觉区域并产生危险动作。

**💡 核心思路**
先以 VASA 根据 visuomotor attention 构造语义补丁进行压力测试，再用 APFT 稳定时空注意力并约束几何一致性，在不增加推理开销的情况下提升攻击下的鲁棒性。

**🔎 为什么重要**
工作把 attention-pathway vulnerability 与仿真和实体机器人的物理后果直接关联，并给出与该攻击面对应的训练期防御。

[Paper](https://arxiv.org/abs/2608.01028) · [PDF](https://arxiv.org/pdf/2608.01028.pdf)   `arXiv:2608.01028`

### P41 · Hidden in Plain Sight: Diffusion-Based Unrestricted Robotic Attacks on Vision-Language-Action Models

`VLA` `Diffusion` `Physical Patch`   **Physical Attack**

**🎯 问题**
传统 VLA 对抗攻击常依赖像素级扰动或白盒梯度，生成物明显且现实部署条件受限，难以代表自然外观攻击物进入机器人视野时的风险。

**💡 核心思路**
DURA 在预训练扩散模型的潜在轨迹上优化自然外观补丁，使机器人趋向攻击者指定动作；方法同时支持白盒设置和只读取预测动作的黑盒设置，并在仿真与实体系统中评测。

**🔎 为什么重要**
它把 VLA 物理攻击从易察觉的像素扰动推进到更具现实可实现性的 unrestricted patch，扩大了闭环红队评测应覆盖的威胁范围。

[Paper](https://arxiv.org/abs/2608.10393) · [PDF](https://arxiv.org/pdf/2608.10393.pdf)   `arXiv:2608.10393`

### P42 · Bit-Flip Attacks on Vision-Language-Action Models: Action-Decoding Architecture Shapes the Vulnerability

`VLA` `Bit Flip` `Weight Integrity`   **Weight-Integrity Attack**

**🎯 问题**
量化 VLA 的 INT8 权重可能遭受 Rowhammer 风格的定向位翻转，而动作解码头的架构会显著影响少量权重破坏在闭环中的失效程度。

**💡 核心思路**
用梯度选择高影响位并设计 manifold-escape 目标，跨三类 action head 比较攻击预算，同时评估只保护少量关键权重的选择性防护方案。

**🔎 为什么重要**
结果将模型权重完整性明确为具身基础模型的安全边界，并表明位翻转防护需要针对动作生成架构，而不能只依据随机故障测试。

[Paper](https://arxiv.org/abs/2608.15475) · [PDF](https://arxiv.org/pdf/2608.15475.pdf)   `arXiv:2608.15475`

---

## ⚙️ II. Software and Hardware Errors and Robustness

没有攻击者时，传感、环境、软件近似和计算/执行故障是否会在闭环中被放大。

### P20 · LIBERO-Plus: In-depth Robustness Analysis of Vision-Language-Action Models

`VLA` `Robustness` `LIBERO`   **Robustness Benchmark**

![Representative figure for P20](assets/figures/20_libero-plus-in-depth-robustness-analysis-of-vision-language-action-model.png)

**🎯 问题**
标准 LIBERO 上的高成功率可能只是记住固定相机、初始姿态和空间关系，并不代表真实鲁棒能力。

**💡 核心思路**
围绕 object layout、camera viewpoint、robot initial state、language、light、background、sensor noise 七个维度进行控制变量和分级扰动评测。

**🔎 为什么重要**
结果显示轻微相机/初态变化即可让部分模型从接近满分跌至极低水平，直接揭示“benchmark success ≠ reliable competence”。

[Paper](https://arxiv.org/abs/2510.13626) · [PDF](https://arxiv.org/pdf/2510.13626.pdf) · [Project](https://sylvestf.github.io/LIBERO-plus/) · [Code](https://github.com/sylvestf/LIBERO-plus) · [HF](https://huggingface.co/collections/Sylvest/libero-plus)   `arXiv:2510.13626`

### P21 · LIBERO-Safety: A Comprehensive Benchmark for Physical and Semantic Safety in Vision-Language-Action Models

`VLA` `Physical Safety` `Semantic Safety`   **Safety Benchmark**

![Representative figure for P21](assets/figures/21_libero-safety-a-comprehensive-benchmark-for-physical-and-semantic-safety.png)

**🎯 问题**
机器人可能最终完成任务，但中途发生碰撞；也可能轨迹完全无碰撞，却安全地操作了错误目标。

**💡 核心思路**
用参数化场景和少量关键位姿，经 motion planner 自动生成严格无碰撞示范，并分别评估 physical safety 与 semantic safety。

**🔎 为什么重要**
把“轨迹是否安全”和“事情是否做对”拆开，避免单一成功率掩盖安全退化。

[Paper](https://arxiv.org/abs/2606.23686) · [PDF](https://arxiv.org/pdf/2606.23686.pdf)   `arXiv:2606.23686`

### P24 · When and How Severely: Scenario-Specific Safety Envelopes for Driving VLAs

`Driving VLA` `Sensor Perturbation` `Functional Safety`   **Safety Envelope**

![Representative figure for P24](assets/figures/24_when-and-how-severely-scenario-specific-safety-envelopes-for-driving-vla.png)

**🎯 问题**
平均轨迹误差会掩盖低频但高严重度失败，而且不同驾驶场景可容忍的误差范围不同。

**💡 核心思路**
针对每类场景同时估计“扰动多大时越过安全线”和“越线后严重度如何分布”，形成二维 scenario-specific safety envelope。

**🔎 为什么重要**
把鲁棒性测试从平均性能转向 failure onset + tail severity，更接近功能安全分析。

[Paper](https://arxiv.org/abs/2606.14238) · [PDF](https://arxiv.org/pdf/2606.14238.pdf)   `arXiv:2606.14238`

### P38 · Don't Run with Scissors: Pruning Breaks VLA Models but They Can Be Recovered

`VLA` `Pruning` `Recovery`   **Compression Reliability**

![Representative figure for P38](assets/figures/38_don-t-run-with-scissors-pruning-breaks-vla-models-but-they-can-be-recove.png)

**🎯 问题**
语言模型里看起来温和的结构化剪枝，在 VLA 闭环中可能因单步误差不断反馈而造成大幅任务退化和更多安全违规。

**💡 核心思路**
分析原模型与剪枝模型的权重差值，对被移除信息做低秩分解，只恢复最重要的少数方向，同时保留主要稀疏计算收益。

**🔎 为什么重要**
直接证明“系统优化不是纯性能问题”：压缩/低精度等效率改造必须把 closed-loop robustness 当作一等约束。

[Paper](https://arxiv.org/abs/2510.08464) · [PDF](https://arxiv.org/pdf/2510.08464.pdf)   `arXiv:2510.08464`

---

## 🧠 III. Decision Anomaly Detection and Runtime Assurance

输入与硬件看起来正常时，模型自身是否正在做出不可靠决策，以及如何在执行前/执行中检测、约束与恢复。

### P07 · When to Trust Imagination: Adaptive Action Execution for World Action Models

`WAM` `Adaptive Execution` `Replanning`   **Runtime Verification**

![Representative figure for P07](assets/figures/07_when-to-trust-imagination-adaptive-action-execution-for-world-action-mod.png)

**🎯 问题**
固定 action chunk 长度无法同时兼顾效率和可靠性：执行越长越省推理，但误差越容易累积。

**💡 核心思路**
用 FFDC verifier 联合比较预测动作、预测未来画面、真实观测和语言指令；可信则继续 rollout，不可信则提前停止并重新规划。

**🔎 为什么重要**
把 world model 的 imagined future 从“生成中间量”变成“执行期预期”，形成自然的闭环自验证信号。

[Paper](https://arxiv.org/abs/2605.06222) · [PDF](https://arxiv.org/pdf/2605.06222.pdf)   `arXiv:2605.06222`

### P22 · ForesightSafety-VLA: A Unified Diagnostic Safety Benchmark for Vision-Language-Action Models

`VLA` `Diagnosis` `Long-horizon`   **Diagnostic Benchmark**

![Representative figure for P22](assets/figures/22_foresightsafety-vla-a-unified-diagnostic-safety-benchmark-for-vision-lan.png)

**🎯 问题**
一个安全成功率无法说明危险来自视觉、语言还是物理执行，也无法衡量风险在轨迹中持续了多久。

**💡 核心思路**
构造 13 类风险与 scene/language/vision 三类控制变量，记录累计安全成本、风险暴露时间和四象限安全/不安全成功失败。

**🔎 为什么重要**
提供“哪里出了问题、持续多久、最终结果如何”的诊断视角，而不只是给模型一个总分。

[Paper](https://arxiv.org/abs/2606.27079) · [PDF](https://arxiv.org/pdf/2606.27079.pdf)   `arXiv:2606.27079`

### P23 · How VLAs Fail Differently: Black-Box Action Monitoring Reveals Architecture-Specific Failure Signatures

`VLA` `Black-box` `Conformal`   **Black-box Runtime Monitor**

![Representative figure for P23](assets/figures/23_how-vlas-fail-differently-black-box-action-monitoring-reveals-architectu.png)

**🎯 问题**
给所有 VLA 使用同一个速度/抖动阈值并不可靠，因为离散 token、diffusion 和 action chunking 的动作统计天然不同。

**💡 核心思路**
SafeContract 只观察 action output，计算 reversal、jerk、momentum coherence、spectral energy、velocity 等指标，并用 conformal calibration / CUSUM 做运行时监测。

**🔎 为什么重要**
方向反复是跨架构较稳定的失败信号，而 jerk 只对离散族强；核心结论是 monitor 必须 architecture-matched。

[Paper](https://arxiv.org/abs/2605.28726) · [PDF](https://arxiv.org/pdf/2605.28726.pdf) · [Code](https://github.com/krishnam94/vla-edge)   `arXiv:2605.28726`

### P25 · SAFE: Multitask Failure Detection for Vision-Language-Action Models

`VLA` `Hidden Feature` `Conformal`   **Runtime Failure Detection**

![Representative figure for P25](assets/figures/25_safe-multitask-failure-detection-for-vision-language-action-models.png)

**🎯 问题**
如果每个机器人任务都要单独训练失败检测器，通用 VLA 的部署成本会很高。

**💡 核心思路**
从 VLA 中间 hidden features 学习连续 failure probability，并用 conformal prediction 校准报警阈值，在提前量和误报之间权衡。

**🔎 为什么重要**
说明不同任务虽然视觉/动作不同，但模型内部“正在失败”的表示具有一定跨任务共性。

[Paper](https://arxiv.org/abs/2506.09937) · [PDF](https://arxiv.org/pdf/2506.09937.pdf)   `arXiv:2506.09937`

### P26 · Foresight: Failure Detection for Long-Horizon Robotic Manipulation with Action-Conditioned World Model Latents

`World Model` `Long-horizon` `Conformal`   **Runtime Failure Detection**

![Representative figure for P26](assets/figures/26_foresight-failure-detection-for-long-horizon-robotic-manipulation-with-a.png)

**🎯 问题**
长时程失败往往没有明确 onset：小偏差可能几十步之后才导致不可恢复结果，当前单帧看起来甚至完全正常。

**💡 核心思路**
用 action-conditioned world model 提取 observed / predicted latent，经 causal Transformer 聚合时序信息，再用 functional conformal prediction 构造随时间变化的报警阈值。

**🔎 为什么重要**
不依赖 VLA logits 或 hidden states，只需 observation + action chunk 接口，更适合跨 policy 的统一监测。

[Paper](https://arxiv.org/abs/2606.23085) · [PDF](https://arxiv.org/pdf/2606.23085.pdf)   `arXiv:2606.23085`

### P27 · SafeVLA: Towards Safety Alignment of Vision-Language-Action Model via Constrained Learning

`VLA` `Safe RL` `CMDP`   **Training-time Alignment**

![Representative figure for P27](assets/figures/27_safevla-towards-safety-alignment-of-vision-language-action-model-via-con.png)

**🎯 问题**
普通模仿学习主要展示“应该怎么做”，危险状态在真实数据里很少，模型未必真正学到安全边界。

**💡 核心思路**
将任务收益与累计安全代价写成 constrained MDP，先主动诱发危险轨迹，再根据当前违规程度动态调节安全约束进行 RL。

**🔎 为什么重要**
把安全从部署后的外挂检测，前移到策略训练目标中，并显式建模 task performance–safety trade-off。

[Paper](https://arxiv.org/abs/2503.03480) · [PDF](https://arxiv.org/pdf/2503.03480.pdf)   `arXiv:2503.03480`

### P28 · SafeDojo: Safe Reinforcement Learning for VLA via Interactive World Model

`VLA` `World Model` `Safe RL`   **Training-time Safe RL**

![Representative figure for P28](assets/figures/28_safedojo-safe-reinforcement-learning-for-vla-via-interactive-world-model.png)

**🎯 问题**
安全强化学习需要真正经历危险状态，但真实机器人不能为了训练反复碰撞、摔物体。

**💡 核心思路**
把 interactive world model 当作可安全犯错的虚拟训练场，分别评估 imagined rollout 的任务进展和风险代价，再做 constrained RL 更新。

**🔎 为什么重要**
世界模型不只是预测器，也可以成为低成本的 safety exploration environment。

[Paper](https://arxiv.org/abs/2606.20698) · [PDF](https://arxiv.org/pdf/2606.20698.pdf)   `arXiv:2606.20698`

### P29 · SafeAlign-VLA: A Negative-Enhanced Safe Alignment Framework for Risk-Aware Autonomous Driving

`Driving VLA` `Negative Data` `Preference`   **Safety Alignment**

![Representative figure for P29](assets/figures/29_safealign-vla-a-negative-enhanced-safe-alignment-framework-for-risk-awar.png)

**🎯 问题**
专家数据大多只有正确轨迹，模型很少看到“看似合理但其实危险”的 hard negative。

**💡 核心思路**
为高风险场景构造危险轨迹与安全替代轨迹对，先学习识别/修正，再通过偏好式强化扩大 safe–unsafe trajectory margin。

**🔎 为什么重要**
用有针对性的 negative examples 直接刻画安全决策边界，比随机错误动作更有训练价值。

[Paper](https://arxiv.org/abs/2605.19524) · [PDF](https://arxiv.org/pdf/2605.19524.pdf)   `arXiv:2605.19524`

### P30 · SafeBimanual: Diffusion-based Trajectory Optimization for Safe Bimanual Manipulation

`Bimanual` `Diffusion` `Trajectory Optimization`   **Test-time Constraint**

![Representative figure for P30](assets/figures/30_safebimanual-diffusion-based-trajectory-optimization-for-safe-bimanual-m.png)

**🎯 问题**
双臂操作的防碰撞、防撕裂等约束随任务阶段变化，固定 rule set 很难兼顾所有情况。

**💡 核心思路**
由 VLM 判断当前任务阶段并选择安全代价，在预训练 diffusion policy 的每一步 denoising 中对候选轨迹做 test-time guidance。

**🔎 为什么重要**
无需重训主策略，就能在动作生成过程中按场景动态注入安全约束。

[Paper](https://arxiv.org/abs/2508.18268) · [PDF](https://arxiv.org/pdf/2508.18268.pdf)   `arXiv:2508.18268`

### P31 · Neuro-Symbolic Safety Guidance for Vision-Language-Action Models via Constrained Flow Matching

`VLA` `Flow Matching` `Neuro-symbolic`   **Generation-time Constraint**

![Representative figure for P31](assets/figures/31_neuro-symbolic-safety-guidance-for-vision-language-action-models-via-con.png)

**🎯 问题**
只检查“下一步会不会撞”对 action chunk 太晚：前几步安全，第五步可能已经注定违反约束。

**💡 核心思路**
在 flow-matching 每个中间生成步骤都展开完整未来轨迹，用符号安全约束检查并对生成方向做尽可能小的修正。

**🔎 为什么重要**
把 runtime shield 提前到生成过程中，实现对整段未来动作的持续前瞻检查。

[Paper](https://arxiv.org/abs/2607.01378) · [PDF](https://arxiv.org/pdf/2607.01378.pdf)   `arXiv:2607.01378`

### P32 · Safe Vision Language Action Models via Barrier Enhanced Flow Matching

`VLA` `Barrier Function` `Flow Matching`   **Generation-time Constraint**

![Representative figure for P32](assets/figures/32_safe-vision-language-action-models-via-barrier-enhanced-flow-matching.png)

**🎯 问题**
生成完再强行截断/投影虽然能避碰，却可能让动作偏离原策略分布过大、破坏任务能力。

**💡 核心思路**
将整段 action chunk 的 barrier-based safety condition 注入 flow matching，寻找满足约束同时尽量保持原策略行为的最小修正。

**🔎 为什么重要**
同时考虑“必须安全”和“不要为安全改得太多”，并给出动作分布偏移的理论分析。

[Paper](https://arxiv.org/abs/2607.29569) · [PDF](https://arxiv.org/pdf/2607.29569.pdf)   `arXiv:2607.29569`

### P33 · ProbeAct: Probe-Guided Training-Free Failure Recovery in Vision-Language-Action Models

`VLA` `Probe` `Failure Recovery`   **Runtime Recovery**

![Representative figure for P33](assets/figures/33_probeact-probe-guided-training-free-failure-recovery-in-vision-language-.png)

**🎯 问题**
最终动作错并不一定说明模型完全看错了；失败时 hidden representation 里可能仍保留准确的目标几何信息。

**💡 核心思路**
从 hidden features probe 目标 3D 位置，用状态机判断接近/抓取/搬运/放置阶段，检测偏离后通过分层安全约束做在线最小动作修正。

**🔎 为什么重要**
证明部分 VLA 失败发生在“正确内部表示 → 错误最终动作”这一段，因此可以 training-free 地局部恢复。

[Paper](https://arxiv.org/abs/2606.09740) · [PDF](https://arxiv.org/pdf/2606.09740.pdf)   `arXiv:2606.09740`

### P34 · Modular Safety Guardrails Are Necessary for Foundation-Model-Enabled Robots in the Real World

`Foundation Model` `Guardrail` `System Design`   **System Guardrail**

![Representative figure for P34](assets/figures/34_modular-safety-guardrails-are-necessary-for-foundation-model-enabled-rob.png)

**🎯 问题**
现实机器人风险跨动作、决策和人因层面，让单个端到端模型承担全部安全职责既难验证也难维护。

**💡 核心思路**
提出模块化 guardrail 架构：不同模块分别监测不同风险，按风险放行/修改/重规划/阻止，并显式传递上游风险结构和协调保守程度。

**🔎 为什么重要**
给出比“再训练一个更安全的大模型”更工程化的系统安全路线。

[Paper](https://arxiv.org/abs/2602.04056) · [PDF](https://arxiv.org/pdf/2602.04056.pdf)   `arXiv:2602.04056`

### P35 · Verifiable Foundation Models for Robot Safety

`Foundation Model` `Formal` `Safety Module`   **Formal Verification**

![Representative figure for P35](assets/figures/35_verifiable-foundation-models-for-robot-safety.png)

**🎯 问题**
直接形式化验证数十亿参数的 VLA 几乎不可行，但许多最终物理安全约束只依赖少量距离/位置等低维变量。

**💡 核心思路**
让大模型负责复杂任务理解，只输出受限任务信息；小型安全动作模块再结合低维安全传感器给出最终动作，并只对这个模块做形式化验证。

**🔎 为什么重要**
把“智能”与“可证明安全”解耦，使 foundation-model robot 获得可计算的 verification boundary。

[Paper](https://arxiv.org/abs/2606.23754) · [PDF](https://arxiv.org/pdf/2606.23754.pdf)   `arXiv:2606.23754`

### P36 · LabGuard: Grounding Natural-Language Laboratory Rules into Runtime Guards for Embodied Laboratory Agents

`Lab Agent` `Rules` `Runtime`   **Runtime Guard**

![Representative figure for P36](assets/figures/36_labguard-grounding-natural-language-laboratory-rules-into-runtime-guards.png)

**🎯 问题**
现实安全要求常写在自然语言手册里，如“加热器开启时易燃物不得靠近”，控制器却无法直接执行这些句子。

**💡 核心思路**
把规则解析成对象—条件—动作范围—风险程度—干预方式等 typed IR，再自动编译成运行时 monitor，在执行前选择放行、修改或阻止。

**🔎 为什么重要**
补齐从自然语言安全知识到可执行 runtime guard 的最后一公里。

[Paper](https://arxiv.org/abs/2606.31045) · [PDF](https://arxiv.org/pdf/2606.31045.pdf)   `arXiv:2606.31045`

### P37 · Pre-VLA: Preemptive Runtime Verification for Reliable Vision-Language-Action and World-Model Rollouts

`VLA` `Runtime` `Resampling`   **Pre-execution Verification**

![Representative figure for P37](assets/figures/37_pre-vla-preemptive-runtime-verification-for-reliable-vision-language-act.png)

**🎯 问题**
坏 action chunk 一旦真实执行会直接失败；如果先送入 world model，又会污染后续 imagined rollout 并浪费计算。

**💡 核心思路**
动作块生成后同时预测 safety confidence 和 long-term advantage；不合格则在预算内重采样，预算耗尽后从候选中选综合价值最优者。

**🔎 为什么重要**
把可靠性检查前移到“动作进入物理世界/世界模型之前”，从 post-hoc detection 变成 proactive verification。

[Paper](https://arxiv.org/abs/2605.22446) · [PDF](https://arxiv.org/pdf/2605.22446.pdf)   `arXiv:2605.22446`

---

## 🚧 Open Research Gaps

从目前 43 篇工作的分布可以看到，**攻击安全与模型决策保障已经形成较密集的研究群，而“软硬件运行误差 → 闭环可信退化 → 在线恢复”仍明显不足。** 特别值得继续补充：

1. **Hardware fault → embodied behavior propagation**：GPU / NPU soft error、memory bit flip、传感器异常、关节/执行器退化如何跨层传播到最终动作与物理后果。
2. **Approximate computing under closed loop**：quantization、pruning、cache、early-exit、speculative execution 等优化不应只看离线精度，而应评价长时程误差累积与恢复。
3. **Pure black-box decision assurance**：只依赖 observation / action / physical feedback，不读取 hidden state，也不假设可访问动力学模型的通用异常监测。
4. **Unified trust state**：把 security、robustness、decision reliability 的多源信号统一成可用于 runtime scheduling / verification / fallback 的可信状态。

## 🤝 Contributing

欢迎 PR / Issue 补充新论文、代码、项目主页或更合适的代表图。新增论文建议至少说明：**非可信来源、攻击/故障位置、检测信号、干预阶段、是否需要访问模型内部状态**。详细格式见 [`CONTRIBUTING.md`](CONTRIBUTING.md)。

## 📦 Repository Structure

```text
Awesome-Embodied-Trustworthy-Execution/
├── README.md
├── README_EN.md
├── CONTRIBUTING.md
├── assets/
│   ├── banner.svg
│   ├── taxonomy.svg
│   └── figures/              # representative figure for each paper
├── data/
│   ├── papers_detailed.csv   # problem / idea / significance
│   └── paper_links_full.csv  # primary and supplementary paper links
├── scripts/
│   └── extract_figure1.py
└── .github/ISSUE_TEMPLATE/
    └── paper_addition.md
```

## 📌 Figure & Citation Notice

Paper titles, figures, and technical ideas belong to their respective authors/publishers. Figures in this repository are cropped representative excerpts used for scholarly review and navigation; please follow the original paper/license when reusing them elsewhere. If you are an author and would like a figure replaced or removed, please open an Issue.

---

If this list helps your research, consider giving the repository a ⭐ and contributing new work.
**Trustworthy embodied AI is not only about making the model better—it is about making the entire closed loop dependable.**
