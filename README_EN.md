[简体中文](README.md) · **English**
![Awesome Embodied Trustworthy Execution banner](assets/banner.svg) [![Awesome](https://awesome.re/badge.svg)](https://awesome.re) ![43 papers](https://img.shields.io/badge/Papers-43-2563eb?style=flat-square) ![VLA WAM VLN](https://img.shields.io/badge/Embodied_AI-VLA%20%7C%20WAM%20%7C%20VLN-0f766e?style=flat-square) ![Trustworthy Execution](https://img.shields.io/badge/Focus-Trustworthy_Execution-b45309?style=flat-square) ![Updated 2026-08-29](https://img.shields.io/badge/Updated-2026--08--29-64748b?style=flat-square) ![PRs welcome](https://img.shields.io/badge/PRs-Welcome-16a34a?style=flat-square)

**A curated research map for security, reliability, and decision assurance in embodied AI.**

`Trust` · `Detect` · `Verify` · `Mitigate` · `Recover`

## 👥 Authors

[Zihao Zheng (郑子豪)](https://github.com/zhengzihaoPKU) · [Hangyu Cao (曹航语)](https://github.com/i6bimua) · [Zhihao Mao (毛郅皓)](https://github.com/lusunn111)

> [!NOTE]
> **The organizing principle is the source of non-trustworthiness.** Attack surfaces, evaluation methods, training strategies, and runtime mechanisms are not mixed at the same level. This keeps malicious attacks, software/hardware errors, and model-originated decision anomalies tied to distinct research questions.

## ✨ Why this list?

Unlike conventional digital AI, an embodied model operates inside a **perception → reasoning → action → physical feedback** loop. A small visual deviation, computational approximation, or decision anomaly can propagate and grow throughout continuous execution. This repository therefore focuses on **Trustworthy Embodied Execution**: detecting untrustworthy states, stopping risk before it enters the execution chain, and correcting, replanning, or recovering when needed.

![Source-first taxonomy](assets/taxonomy.svg)

### Three sources of non-trustworthiness

| Layer                                        | Core question                                                            | Typical causes                                                                     | Typical response                                            |
| -------------------------------------------- | ------------------------------------------------------------------------ | ---------------------------------------------------------------------------------- | ----------------------------------------------------------- |
| 🛡️**I. Malicious Attacks**           | Is an adversary actively manipulating the system?                        | Patch or 3D texture, jailbreak, prompt injection, WAM integrity attack             | Red teaming, attack detection, adversarial defense          |
| ⚙️**II. Software / Hardware Errors** | Can system error break the closed loop without an attacker?              | Sensor noise, viewpoint shift, pruning or quantization, hardware or actuator fault | Robustness, fault tolerance, recovery                       |
| 🧠**III. Decision Anomalies**          | Is the model making a wrong decision despite normal inputs and hardware? | Oscillation, task drift, imagination–reality mismatch, long-horizon failure       | Monitoring, verification, constraints, replanning, recovery |

> [!IMPORTANT]
> **Black-box attack ≠ black-box anomaly monitoring.** In AdvNav and BadWAM, *black-box* means the attacker has no gradient access. In *How VLAs Fail Differently*, black-box monitoring means the deployment-side monitor reads no internal model state and observes only action outputs.

## 🧭 Quick navigation

- [👥 Authors](#-authors)
- [✨ Why this list?](#-why-this-list)
  - [Three sources of non-trustworthiness](#three-sources-of-non-trustworthiness)
- [🧭 Quick navigation](#-quick-navigation)
- [🔥 Featured papers](#-featured-papers)
- [🗺️ Research landscape](#️-research-landscape)
  - [Surveys and frameworks](#surveys-and-frameworks)
  - [I. Malicious attacks and defense](#i-malicious-attacks-and-defense)
  - [II. Software and hardware errors and robustness](#ii-software-and-hardware-errors-and-robustness)
  - [III. Decision anomaly detection and runtime assurance](#iii-decision-anomaly-detection-and-runtime-assurance)
- [🚧 Open research gaps](#-open-research-gaps)
- [🤝 Contributing](#-contributing)
- [📝 Citation](#-citation)
- [📦 Repository structure](#-repository-structure)
- [📌 Figure and citation notice](#-figure-and-citation-notice)

## 🔥 Featured papers

|            ID | Paper                                                                                                                                           | Why read it first?                                           |
| ------------: | ----------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------ |
| **P01** | [Safety in Embodied AI: A Survey of Risks, Attacks, and Defenses](https://arxiv.org/abs/2605.02900)                                                | A broad entry point to the embodied-safety landscape         |
| **P04** | [JailWAM: Jailbreaking World Action Models in Robot Control](https://arxiv.org/abs/2604.05498)                                                     | WAM jailbreaks evaluated by their physical consequences      |
| **P07** | [When to Trust Imagination: Adaptive Action Execution for World Action Models](https://arxiv.org/abs/2605.06222)                                   | Closed-loop verification of imagined versus observed futures |
| **P08** | [Tex3D: Objects as Attack Surfaces via Adversarial 3D Textures for Vision-Language-Action Models](https://arxiv.org/abs/2604.01618)                | Extends physical attacks from 2D patches to 3D textures      |
| **P19** | [RedVLA: Physical Red Teaming for Vision-Language-Action Models](https://arxiv.org/abs/2604.22591)                                                 | Trajectory-guided physical red teaming                       |
| **P20** | [LIBERO-Plus: In-depth Robustness Analysis of Vision-Language-Action Models](https://arxiv.org/abs/2510.13626)                                     | VLA robustness under seven dimensions of realistic variation |
| **P23** | [How VLAs Fail Differently: Black-Box Action Monitoring Reveals Architecture-Specific Failure Signatures](https://arxiv.org/abs/2605.28726)        | Pure black-box monitoring of action outputs                  |
| **P26** | [Foresight: Failure Detection for Long-Horizon Robotic Manipulation with Action-Conditioned World Model Latents](https://arxiv.org/abs/2606.23085) | Long-horizon failure prediction with world-model latents     |
| **P37** | [Pre-VLA: Preemptive Runtime Verification for Reliable Vision-Language-Action and World-Model Rollouts](https://arxiv.org/abs/2605.22446)          | Pre-execution verification with budgeted resampling          |
| **P38** | [Don&#39;t Run with Scissors: Pruning Breaks VLA Models but They Can Be Recovered](https://arxiv.org/abs/2510.08464)                               | How model compression degrades closed-loop reliability       |

## 🗺️ Research landscape

### Surveys and frameworks

|  ID | Paper                                                                                                                    | Role                 |
| --: | ------------------------------------------------------------------------------------------------------------------------ | -------------------- |
| P01 | [Safety in Embodied AI: A Survey of Risks, Attacks, and Defenses](https://arxiv.org/abs/2605.02900)                         | Survey               |
| P02 | [Safe Embodied AI for Long-horizon Tasks: A Cross-layer Analysis of Robotic Manipulation](https://arxiv.org/abs/2606.05660) | Survey / framework   |
| P03 | [What Breaks Embodied AI Security: LLM Vulnerabilities, CPS Flaws, or Something Else?](https://arxiv.org/abs/2602.17345)    | Survey / system view |
| P39 | [Security of World-Model-Based Embodied AI: A Lifecycle of Threats, Defenses, and Evaluation](https://arxiv.org/abs/2607.28226) | Lifecycle security survey |
| P43 | [Security of Foundation-Model-Powered Embodied Agents: Attack Surfaces, Attacks, Defenses, and Evaluation](https://arxiv.org/abs/2608.16843) | Trust-boundary survey |

### I. Malicious attacks and defense

|  ID | Paper                                                                                                                                              | Role                      |
| --: | -------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------- |
| P04 | [JailWAM: Jailbreaking World Action Models in Robot Control](https://arxiv.org/abs/2604.05498)                                                        | Attack + evaluation       |
| P05 | [BadWAM: When World-Action Models Dream Right but Act Wrong](https://arxiv.org/abs/2607.15207)                                                        | Attack                    |
| P06 | [Attacking the Trusted Imagination: Oracle-Level Integrity Attacks on Imagine-then-Act World Models](https://arxiv.org/abs/2606.22966)                | Attack + detection        |
| P08 | [Tex3D: Objects as Attack Surfaces via Adversarial 3D Textures for Vision-Language-Action Models](https://arxiv.org/abs/2604.01618)                   | Physical attack           |
| P09 | [TRAP: Hijacking VLA CoT-Reasoning via Adversarial Patches](https://arxiv.org/abs/2603.23117)                                                         | Physical attack           |
| P10 | [VLA-Hijack: A Transferable Patch Attack against Vision-Language-Action Models via Visual Proprioception Hijacking](https://arxiv.org/abs/2605.28083) | Physical attack           |
| P11 | [FreezeVLA: Action-Freezing Attacks against Vision-Language-Action Models](https://arxiv.org/abs/2509.19870)                                          | Attack                    |
| P12 | [When Alignment Fails: Multimodal Adversarial Attacks on Vision-Language-Action Models](https://arxiv.org/abs/2511.16203)                             | Attack toolbox            |
| P13 | [Exploring the Adversarial Vulnerabilities of Vision-Language-Action Models in Robotics](https://arxiv.org/abs/2411.13587)                            | Attack                    |
| P14 | [AdvNav: Behavior-Guided Black-Box Adversarial Attacks on Vision-Language Navigation](https://arxiv.org/abs/2607.11063)                               | Black-box attack          |
| P15 | [Adversarial Attacks on Robotic Vision Language Action Models](https://arxiv.org/abs/2506.03350)                                                      | Attack                    |
| P16 | [Manipulating Multimodal Agents via Cross-Modal Prompt Injection](https://arxiv.org/abs/2504.14348)                                                   | Attack                    |
| P17 | [Hijacking Robots with a Piece of Paper: A Systematic Study of Physical Prompt Injection in VLM-Controlled Robots](https://arxiv.org/abs/2608.05715)  | Physical prompt injection |
| P18 | [ANNIE: Be Careful of Your Robots](https://arxiv.org/abs/2509.03383)                                                                                  | Benchmark + attack        |
| P19 | [RedVLA: Physical Red Teaming for Vision-Language-Action Models](https://arxiv.org/abs/2604.22591)                                                    | Red team + guard          |
| P40 | [VLAGuard: A Framework for Evaluating and Mitigating Physical Attention Hijacking in Vision-Language-Action Robots within Wireless Sensor Networks](https://arxiv.org/abs/2608.01028) | Attack + defense |
| P41 | [Hidden in Plain Sight: Diffusion-Based Unrestricted Robotic Attacks on Vision-Language-Action Models](https://arxiv.org/abs/2608.10393)               | Physical attack           |
| P42 | [Bit-Flip Attacks on Vision-Language-Action Models: Action-Decoding Architecture Shapes the Vulnerability](https://arxiv.org/abs/2608.15475)          | Weight-integrity attack   |

### II. Software and hardware errors and robustness

|  ID | Paper                                                                                                                                       | Role                    |
| --: | ------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------- |
| P20 | [LIBERO-Plus: In-depth Robustness Analysis of Vision-Language-Action Models](https://arxiv.org/abs/2510.13626)                                 | Robustness benchmark    |
| P21 | [LIBERO-Safety: A Comprehensive Benchmark for Physical and Semantic Safety in Vision-Language-Action Models](https://arxiv.org/abs/2606.23686) | Safety benchmark        |
| P24 | [When and How Severely: Scenario-Specific Safety Envelopes for Driving VLAs](https://arxiv.org/abs/2606.14238)                                 | Safety envelope         |
| P38 | [Don&#39;t Run with Scissors: Pruning Breaks VLA Models but They Can Be Recovered](https://arxiv.org/abs/2510.08464)                           | Compression reliability |

### III. Decision anomaly detection and runtime assurance

|  ID | Paper                                                                                                                                           | Role                       |
| --: | ----------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------- |
| P07 | [When to Trust Imagination: Adaptive Action Execution for World Action Models](https://arxiv.org/abs/2605.06222)                                   | Runtime verification       |
| P22 | [ForesightSafety-VLA: A Unified Diagnostic Safety Benchmark for Vision-Language-Action Models](https://arxiv.org/abs/2606.27079)                   | Diagnostic benchmark       |
| P23 | [How VLAs Fail Differently: Black-Box Action Monitoring Reveals Architecture-Specific Failure Signatures](https://arxiv.org/abs/2605.28726)        | Black-box runtime monitor  |
| P25 | [SAFE: Multitask Failure Detection for Vision-Language-Action Models](https://arxiv.org/abs/2506.09937)                                            | Runtime failure detection  |
| P26 | [Foresight: Failure Detection for Long-Horizon Robotic Manipulation with Action-Conditioned World Model Latents](https://arxiv.org/abs/2606.23085) | Runtime failure detection  |
| P27 | [SafeVLA: Towards Safety Alignment of Vision-Language-Action Model via Constrained Learning](https://arxiv.org/abs/2503.03480)                     | Training-time alignment    |
| P28 | [SafeDojo: Safe Reinforcement Learning for VLA via Interactive World Model](https://arxiv.org/abs/2606.20698)                                      | Training-time safe RL      |
| P29 | [SafeAlign-VLA: A Negative-Enhanced Safe Alignment Framework for Risk-Aware Autonomous Driving](https://arxiv.org/abs/2605.19524)                  | Safety alignment           |
| P30 | [SafeBimanual: Diffusion-based Trajectory Optimization for Safe Bimanual Manipulation](https://arxiv.org/abs/2508.18268)                           | Test-time constraint       |
| P31 | [Neuro-Symbolic Safety Guidance for Vision-Language-Action Models via Constrained Flow Matching](https://arxiv.org/abs/2607.01378)                 | Generation-time constraint |
| P32 | [Safe Vision Language Action Models via Barrier Enhanced Flow Matching](https://arxiv.org/abs/2607.29569)                                          | Generation-time constraint |
| P33 | [ProbeAct: Probe-Guided Training-Free Failure Recovery in Vision-Language-Action Models](https://arxiv.org/abs/2606.09740)                         | Runtime recovery           |
| P34 | [Modular Safety Guardrails Are Necessary for Foundation-Model-Enabled Robots in the Real World](https://arxiv.org/abs/2602.04056)                  | System guardrail           |
| P35 | [Verifiable Foundation Models for Robot Safety](https://arxiv.org/abs/2606.23754)                                                                  | Formal verification        |
| P36 | [LabGuard: Grounding Natural-Language Laboratory Rules into Runtime Guards for Embodied Laboratory Agents](https://arxiv.org/abs/2606.31045)       | Runtime guard              |
| P37 | [Pre-VLA: Preemptive Runtime Verification for Reliable Vision-Language-Action and World-Model Rollouts](https://arxiv.org/abs/2605.22446)          | Pre-execution verification |

For representative figures and concise notes on each paper's problem, core idea, and significance, see the [Chinese detailed edition](README.md). The paper titles and arXiv links above are language-independent.

## 🚧 Open research gaps

The collection is relatively dense in attack security and model-decision assurance, while the path from **software/hardware runtime error → degraded closed-loop trust → online recovery** remains underexplored.

1. **Hardware fault → embodied behavior propagation:** how GPU/NPU soft errors, memory bit flips, sensor anomalies, and joint or actuator degradation propagate across layers into actions and physical consequences.
2. **Approximate computing under closed-loop execution:** quantization, pruning, caching, early exit, and speculative execution should be evaluated for long-horizon error accumulation and recovery, not only offline accuracy.
3. **Pure black-box decision assurance:** general anomaly monitoring based only on observations, actions, and physical feedback, without hidden-state access or an available dynamics model.
4. **Unified trust state:** combining security, robustness, and decision-reliability signals into a state usable for runtime scheduling, verification, and fallback.

## 🤝 Contributing

Pull requests and issues for new papers, code, project pages, or improved representative figures are welcome. A new entry should identify the **source of non-trustworthiness, attack or fault location, detection signal, intervention stage, and required model visibility**. See [CONTRIBUTING.md](CONTRIBUTING.md) for the submission format.

## 📝 Citation

If this project helps your research, please cite it using the following BibTeX entry:

```bibtex
@misc{zheng2026awesomeembodiedtrustworthyexecution,
  title        = {Awesome Embodied Trustworthy Execution},
  author       = {Zheng, Zihao and Cao, Hangyu and Mao, Zhihao},
  year         = {2026},
  howpublished = {\url{https://github.com/zhengzihaoPKU/Awesome-Embodied-Trustworthy-Execution}},
  note         = {A curated research map for security, reliability, and decision assurance in embodied AI}
}
```

## 📦 Repository structure

```text
Awesome-Embodied-Trustworthy-Execution/
├── README.md                 # Chinese detailed edition
├── README_EN.md              # English edition
├── CONTRIBUTING.md
├── assets/
│   ├── banner.svg
│   ├── taxonomy.svg
│   └── figures/              # representative figure for each paper
├── data/
│   ├── papers_detailed.csv   # problem / idea / significance
│   └── paper_links_full.csv  # primary and supplementary paper links
└── .github/ISSUE_TEMPLATE/
    └── paper_addition.md
```

## 📌 Figure and citation notice

Paper titles, figures, and technical ideas belong to their respective authors and publishers. Figures in this repository are cropped representative excerpts used for scholarly review and navigation. Follow the original paper's license when reusing them. Authors may open an issue to request replacement or removal of a figure.

---

If this list helps your research, consider giving the repository a ⭐ and contributing new work.
**Trustworthy embodied AI is not only about making the model better—it is about making the entire closed loop dependable.**
