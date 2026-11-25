[简体中文](README.md) · **English**

# 🤖 Awesome Embodied Trustworthy Execution

![Efficient and trustworthy cross-layer embodied execution](assets/banner.svg)

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re) [![Stars](https://img.shields.io/github/stars/zhengzihaoPKU/Awesome-Embodied-Trustworthy-Execution?style=flat-square&logo=github)](https://github.com/zhengzihaoPKU/Awesome-Embodied-Trustworthy-Execution/stargazers) ![Resources](https://img.shields.io/badge/Resources-138-2563EB?style=flat-square) [![License MIT](https://img.shields.io/badge/License-MIT-blue?style=flat-square)](LICENSE) [![PRs Welcome](https://img.shields.io/badge/PRs-Welcome-16A34A?style=flat-square)](CONTRIBUTING.md)

A companion academic resource for the survey below, covering **efficient execution, trustworthy assurance, and cross-layer coordination** in VLA, WAM, and related embodied systems. The literature is organized according to the survey’s four-layer system framework.

📄 **Companion survey:** *Efficient and Trustworthy Execution of Embodied AI: A Cross-Layer Survey under System-Perspective*.

👥 Maintainers: [Zihao Zheng](https://github.com/zhengzihaoPKU) · [Hangyu Cao](https://github.com/i6bimua) · [Zhihao Mao](https://github.com/lusunn111)

📚 [Detailed catalog](data/papers_detailed.csv) · [Resource links](data/paper_links_full.csv) · [Curation guidelines](CONTRIBUTING.md)

<a id="updates"></a>
## 🔥 News & Updates

- **2026-11-25:** Reorganized the collected literature according to the survey's new framework and refined the repository's presentation structure.

<a id="contents"></a>
## 🧭 Table of Contents

- [Research Scope & Taxonomy](#about-and-taxonomy)
  - [Research Scope](#research-scope)
  - [Literature Taxonomy](#literature-taxonomy)
  - [Four-Layer System Architecture](#system-architecture)
  - [Efficiency–Trustworthiness Trade-offs](#efficiency-tradeoffs)
- [Research Timeline](#research-timeline)
- [Background and Related Work](#background-and-related-work)
  - [Related Surveys](#section-0-1)
  - [Foundation Models](#section-0-2)
- [🧠 1. Model Software](#model-software)
  - [1.1 Model Risk Sources and Behavioral Effects](#section-1-1)
  - [1.2 Evidence for Model Risk Assessment](#section-1-2)
  - [1.3 Model Protection and Behavioral Evaluation](#section-1-3)
- [⚙️ 2. Runtime Systems](#runtime-systems)
  - [2.1 Runtime Risk Sources and Execution Effects](#section-2-1)
  - [2.2 Evidence for Runtime Risk Assessment](#section-2-2)
  - [2.3 Runtime Protection and Execution Evaluation](#section-2-3)
- [💻 3. Computing Hardware](#computing-hardware)
  - [3.1 Platform Integrity and Fault Tolerance](#section-3-1)
  - [3.2 Deployment Characteristics and Resource Constraints](#section-3-2)
  - [3.3 State Management and Coordinated Execution](#section-3-3)
- [🦾 4. Physical Execution and Feedback](#physical-execution-and-feedback)
  - [4.1 Physical Execution Deviations and Feedback Evidence](#section-4-1)
  - [4.2 Physical Risk Monitoring and Prediction](#section-4-2)
  - [4.3 Execution Intervention and Safe Recovery](#section-4-3)
  - [4.4 Recovery Outcomes and Feedback Limitations](#section-4-4)
- [5. Evaluation and Benchmarks](#evaluation-and-benchmarks)
  - [5.1 Benchmarks and Datasets](#section-5-1)
  - [5.2 Evaluation Studies](#section-5-2)
- [Contributing](#contributing)
- [Citation](#citation)
- [Acknowledgements & Contributors](#acknowledgements)
- [Star History](#star-history)

<details>
<summary>Expand the complete technical taxonomy</summary>

- [Research Scope & Taxonomy](#about-and-taxonomy)
  - [Research Scope](#research-scope)
  - [Literature Taxonomy](#literature-taxonomy)
  - [Four-Layer System Architecture](#system-architecture)
  - [Efficiency–Trustworthiness Trade-offs](#efficiency-tradeoffs)
- [Research Timeline](#research-timeline)
- [Background and Related Work](#background-and-related-work)
  - [Related Surveys](#section-0-1)
  - [Foundation Models](#section-0-2)
- [🧠 1. Model Software](#model-software)
  - [1.1 Model Risk Sources and Behavioral Effects](#section-1-1)
    - [a) Malicious manipulation of model inputs and resources](#section-1-1-1)
    - [b) Environmental disturbances and observation changes](#section-1-1-2)
    - [c) Computational errors and action deviations](#section-1-1-3)
    - [d) Decision anomalies in task understanding and action generation](#section-1-1-4)
  - [1.2 Evidence for Model Risk Assessment](#section-1-2)
    - [a) Malicious input and model compromise detection](#section-1-2-1)
    - [b) Observation shift and failure risk assessment](#section-1-2-2)
    - [c) Computational error detection and behavioral sensitivity](#section-1-2-3)
    - [d) Task grounding and candidate quality assessment](#section-1-2-4)
  - [1.3 Model Protection and Behavioral Evaluation](#section-1-3)
    - [a) Input repair and representation robustness](#section-1-3-1)
    - [b) Robustness against computational perturbations](#section-1-3-2)
    - [c) Decision constraints and candidate verification](#section-1-3-3)
- [⚙️ 2. Runtime Systems](#runtime-systems)
  - [2.1 Runtime Risk Sources and Execution Effects](#section-2-1)
    - [a) Malicious interference with communication](#section-2-1-1)
    - [b) Environmental changes during inference and action handoff](#section-2-1-2)
    - [c) Computational deviations from approximation and faults](#section-2-1-3)
    - [d) Decision anomalies at candidate release](#section-2-1-4)
  - [2.2 Evidence for Runtime Risk Assessment](#section-2-2)
    - [a) Communication permission and behavior checks](#section-2-2-1)
    - [b) Observation age and state consistency checks](#section-2-2-2)
    - [c) Configuration deviation and computation integrity checks](#section-2-2-3)
    - [d) Candidate quality and regeneration evidence](#section-2-2-4)
  - [2.3 Runtime Protection and Execution Evaluation](#section-2-3)
    - [a) Communication protection and temporal coordination](#section-2-3-1)
    - [b) Computation adaptation and fault recovery](#section-2-3-2)
    - [c) Candidate verification and supervision scheduling](#section-2-3-3)
- [💻 3. Computing Hardware](#computing-hardware)
  - [3.1 Platform Integrity and Fault Tolerance](#section-3-1)
    - [a) Integrity of executable code and model state](#section-3-1-1)
    - [b) Detection and recovery of transient errors](#section-3-1-2)
    - [c) Device diagnostics and hardware redundancy](#section-3-1-3)
  - [3.2 Deployment Characteristics and Resource Constraints](#section-3-2)
    - [a) Workload characteristics and deployment costs](#section-3-2-1)
    - [b) Hardware realization of approximations](#section-3-2-2)
  - [3.3 State Management and Coordinated Execution](#section-3-3)
    - [a) Computation state maintenance and verification support](#section-3-3-1)
    - [b) Competition between inference and assurance](#section-3-3-2)
- [🦾 4. Physical Execution and Feedback](#physical-execution-and-feedback)
  - [4.1 Physical Execution Deviations and Feedback Evidence](#section-4-1)
    - [a) Attacks realized through physical interaction](#section-4-1-1)
    - [b) Changing environments and degrading bodies](#section-4-1-2)
    - [c) Local action quality versus task progression](#section-4-1-3)
  - [4.2 Physical Risk Monitoring and Prediction](#section-4-2)
    - [a) Cross-modal and attack-aware consistency](#section-4-2-1)
    - [b) Physical constraints and imminent hazards](#section-4-2-2)
    - [c) Sensor, actuator, and feedback integrity](#section-4-2-3)
    - [d) Progress monitoring and failure localization](#section-4-2-4)
  - [4.3 Execution Intervention and Safe Recovery](#section-4-3)
    - [a) From malicious evidence to bounded action protection](#section-4-3-1)
    - [b) Safety constraints and context-dependent intervention](#section-4-3-2)
    - [c) Compensation under altered physical capability](#section-4-3-3)
  - [4.4 Recovery Outcomes and Feedback Limitations](#section-4-4)
    - [a) Recovering local execution and task state](#section-4-4-1)
    - [b) Assessing recovery rather than just detection](#section-4-4-2)
- [5. Evaluation and Benchmarks](#evaluation-and-benchmarks)
  - [5.1 Benchmarks and Datasets](#section-5-1)
    - [Environmental and Perceptual Robustness](#section-5-1-1)
    - [Instruction Grounding and Task Planning](#section-5-1-2)
    - [Safety and Constraint Satisfaction](#section-5-1-3)
    - [Numerical Fidelity and Efficiency](#section-5-1-4)
    - [Physical Faults and Failure Severity](#section-5-1-5)
    - [Failure Diagnosis and Recovery](#section-5-1-6)
  - [5.2 Evaluation Studies](#section-5-2)
    - [Hardware and Deployment Performance](#section-5-2-1)
    - [Runtime Timing and Resource Evaluation](#section-5-2-2)
- [Contributing](#contributing)
- [Citation](#citation)
- [Acknowledgements & Contributors](#acknowledgements)
- [Star History](#star-history)

</details>

<a id="overview"></a>
<a id="about-and-taxonomy"></a>
## 🗺️ Research Scope & Taxonomy

<a id="research-scope"></a>
### Research Scope

Embodied systems execute a continuing loop of observation, reasoning, action, and physical feedback: models propose behavior, runtimes organize computation and action release, hardware supplies processing and storage, and interaction produces motion and subsequent observations. Attacks, environmental change, computational deviations, and decision anomalies can propagate across this chain. Local acceleration must therefore be evaluated together with verification, waiting, and recovery costs.

<a id="literature-taxonomy"></a>
### Literature Taxonomy

**System layers locate mechanisms, risk sources explain initiating conditions, and assurance properties identify what must be verified.** This repository organizes the literature using the four-layer system framework, with further subdivisions by research problem and technical direction. Source, computation fidelity, freshness, and task suitability remain separate assurance dimensions. Cross-layer studies can appear in multiple relevant directions; the taxonomy below provides an overall literature index.

![Survey Fig. 3: literature taxonomy](assets/figures/survey-taxonomy.png)

*Citation and section numbers in the figure are those used in the paper.*

<a id="system-architecture"></a>
### Four-Layer System Architecture

<details>
<summary>Expand the four-layer execution architecture (Fig. 2)</summary>

![Survey Fig. 2: four-layer execution architecture](assets/figures/survey-system.png)

</details>

<a id="efficiency-tradeoffs"></a>
### Efficiency–Trustworthiness Trade-offs

<details>
<summary>Expand the cross-layer efficiency–trustworthiness trade-off (Fig. 4)</summary>

![Survey Fig. 4: efficiency and trustworthiness](assets/figures/survey-tradeoffs.png)

</details>

<a id="research-timeline"></a>
## 🕒 Research Timeline

Research spans early robot middleware verification and safety control through foundation-model behavior assessment, runtime assurance, and failure recovery, progressively covering more of the execution chain. The timeline places representative academic studies alongside industry systems to show their technical context and the interplay of model capabilities, deployment efficiency, and execution assurance. The literature lists that follow provide a complementary route through specific research questions.

![Survey Fig. 1: research timeline](assets/figures/survey-timeline.png)

*Representative research and industry outputs by first public release (survey Fig. 1).*

<a id="surveys-and-foundations"></a>
<a id="background-and-related-work"></a>
## 📚 Background and Related Work

Related surveys provide problem definitions and research context, while foundation models supply representative behavior-generation and prediction architectures. This section is background for the four-layer technical collection.

<a id="section-0-1"></a>
### Related Surveys

- <a id="p007"></a>**A Survey on Efficient Vision-Language-Action Models**. (2026, IEEE TPAMI (accepted)) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2510.24795) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://evla-survey.github.io/)
- <a id="p004"></a>**Embodied Intelligence Security with Vision-language Models: A Survey**. (2026, MIR) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://doi.org/10.1007/s11633-025-1626-x)
- <a id="p006"></a>**From Bits to Atoms: A survey of cross-layer safety in Embodied AI**. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2610.14038)
- <a id="p002"></a>**Large-scale multimodal model based embodied intelligent robots: A survey**. (2026, EAAI) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://doi.org/10.1016/j.engappai.2025.112991)
- <a id="p005"></a>**Safety in Embodied AI**: A Survey of Risks, Attacks, and Defenses. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2605.02900) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://x-zheng16.github.io/Awesome-Embodied-AI-Safety/)
- <a id="p003"></a>**Towards Robust and Secure Embodied AI: A Survey on Vulnerabilities and Attacks**. (2026, ACM CSUR) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://doi.org/10.1145/3806048)
- <a id="p001"></a>**A Survey on Robotics with Foundation Models: toward Embodied AI**. (2024, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2402.02385)

<a id="section-0-2"></a>
### Foundation Models

- <a id="p011"></a>**World Action Models are Zero-shot Policies**. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2602.15922) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/dreamzero0/dreamzero) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://dreamzero0.github.io/)
- <a id="p009"></a>**OpenVLA**: An Open-Source Vision-Language-Action Model. (2025, CoRL) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://proceedings.mlr.press/v270/kim25c.html) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/openvla/openvla) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://openvla.github.io/)
- <a id="p010"></a>**GR-2**: A Generative Video-Language-Action Model with Web-Scale Knowledge for Robot Manipulation. (2024, arXiv) [![Technical Report](https://img.shields.io/badge/Technical_Report-8C564B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2410.06158) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://gr2-manipulation.github.io/)
- <a id="p008"></a>**Octo**: An Open-Source Generalist Robot Policy. (2024, RSS) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://doi.org/10.15607/RSS.2024.XX.090) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/octo-models/octo) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://octo-models.github.io/)

<a id="model-software"></a>
## 🧠 1. Model Software

The model layer concerns how observations and task requirements become representations, predictions, and candidate actions. This section connects input manipulation, observation shifts, computational deviations, and decision anomalies with risk assessment, input and representation protection, numerical robustness, and candidate verification. A central distinction is fidelity to a specified computation versus suitability of the resulting behavior for the task.

<a id="section-1-4"></a>

<details>
<summary>Layer mechanism overview（Fig. 5）</summary>

![Survey layer overview](assets/figures/survey-model.png)

</details>

<a id="section-1-1"></a>
### 1.1 Model Risk Sources and Behavioral Effects

<a id="section-1-1-1"></a>
#### a) Malicious manipulation of model inputs and resources

- <a id="p013"></a>**DRIFT**: Derailing Denoising Trajectories of Flow-Matching VLAs with Adversarial Patch Attack. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2608.03207) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/TaeHoseong/DRIFT) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://taehoseong.github.io/DRIFT/)
- <a id="p015"></a>**Hijacking Robots with a Piece of Paper: A Systematic Study of Physical Prompt Injection in VLM-Controlled Robots**. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2608.05715)
- <a id="p012"></a>**Phantom Menace**: Exploring and Enhancing the Robustness of VLA Models Against Physical Sensor Attacks. (2026, AAAI) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2511.10008) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/ZJUshine/Phantom-Menace)
- <a id="p017"></a>**TrojanWorld**: Backdooring World-Model Agents via Imagination Steering. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2609.07051)
- <a id="p016"></a>**Goal-oriented backdoor attack against vision-language-action models via physical objects**. (2025, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2510.09269) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/trustmlyoungscientist/GoBA_attack) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://goba-attack.github.io/)
- <a id="p014"></a>**RoboPAIR**: Jailbreaking LLM-Controlled Robots. (2025, ICRA) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://doi.org/10.1109/ICRA55743.2025.11128119) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/arobey1/robopair) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://robopair.org/)
- <a id="p018"></a>**AgentPoison**: Red-teaming LLM Agents via Poisoning Memory or Knowledge Bases. (2024, NeurIPS) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2407.12784) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/AI-secure/AgentPoison)

<a id="section-1-1-2"></a>
#### b) Environmental disturbances and observation changes

- <a id="p021"></a>**Are Vision-Language-Action Models Robust to One-Step Observation Perturbations?** (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2609.32550)
- <a id="p020"></a>**LIBERO-Occ**: Evaluating and Improving Vision-Language-Action Models under Scene-Induced Occlusion via Viewpoint Imagination. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2606.10862) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/litsh/Libero-Occ)
- <a id="p019"></a>**LIBERO-Plus**: In-depth Robustness Analysis of Vision-Language-Action Models. (2025, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2510.13626) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/sylvestf/LIBERO-plus) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://sylvestf.github.io/LIBERO-plus/)

<a id="section-1-1-3"></a>
#### c) Computational errors and action deviations

- <a id="p022"></a>**Dependability analysis and hardening of vision transformers against soft errors**. (2026, J. Supercomputing) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://doi.org/10.1007/s11227-026-08373-0) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/lesterfd95/vit-fi)
- <a id="p023"></a>**QVLA**: Not All Channels Are Equal in Vision-Language-Action Model's Quantization. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2602.03782) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/AutoLab-SAI-SJTU/QVLA)
- <a id="p024"></a>**SQAP-VLA**: A Synergistic Quantization-Aware Pruning Framework for High-Performance Vision-Language-Action Models. (2025, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2509.09090) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://github.com/ecdine/SQAP-VLA)

<a id="section-1-1-4"></a>
#### d) Decision anomalies in task understanding and action generation

- <a id="p025"></a>**LIBERO-CF**: When Vision Overrides Language: Evaluating and Mitigating Counterfactual Failures in VLAs. (2026, CoRL) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2602.17659) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/yuffish/VLA-CF) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://vla-cf.github.io/)
- <a id="p027"></a>**SafePlan-Bench**: A Framework for Benchmarking and Aligning Task-Planning Safety in LLM-Based Embodied Agents. (2025, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2504.14650)
- <a id="p026"></a>**EmbodiedBench**: Comprehensive Benchmarking Multi-modal Large Language Models for Vision-Driven Embodied Agents. (2025, ICML) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://proceedings.mlr.press/v267/yang25f.html) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/EmbodiedBench/EmbodiedBench) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://embodiedbench.github.io/)

<a id="section-1-2"></a>
### 1.2 Evidence for Model Risk Assessment

<a id="section-1-2-1"></a>
#### a) Malicious input and model compromise detection

- <a id="p030"></a>**TMT**: Runtime Backdoor Detection for Vision-Language-Action Policies on Unseen Tasks. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2610.09462) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://zzr42.github.io/tmt/)
- <a id="p029"></a>**PEFTGuard**: Detecting Backdoor Attacks Against Parameter-Efficient Fine-Tuning. (2025, IEEE S&P) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2411.17453) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/Vincent-HKUSTGZ/PEFTGuard)
- <a id="p028"></a>**Sentinel: Sota model to protect against prompt injections**. (2025, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2506.05446) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://huggingface.co/qualifire/prompt-injection-sentinel)

<a id="section-1-2-2"></a>
#### b) Observation shift and failure risk assessment

- <a id="p033"></a>**PFD**: Perturbation-Based Epistemic Uncertainty for Failure Detection in Vision-Language-Action Models. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2606.20754)
- <a id="p034"></a>**VLA-Scope**: Shift-Aware Failure Prediction for Vision-Language-Action Models. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2609.21246)
- <a id="p031"></a>**Are vision language models robust to uncertain inputs?** (2025, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2505.11804)
- <a id="p032"></a>**FIPER**: Failure Prediction at Runtime for Generative Robot Policies. (2025, NeurIPS) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2510.09459) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/learnsyslab/fiper) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://tum-lsy.github.io/fiper_website/)

<a id="section-1-2-3"></a>
#### c) Computational error detection and behavioral sensitivity

- **Dependability analysis and hardening of vision transformers against soft errors**. (2026, J. Supercomputing) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://doi.org/10.1007/s11227-026-08373-0) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/lesterfd95/vit-fi)
- <a id="p035"></a>**Error-Resilient Transformers: A Novel Soft Error Vulnerability Guided Approach to Error Checking and Suppression**. (2026, JETTA) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://doi.org/10.1007/s10836-026-06227-4)
- **QVLA**: Not All Channels Are Equal in Vision-Language-Action Model's Quantization. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2602.03782) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/AutoLab-SAI-SJTU/QVLA)
- <a id="p036"></a>**Certifiably Quantisation-Robust training and inference of Neural Networks**. (2025, AISTATS) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://proceedings.mlr.press/v258/dang25a.html) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/danghue18/Certifiably-Quantisation-Robust-training-and-inference)

<a id="section-1-2-4"></a>
#### d) Task grounding and candidate quality assessment

- <a id="p037"></a>**Do Vision-Language-Action Models Understand Instructions? A Mechanistic Interpretability Study on Language Grounding**. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2610.10178)
- <a id="p038"></a>**Confidence Calibration in Vision-Language-Action Models**. (2025, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2507.17383) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/thomaspzollo/vla_calibration)
- <a id="p039"></a>**FOREWARN**: From foresight to forethought: VLM-in-the-loop policy steering via latent alignment. (2025, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2502.01828) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/CMU-IntentLab/Forewarn) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://yilin-wu98.github.io/forewarn/)

<a id="section-1-3"></a>
### 1.3 Model Protection and Behavioral Evaluation

<a id="section-1-3-1"></a>
#### a) Input repair and representation robustness

- **LIBERO-Occ**: Evaluating and Improving Vision-Language-Action Models under Scene-Induced Occlusion via Viewpoint Imagination. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2606.10862) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/litsh/Libero-Occ)
- <a id="p042"></a>**StableVLA**: Towards Robust Vision-Language-Action Models without Extra Data. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2605.18287) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/DAGroup-PKU/HumanNet) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://dagroup-pku.github.io/StableVLA/)
- <a id="p041"></a>**SARF**: Structure-Aware Robust Fine-Tuning: Defending Vision-Language-Action Robots Against Physical Attention Hijacking. (2026, IROS) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2608.03231)
- <a id="p040"></a>**Bera**: When attention betrays: Erasing backdoor attacks in robotic policies by reconstructing visual tokens. (2026, ICRA) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2602.03153)

<a id="section-1-3-2"></a>
#### b) Robustness against computational perturbations

- <a id="p044"></a>**HoloQ-VLA**: Uniform W4A4 quantization of vision-language-action models. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2605.28803)
- <a id="p045"></a>**VLAQuantBench**: Closed-Loop Evaluation of Post-Training Quantization for Vision-Language-Action Models. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2609.25376) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/jiuyixu25/VLAQuantBench)
- <a id="p043"></a>**DieHardNet**: Improving Deep Neural Network Reliability via Transient-Fault-Aware Design and Training. (2025, IEEE TETC) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://doi.org/10.1109/TETC.2024.3520672) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/diehardnet/diehardnet)

<a id="section-1-3-3"></a>
#### c) Decision constraints and candidate verification

- <a id="p047"></a>**RoboGuard**: Safety Guardrails for LLM-Enabled Robots. (2026, IEEE RA-L) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2503.07885) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/KumarRobotics/RoboGuard) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://robo-guard.github.io/)
- <a id="p051"></a>**Gemini Robotics 1.5**: Pushing the Frontier of Generalist Robots with Advanced Embodied Reasoning, Thinking, and Motion Transfer. (2025, arXiv) [![Technical Report](https://img.shields.io/badge/Technical_Report-8C564B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2510.03342) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://deepmind.google/blog/gemini-robotics-15-brings-ai-agents-into-the-physical-world/)
- <a id="p050"></a>**RoboMonkey**: Scaling test-time sampling and verification for vision-language-action models. (2025, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2506.17811) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/robomonkey-vla/RoboMonkey) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://robomonkey-vla.github.io/)
- <a id="p046"></a>**SafeVLA**: Towards Safety Alignment of Vision-Language-Action Model via Constrained Learning. (2025, NeurIPS) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://proceedings.neurips.cc/paper_files/paper/2025/file/e185c7be603426028c32ae1003a59d78-Paper-Conference.pdf) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/PKU-Alignment/SafeVLA) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://safevla.github.io/)
- <a id="p049"></a>**KnowNo**: Robots that ask for help: Uncertainty alignment for large language model planners. (2023, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2307.01928) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/google-research/google-research/tree/master/language_model_uncertainty) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://robot-help.github.io/)
- <a id="p048"></a>**SayPlan**: Grounding Large Language Models using 3D Scene Graphs for Scalable Task Planning. (2023, CoRL) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://openreview.net/forum?id=wMpOMO0Ss7a) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://sayplan.github.io/)

<a id="runtime-systems"></a>
## ⚙️ 2. Runtime Systems

Runtime systems turn model evidence into execution decisions: which updates to admit, which computation configuration to use, when to check or regenerate, and when to release an action. This section covers communication permissions, observation freshness, computation integrity, and candidate quality, asking how inference and verification can be coordinated with ongoing motion under finite budgets and response deadlines.

<a id="section-2-4"></a>

<details>
<summary>Layer mechanism overview（Fig. 6）</summary>

![Survey layer overview](assets/figures/survey-runtime.png)

</details>

<a id="section-2-1"></a>
### 2.1 Runtime Risk Sources and Execution Effects

<a id="section-2-1-1"></a>
#### a) Malicious interference with communication

- <a id="p053"></a>**Cybersecurity Simulation Environment for Drones in Naval Applications**. (2026, Autonomous Sea Navigation) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://doi.org/10.3233/NICSP260010)
- <a id="p052"></a>**On the (In)Security of Secure ROS2**. (2022, ACM CCS) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://sites.google.com/view/secure-sros2/home) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/victomteng1997/SROS2_Broadcast_Encryption)

<a id="section-2-1-2"></a>
#### b) Environmental changes during inference and action handoff

- <a id="p055"></a>**FutureRTC**: Real-Time Robot Execution with Anticipatory-Conditioned Action Chunking. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2607.24008) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://jianghaiscu.github.io/FutureRTC_proj/)
- <a id="p056"></a>**RTC**: Real-Time Execution of Action Chunking Flow Policies. (2025, NeurIPS) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://proceedings.neurips.cc/paper_files/paper/2025/file/300ccb2187dedd4edcc07f7e76d8e553-Paper-Conference.pdf) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/Physical-Intelligence/real-time-chunking-kinetix) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://pi.website/research/real_time_chunking)
- <a id="p054"></a>**VLASH**: Real-Time VLAs via Future-State-Aware Asynchronous Inference. (2025, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2512.01031) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/mit-han-lab/vlash)

<a id="section-2-1-3"></a>
#### c) Computational deviations from approximation and faults

- **QVLA**: Not All Channels Are Equal in Vision-Language-Action Model's Quantization. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2602.03782) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/AutoLab-SAI-SJTU/QVLA)
- <a id="p057"></a>**Don't Run with Scissors: Pruning Breaks VLA Models but They Can Be Recovered**. (2025, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2510.08464) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://gluestick-vla.github.io/)
- <a id="p058"></a>**Spec-VLA**: Speculative Decoding for Vision-Language-Action Models with Relaxed Acceptance. (2025, EMNLP) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://aclanthology.org/2025.emnlp-main.1367/) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/PineTreeWss/SpecVLA)
- **SQAP-VLA**: A Synergistic Quantization-Aware Pruning Framework for High-Performance Vision-Language-Action Models. (2025, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2509.09090) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://github.com/ecdine/SQAP-VLA)

<a id="section-2-1-4"></a>
#### d) Decision anomalies at candidate release

- **RoboMonkey**: Scaling test-time sampling and verification for vision-language-action models. (2025, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2506.17811) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/robomonkey-vla/RoboMonkey) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://robomonkey-vla.github.io/)

<a id="section-2-2"></a>
### 2.2 Evidence for Runtime Risk Assessment

<a id="section-2-2-1"></a>
#### a) Communication permission and behavior checks

- <a id="p060"></a>**ROS-Defender**: SDN-Based Security Policy Enforcement for Robotic Applications. (2019, IEEE SPW) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://orbilu.uni.lu/handle/10993/39887)
- <a id="p059"></a>**ROSRV**: Runtime Verification for Robots. (2014, RV) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://doi.org/10.1007/978-3-319-11164-3_20) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/cansuerdogan/ROSRV)

<a id="section-2-2-2"></a>
#### b) Observation age and state consistency checks

- <a id="p063"></a>**ActFovea**: Runtime safeguarding for VLA policies via spatiotemporal visual-action consistency. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2607.29169) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/SunnyYWD/ActFovea)
- <a id="p062"></a>**RTI Connext QoS Reference Guide**. (2026, RTI documentation) [![Documentation](https://img.shields.io/badge/Documentation-4C78A8?style=flat-square&logo=readthedocs&logoColor=white)](https://community.rti.com/static/documentation/connext-dds/7.7.0/doc/manuals/connext_dds_professional/qos_reference/qos_reference/BasicQoS.htm)
- <a id="p061"></a>**End-to-end timing analysis in ROS2**. (2022, RTSS) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://daes.cs.tu-dortmund.de/storages/daes-cs/r/publications/teper_rtss_2022.pdf) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/HarunTeper/ros2-end-to-end)

<a id="section-2-2-3"></a>
#### c) Configuration deviation and computation integrity checks

- **QVLA**: Not All Channels Are Equal in Vision-Language-Action Model's Quantization. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2602.03782) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/AutoLab-SAI-SJTU/QVLA)
- **VLAQuantBench**: Closed-Loop Evaluation of Post-Training Quantization for Vision-Language-Action Models. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2609.25376) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/jiuyixu25/VLAQuantBench)
- <a id="p064"></a>**SAVE**: Software-Implemented Fault Tolerance for Model Inference against GPU Memory Bit Flips. (2025, USENIX ATC) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://www.usenix.org/conference/atc25/presentation/zheng) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/peterzheng98/gpu-memory)

<a id="section-2-2-4"></a>
#### d) Candidate quality and regeneration evidence

- <a id="p065"></a>**Pre-VLA**: Preemptive Runtime Verification for Reliable Vision-Language-Action and World-Model Rollouts. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2605.22446)
- **RoboMonkey**: Scaling test-time sampling and verification for vision-language-action models. (2025, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2506.17811) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/robomonkey-vla/RoboMonkey) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://robomonkey-vla.github.io/)

<a id="section-2-3"></a>
### 2.3 Runtime Protection and Execution Evaluation

<a id="section-2-3-1"></a>
#### a) Communication protection and temporal coordination

- <a id="p066"></a>**Action ControlNet**: A Lightweight Delay-Aware Adapter for Smooth Asynchronous Control in Vision-Language-Action Models. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2606.25985)
- <a id="p067"></a>**DAM-VLA**: Decoupled Asynchronous Multimodal Vision Language Action model. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2606.12105) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://intuitive-robots.github.io/DAM-VLA/)
- **FutureRTC**: Real-Time Robot Execution with Anticipatory-Conditioned Action Chunking. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2607.24008) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://jianghaiscu.github.io/FutureRTC_proj/)
- <a id="p068"></a>**Inside NVIDIA Halos for Robotics: A Full-Stack Functional Safety System for Physical AI**. (2026, NVIDIA Technical Blog) [![Blog](https://img.shields.io/badge/Blog-E69500?style=flat-square&logo=readthedocs&logoColor=white)](https://developer.nvidia.com/blog/inside-nvidia-halos-for-robotics-a-full-stack-functional-safety-system-for-physical-ai/) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/NVIDIA/halos-outside-in-safety)
- <a id="p072"></a>**Latency-Tolerant Cloud-Edge Collaborative Vision-Language-Action Models via Emergent Representational Specialization**. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2608.00569) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://daojiepeng.github.io/CloudEdgeVLA/)
- **RTC**: Real-Time Execution of Action Chunking Flow Policies. (2025, NeurIPS) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://proceedings.neurips.cc/paper_files/paper/2025/file/300ccb2187dedd4edcc07f7e76d8e553-Paper-Conference.pdf) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/Physical-Intelligence/real-time-chunking-kinetix) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://pi.website/research/real_time_chunking)
- **VLASH**: Real-Time VLAs via Future-State-Aware Asynchronous Inference. (2025, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2512.01031) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/mit-han-lab/vlash)
- **ROS-Defender**: SDN-Based Security Policy Enforcement for Robotic Applications. (2019, IEEE SPW) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://orbilu.uni.lu/handle/10993/39887)
- **ROSRV**: Runtime Verification for Robots. (2014, RV) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://doi.org/10.1007/978-3-319-11164-3_20) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/cansuerdogan/ROSRV)

<a id="section-2-3-2"></a>
#### b) Computation adaptation and fault recovery

- <a id="p070"></a>**DyQ-VLA**: Temporal-Dynamic-Aware Quantization for Embodied Vision-Language-Action Models. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2603.07904) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square)](https://anonymous.4open.science/r/DyQ-VLA-7F51/)
- <a id="p069"></a>**QuantVLA**: Scale-Calibrated Post-Training Quantization for Vision-Language-Action Models. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2602.20309) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/AIoT-MLSys-Lab/QuantVLA) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://quantvla.github.io/)
- **SAVE**: Software-Implemented Fault Tolerance for Model Inference against GPU Memory Bit Flips. (2025, USENIX ATC) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://www.usenix.org/conference/atc25/presentation/zheng) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/peterzheng98/gpu-memory)
- **SQAP-VLA**: A Synergistic Quantization-Aware Pruning Framework for High-Performance Vision-Language-Action Models. (2025, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2509.09090) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://github.com/ecdine/SQAP-VLA)

<a id="section-2-3-3"></a>
#### c) Candidate verification and supervision scheduling

- <a id="p071"></a>**FastHarness**: Experience-Driven Review Scheduling for Vision-Language-Action Policies. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2610.31427) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/FastHarness/fast-harness)
- **Pre-VLA**: Preemptive Runtime Verification for Reliable Vision-Language-Action and World-Model Rollouts. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2605.22446)
- **RoboMonkey**: Scaling test-time sampling and verification for vision-language-action models. (2025, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2506.17811) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/robomonkey-vla/RoboMonkey) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://robomonkey-vla.github.io/)
- **Spec-VLA**: Speculative Decoding for Vision-Language-Action Models with Relaxed Acceptance. (2025, EMNLP) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://aclanthology.org/2025.emnlp-main.1367/) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/PineTreeWss/SpecVLA)

<a id="computing-hardware"></a>
## 💻 3. Computing Hardware

Computing hardware determines whether inference and assurance workloads complete reliably and on time. This section covers code and model-state integrity, transient-error detection and recovery, heterogeneous deployment, state reuse, and shared-resource coordination. Comparing these studies requires considering the protected objects, device assumptions, and data-movement costs together.

<a id="section-3-4"></a>
Inference and assurance must be considered jointly in terms of device capabilities, data movement, and response time.

<details>
<summary>Layer mechanism overview（Fig. 7）</summary>

![Survey layer overview](assets/figures/survey-hardware.png)

</details>

<a id="section-3-1"></a>
### 3.1 Platform Integrity and Fault Tolerance

<a id="section-3-1-1"></a>
#### a) Integrity of executable code and model state

- <a id="p074"></a>**Bit-Flip Attacks on Vision-Language-Action Models: Action-Decoding Architecture Shapes the Vulnerability**. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2608.15475) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square)](https://arxiv.org/src/2608.15475v3/anc)
- <a id="p073"></a>**GPUHammer**: Rowhammer Attacks on GPU Memories are Practical. (2025, USENIX Security) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://www.usenix.org/conference/usenixsecurity25/presentation/lin-shaopeng) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/sith-lab/gpuhammer) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://www.gpuhammer.com/)
- <a id="p075"></a>**SAGE**: Software-based Attestation for GPU Execution. (2023, USENIX ATC) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://www.usenix.org/conference/atc23/presentation/ivanov) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/spcl/sage)
- <a id="p076"></a>**Graviton**: Trusted Execution Environments on GPUs. (2018, OSDI) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://www.usenix.org/conference/osdi18/presentation/volos)

<a id="section-3-1-2"></a>
#### b) Detection and recovery of transient errors

- <a id="p078"></a>**Flash-ABFT**: Custom Algorithm-based Fault Tolerance for Attention Layers in Transformers. (2025, IEEE SOCC) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2507.16676)
- **SAVE**: Software-Implemented Fault Tolerance for Model Inference against GPU Memory Bit Flips. (2025, USENIX ATC) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://www.usenix.org/conference/atc25/presentation/zheng) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/peterzheng98/gpu-memory)
- <a id="p077"></a>**ALBERTA**: ALgorithm-Based Error Resilience in Transformer Architectures. (2024, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2310.03841)

<a id="section-3-1-3"></a>
#### c) Device diagnostics and hardware redundancy

- **Inside NVIDIA Halos for Robotics: A Full-Stack Functional Safety System for Physical AI**. (2026, NVIDIA Technical Blog) [![Blog](https://img.shields.io/badge/Blog-E69500?style=flat-square&logo=readthedocs&logoColor=white)](https://developer.nvidia.com/blog/inside-nvidia-halos-for-robotics-a-full-stack-functional-safety-system-for-physical-ai/) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/NVIDIA/halos-outside-in-safety)
- <a id="p079"></a>**AI-Driven Industrial Automation with AMD Versal AI Edge Series Gen 2**. (2024, AMD technical brief) [![Technical Report](https://img.shields.io/badge/Technical_Report-8C564B?style=flat-square&logo=readthedocs&logoColor=white)](https://www.amd.com/content/dam/amd/en/documents/products/adaptive-socs-and-fpgas/versal/versal-ai-edge-gen2-industrial-solution-brief.pdf)

<a id="section-3-2"></a>
### 3.2 Deployment Characteristics and Resource Constraints

<a id="section-3-2-1"></a>
#### a) Workload characteristics and deployment costs

- <a id="p082"></a>**Beyond LLM Serving**: Characterizing Vision-Language-Action Workloads for Embodied AI System Design. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2610.05062)
- <a id="p080"></a>**Characterizing Vision-Language-Action Models across XPUs: Constraints and Acceleration for On-Robot Deployment**. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2604.24447) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://vla-leaderboard-01.vercel.app/)
- <a id="p083"></a>**How Fast Can I Run My VLA? Demystifying VLA Inference Performance with VLA-Perf**. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2602.18397) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/NVlabs/vla-perf)
- <a id="p081"></a>**Optimizing π0.5 Vision-Language-Action Robotic Model on Intel Core Ultra Series 3 Processor**. (2026, Intel technical article) [![Technical Report](https://img.shields.io/badge/Technical_Report-8C564B?style=flat-square&logo=readthedocs&logoColor=white)](https://docs.openedgeplatform.intel.com/2026.2/OEP-articles/publications/optimizing-pi0.5-lva-model.html)

<a id="section-3-2-2"></a>
#### b) Hardware realization of approximations

- <a id="p085"></a>**VQVLA**: A Motion-Aware Vector Quantization Framework with Centroid Reuse for Efficient VLA Inference. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2607.24148)
- **DyQ-VLA**: Temporal-Dynamic-Aware Quantization for Embodied Vision-Language-Action Models. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2603.07904) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square)](https://anonymous.4open.science/r/DyQ-VLA-7F51/)
- <a id="p084"></a>**EdgeDAE**: Acceleration of Diffusion Action Experts for Real-Time Physical AI with Tiny VLAs on Edge FPGA-GPU Systems. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2610.00311)
- <a id="p086"></a>**SteerQuant**: Steering Quantization Error with Action-Guided Scaling in World-Action Models. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2609.39056)

<a id="section-3-3"></a>
### 3.3 State Management and Coordinated Execution

<a id="section-3-3-1"></a>
#### a) Computation state maintenance and verification support

- <a id="p089"></a>**SpecVLA**: Algorithm-Architecture Co-Design for Efficient VLA Inference via Speculative Inference and Verification. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2608.15636)
- <a id="p087"></a>**FlashRT-PAI**: Fast Kernels Are Not Fast Pipelines for Physical AI Inference. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2610.24349) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/flashrt-project/FlashRT)
- <a id="p088"></a>**WAMJET**: A Harness for World Action Model Acceleration. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2610.03797) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/liulixinkerry/WAMJET) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://liulixinkerry.github.io/WAMJET/index.html)

<a id="section-3-3-2"></a>
#### b) Competition between inference and assurance

- <a id="p090"></a>**MCSched**: Memory-Controller-Aware Scheduling for Embodied LLM Workloads on NVIDIA Jetson. (2026, APSys) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://yunmingxiao.github.io/publication/26apsys-mcsched/)
- <a id="p091"></a>**DaDu-Corki**: Algorithm-Architecture Co-Design for Embodied AI-powered Robotic Manipulation. (2025, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2407.04292)

<a id="physical-execution-and-feedback"></a>
## 🦾 4. Physical Execution and Feedback

Physical execution establishes how digital commands affect the robot and its environment. Moving targets, changing contact conditions, and degraded sensing or actuation can separate intended behavior from realized outcomes. This section organizes feedback-based monitoring, action constraints, compensation, safe exit, and task recovery around the conditions each intervention preserves or restores for continued execution.

<details>
<summary>Layer mechanism overview（Fig. 8）</summary>

![Survey layer overview](assets/figures/survey-physical.png)

</details>

<a id="section-4-1"></a>
### 4.1 Physical Execution Deviations and Feedback Evidence

<a id="section-4-1-1"></a>
#### a) Attacks realized through physical interaction

- <a id="p095"></a>**BadWAM**: When World-Action Models Dream Right but Act Wrong. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2607.15207) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/LiQiiiii/BadWAM) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://liqiiiii.github.io/BadWAM/)
- <a id="p092"></a>**Tex3D**: Objects as Attack Surfaces via Adversarial 3D Textures for Vision-Language-Action Models. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2604.01618) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/vla-attack/tex3d) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://vla-attack.github.io/tex3d/)
- <a id="p094"></a>**TRAP**: Hijacking VLA CoT-reasoning via adversarial patches. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2603.23117) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/Zhengxian-Huang/TRAP) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://zhengxian-huang.github.io/TRAP-website/)
- <a id="p093"></a>**BadVLA**: Towards Backdoor Attacks on Vision-Language-Action Models via Objective-Decoupled Optimization. (2025, NeurIPS) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2505.16640) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/Zxy-MLlab/BadVLA) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://badvla-project.github.io/)
- **RoboPAIR**: Jailbreaking LLM-Controlled Robots. (2025, ICRA) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://doi.org/10.1109/ICRA55743.2025.11128119) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/arobey1/robopair) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://robopair.org/)

<a id="section-4-1-2"></a>
#### b) Changing environments and degrading bodies

- <a id="p097"></a>**DynamicVLA**: A vision-language-action model for dynamic object manipulation. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2601.22153) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/hzxie/DynamicVLA) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://www.infinitescript.com/project/dynamic-vla/)
- <a id="p100"></a>**ME-AD**: Progressive Robotics Anomaly Detection Dataset. (2026, Zenodo) [![Dataset](https://img.shields.io/badge/Dataset-9467BD?style=flat-square&logo=databricks&logoColor=white)](https://doi.org/10.5281/zenodo.20817531)
- <a id="p098"></a>**PREFAIL**: Identifying Precursors to Failures in Robotic Lift-and-Place Tasks to Improve Task Execution Performance. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2607.16921) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/zshanggu/PREFAIL) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://zshanggu.github.io/zeyu-prefail/)
- <a id="p099"></a>**Self-Adaptive VLA for Robust Robot Deployment**. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2609.30092) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://icefoxzhx.github.io/self-adaptive-vla)
- <a id="p101"></a>**TeAR**: Test-Time Adaptation of Manipulation Policies Under Actuator Degradation. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2609.36182) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/somsagar07/TeAR-Telemetry-Aware-Action-Rectification)
- <a id="p102"></a>**J-PARC**: Uncovering Vulnerability of Vision-Language-Action Models under Joint-Level Physical Faults. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2606.10501)
- <a id="p096"></a>**THE COLOSSEUM: A Benchmark for Evaluating Generalization for Robotic Manipulation**. (2024, RSS) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://doi.org/10.15607/RSS.2024.XX.133) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/robot-colosseum/robot-colosseum) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://robot-colosseum.github.io/)

<a id="section-4-1-3"></a>
#### c) Local action quality versus task progression

- <a id="p104"></a>**Don't Drop the BATON: Long-Horizon Robot Manipulation via Agentic Subtask Exploration and Transition-aware Memory**. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2608.16889)
- <a id="p106"></a>**FFDC**: When to Trust Imagination: Adaptive Action Execution for World Action Models. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2605.06222)
- <a id="p105"></a>**DoReMi**: Grounding Language Model by Detecting and Recovering from Plan-Execution Misalignment. (2024, IROS) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://doi.org/10.1109/IROS58592.2024.10802284) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://sites.google.com/view/doremi-paper)
- <a id="p103"></a>**Sentinel**: Unpacking failure modes of generative policies: Runtime monitoring of consistency and progress. (2024, CoRL) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2410.04640) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/agiachris/sentinel) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://sites.google.com/stanford.edu/sentinel)

<a id="section-4-2"></a>
### 4.2 Physical Risk Monitoring and Prediction

<a id="section-4-2-1"></a>
#### a) Cross-modal and attack-aware consistency

- <a id="p111"></a>**Active Defense Against False Data Injection Attacks in Robotic Manipulators**. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2605.17950)
- <a id="p108"></a>**Attacking the Trusted Imagination: Oracle-Level Integrity Attacks on Imagine-then-Act World Models**. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2606.22966)
- <a id="p110"></a>**CertVLA**: Certified Defense against Physical Visual Attacks for Vision-Language-Action Models. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2608.20791)
- <a id="p109"></a>**PROTEA**: Securing Robot Task Planning and Execution. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2601.07186) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/PROTEA-Secure/defense_protea) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://protea-secure.github.io/PROTEA/)
- **TMT**: Runtime Backdoor Detection for Vision-Language-Action Policies on Unseen Tasks. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2610.09462) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://zzr42.github.io/tmt/)
- <a id="p112"></a>**TrustVLA**: Mechanism-Guided Inference-Time Defense Against Vision-Language-Action Backdoors. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2607.12571)
- **Bera**: When attention betrays: Erasing backdoor attacks in robotic policies by reconstructing visual tokens. (2026, ICRA) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2602.03153)
- <a id="p107"></a>**Detecting Perception-Based Attacks using Visual Odometry: Inconsistency Modeling and Checking on Robotic States**. (2025, ICRA) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://ieeexplore.ieee.org/abstract/document/11127598)

<a id="section-4-2-2"></a>
#### b) Physical constraints and imminent hazards

- <a id="p116"></a>**PRISM**: Learning Safe-Stoppability Monitors for Humanoid Robots. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2603.22703) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://intelligent-control-lab.github.io/humanoid_stoppability/)
- **PREFAIL**: Identifying Precursors to Failures in Robotic Lift-and-Place Tasks to Improve Task Execution Performance. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2607.16921) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/zshanggu/PREFAIL) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://zshanggu.github.io/zeyu-prefail/)
- <a id="p114"></a>**RC-NF**: Robot-Conditioned Normalizing Flow for Real-Time Anomaly Detection in Robotic Manipulation. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2603.11106) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://heikaishuizz.github.io/RC-NF/)
- <a id="p113"></a>**Code-as-Monitor**: Constraint-aware Visual Programming for Reactive and Proactive Robotic Failure Detection. (2025, CVPR) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2412.04455) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://zhoues.github.io/Code-as-Monitor/)
- <a id="p115"></a>**Action Conditioned Tactile Prediction: case study on slip prediction**. (2022, RSS) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2205.09430) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/imanlab/action_conditioned_tactile_prediction)

<a id="section-4-2-3"></a>
#### c) Sensor, actuator, and feedback integrity

- **ActFovea**: Runtime safeguarding for VLA policies via spatiotemporal visual-action consistency. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2607.29169) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/SunnyYWD/ActFovea)
- **Self-Adaptive VLA for Robust Robot Deployment**. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2609.30092) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://icefoxzhx.github.io/self-adaptive-vla)
- **TeAR**: Test-Time Adaptation of Manipulation Policies Under Actuator Degradation. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2609.36182) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/somsagar07/TeAR-Telemetry-Aware-Action-Rectification)
- **J-PARC**: Uncovering Vulnerability of Vision-Language-Action Models under Joint-Level Physical Faults. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2606.10501)

<a id="section-4-2-4"></a>
#### d) Progress monitoring and failure localization

- <a id="p118"></a>**ActProbe**: Action-Space Probe for Early Failure Detection of Generative Robot Policies. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2606.08508) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/air-embodied-brain/actprobe) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://air-embodied-brain.github.io/actprobe)
- <a id="p123"></a>**FailureSpot**: Label-Efficient Timestamp-Level Failure Detection for Vision-Language-Action Models. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2609.04277)
- <a id="p122"></a>**Foresight**: Failure Detection for Long-Horizon Robotic Manipulation with Action-Conditioned World Model Latents. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2606.23085) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://haoranzhangumich.github.io/Forsight_web/)
- <a id="p120"></a>**Hide-and-Seek in Trajectories: Discovering Failure Signals for VLA Runtime Monitoring**. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2605.30834) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://seongheon-96.github.io/hide_and_seek_site/)
- <a id="p117"></a>**VLAC**: A vision-language-action-critic model for robotic real-world reinforcement learning. (2025, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2509.15937) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/Sage-PhysicalAI/VLAC) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://vlac.intern-ai.org.cn/)
- <a id="p121"></a>**FAIL-Detect**: Can we detect failures without failure data? uncertainty-aware runtime failure detection for imitation learning policies. (2025, RSS) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2503.08558) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/CXU-TRI/FAIL-Detect) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://cxu-tri.github.io/FAIL-Detect-Website/)
- <a id="p119"></a>**SAFE**: Multitask Failure Detection for Vision-Language-Action Models. (2025, NeurIPS) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2506.09937) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/vla-safe/SAFE) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://vla-safe.github.io/)
- <a id="p124"></a>**AHA**: A vision-language-model for detecting and reasoning over failures in robotic manipulation. (2024, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2410.00371) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/NVlabs/AHA) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://aha-vlm.github.io/)
- **Sentinel**: Unpacking failure modes of generative policies: Runtime monitoring of consistency and progress. (2024, CoRL) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2410.04640) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/agiachris/sentinel) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://sites.google.com/stanford.edu/sentinel)

<a id="section-4-3"></a>
### 4.3 Execution Intervention and Safe Recovery

<a id="section-4-3-1"></a>
#### a) From malicious evidence to bounded action protection

- **Active Defense Against False Data Injection Attacks in Robotic Manipulators**. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2605.17950)
- **CertVLA**: Certified Defense against Physical Visual Attacks for Vision-Language-Action Models. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2608.20791)
- <a id="p125"></a>**JailWAM**: Jailbreaking World Action Models in Robot Control. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2604.05498) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://jailwam.github.io/)
- **RoboGuard**: Safety Guardrails for LLM-Enabled Robots. (2026, IEEE RA-L) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2503.07885) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/KumarRobotics/RoboGuard) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://robo-guard.github.io/)
- **TrustVLA**: Mechanism-Guided Inference-Time Defense Against Vision-Language-Action Backdoors. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2607.12571)
- **Bera**: When attention betrays: Erasing backdoor attacks in robotic policies by reconstructing visual tokens. (2026, ICRA) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2602.03153)

<a id="section-4-3-2"></a>
#### b) Safety constraints and context-dependent intervention

- <a id="p129"></a>**CompliantVLA-adaptor**: VLM-guided variable impedance action for safe contact-rich manipulation. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2601.15541) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://sites.google.com/view/compliantvla)
- **PRISM**: Learning Safe-Stoppability Monitors for Humanoid Robots. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2603.22703) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://intelligent-control-lab.github.io/humanoid_stoppability/)
- **PREFAIL**: Identifying Precursors to Failures in Robotic Lift-and-Place Tasks to Improve Task Execution Performance. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2607.16921) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/zshanggu/PREFAIL) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://zshanggu.github.io/zeyu-prefail/)
- <a id="p128"></a>**STeP**: Signal Temporal Logic for Precise Specifications for Action Generation with Vision Language Models. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2607.18580)
- <a id="p127"></a>**VLSA / AEGIS**: Vlsa: Vision-language-action models with plug-and-play safety constraint layer. (2026, IROS) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2512.11891) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/THU-RCSCT/vlsa-aegis) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://vlsa-aegis.github.io/)
- <a id="p130"></a>**VLA-Arena**: An open-source framework for benchmarking vision-language-action models. (2025, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2512.22539) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/PKU-Alignment/VLA-Arena) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://vla-arena.github.io/)
- <a id="p126"></a>**Control Barrier Function Based Quadratic Programs for Safety Critical Systems**. (2017, IEEE TAC) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/1609.06408)

<a id="section-4-3-3"></a>
#### c) Compensation under altered physical capability

- **ActFovea**: Runtime safeguarding for VLA policies via spatiotemporal visual-action consistency. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2607.29169) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/SunnyYWD/ActFovea)
- <a id="p131"></a>**Failing Gracefully: Mitigating Impact of Inevitable Robot Failures**. (2026, ICRA) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2608.05313) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/ducmngx/FailBench)
- **Self-Adaptive VLA for Robust Robot Deployment**. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2609.30092) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://icefoxzhx.github.io/self-adaptive-vla)
- **TeAR**: Test-Time Adaptation of Manipulation Policies Under Actuator Degradation. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2609.36182) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/somsagar07/TeAR-Telemetry-Aware-Action-Rectification)
- **J-PARC**: Uncovering Vulnerability of Vision-Language-Action Models under Joint-Level Physical Faults. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2606.10501)

<a id="section-4-4"></a>
### 4.4 Recovery Outcomes and Feedback Limitations

Recovery evaluation asks which robot, object, or task conditions were restored and whether useful execution resumed. Physical feedback alone does not identify a unique cause; changing upstream precision, checking frequency, or placement also requires aligned action, timestamp, and execution records.

<a id="section-4-4-1"></a>
#### a) Recovering local execution and task state

- <a id="p135"></a>**CycleVLA**: Proactive self-correcting vision-language-action models via subtask backtracking and minimum bayes risk decoding. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2601.02295) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/dannymcy/cyclevla_code) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://dannymcy.github.io/cyclevla/)
- <a id="p134"></a>**FLARE**: A Failure-Aware Framework for Autonomous Correction and Recovery in Visual-Language Robotic Manipulation. (2026, CVPR) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2608.26645)
- **FFDC**: When to Trust Imagination: Adaptive Action Execution for World Action Models. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2605.06222)
- <a id="p133"></a>**FailSafe**: Reasoning and recovery from failures in vision-language-action models. (2025, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2510.01642) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://jimntu.github.io/FailSafe)
- <a id="p132"></a>**RACER**: Rich Language-Guided Failure Recovery Policies for Imitation Learning. (2025, ICRA) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2409.14674) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/sled-group/RACER) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://rich-language-failure-recovery.github.io/)
- <a id="p136"></a>**DROC**: Distilling and Retrieving Generalizable Knowledge for Robot Manipulation via Language Corrections. (2024, ICRA) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2311.10678) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/Stanford-ILIAD/droc) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://sites.google.com/stanford.edu/droc)
- **DoReMi**: Grounding Language Model by Detecting and Recovering from Plan-Execution Misalignment. (2024, IROS) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://doi.org/10.1109/IROS58592.2024.10802284) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://sites.google.com/view/doremi-paper)

<a id="section-4-4-2"></a>
#### b) Assessing recovery rather than just detection

- <a id="p138"></a>**VLA-FixBench**: Can VLMs Diagnose and Recover from VLA Manipulation Faults? (2026, ICML) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://proceedings.mlr.press/v306/yan26r.html) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://kakigo.github.io/VLA-FixBench/)
- **FailureSpot**: Label-Efficient Timestamp-Level Failure Detection for Vision-Language-Action Models. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2609.04277)
- <a id="p137"></a>**REBOOT**: From Failure to Recovery-A Dataset and Benchmark for Precision Assembly. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2609.22591) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/anon-robo-account/REBOOT) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://nanayawoa.github.io/REBOOT/)
- **AHA**: A vision-language-model for detecting and reasoning over failures in robotic manipulation. (2024, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2410.00371) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/NVlabs/AHA) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://aha-vlm.github.io/)

<a id="evaluation-and-benchmarks"></a>
## 📊 5. Evaluation and Benchmarks

This evaluation resource index draws on Section IX, Table IX, and related survey discussions. Benchmarks and datasets are grouped by evaluation focus; work that only reports performance, timing, or deployment experiments is listed separately as evaluation studies.

<a id="section-5-1"></a>
### 5.1 Benchmarks and Datasets

<a id="section-5-1-1"></a>
#### Environmental and Perceptual Robustness

| Benchmark / Dataset | Evaluation Focus | Paper | Code / Dataset | Project |
| --- | --- | --- | --- | --- |
| **LIBERO-Occ** | Scene-induced occlusion and effects on action generation | [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2606.10862) | [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/litsh/Libero-Occ) | — |
| **LIBERO-Plus** | Task robustness under scene, viewpoint, and initial-state changes | [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2510.13626) | [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/sylvestf/LIBERO-plus) | [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://sylvestf.github.io/LIBERO-plus/) |
| **COLOSSEUM** | Manipulation generalization under environmental variation | [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://doi.org/10.15607/RSS.2024.XX.133) | [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/robot-colosseum/robot-colosseum) | [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://robot-colosseum.github.io/) |

<a id="section-5-1-2"></a>
#### Instruction Grounding and Task Planning

| Benchmark / Dataset | Evaluation Focus | Paper | Code / Dataset | Project |
| --- | --- | --- | --- | --- |
| **LIBERO-CF** | Language following under counterfactual instructions | [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2602.17659) | [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/yuffish/VLA-CF) | [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://vla-cf.github.io/) |
| **EmbodiedBench** | State understanding, planning, and action feasibility | [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://proceedings.mlr.press/v267/yang25f.html) | [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/EmbodiedBench/EmbodiedBench) | [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://embodiedbench.github.io/) |

<a id="section-5-1-3"></a>
#### Safety and Constraint Satisfaction

| Benchmark / Dataset | Evaluation Focus | Paper | Code / Dataset | Project |
| --- | --- | --- | --- | --- |
| **SafePlan-Bench** | Process and terminal-state safety constraints | [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2504.14650) | — | — |
| **VLA-Arena** | Closed-loop task performance and safety costs | [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2512.22539) | [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/PKU-Alignment/VLA-Arena) | [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://vla-arena.github.io/) |

<a id="section-5-1-4"></a>
#### Numerical Fidelity and Efficiency

| Benchmark / Dataset | Evaluation Focus | Paper | Code / Dataset | Project |
| --- | --- | --- | --- | --- |
| **VLAQuantBench** | Fixed-input deviations, closed-loop outcomes, and execution costs | [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2609.25376) | [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/jiuyixu25/VLAQuantBench) | — |

<a id="section-5-1-5"></a>
#### Physical Faults and Failure Severity

| Benchmark / Dataset | Evaluation Focus | Paper | Code / Dataset | Project |
| --- | --- | --- | --- | --- |
| **FailBench** | Fault consequences, collisions, and failure severity | [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2608.05313) | [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/ducmngx/FailBench) | — |
| **ME-AD** | Progressive industrial-manipulator wear observations | — | [![Dataset](https://img.shields.io/badge/Dataset-9467BD?style=flat-square&logo=databricks&logoColor=white)](https://doi.org/10.5281/zenodo.20817531) | — |

<a id="section-5-3"></a>
<a id="section-5-1-6"></a>
#### Failure Diagnosis and Recovery

| Benchmark / Dataset | Evaluation Focus | Paper | Code / Dataset | Project |
| --- | --- | --- | --- | --- |
| **VLA-FixBench** | Manipulation-fault diagnosis and closed-loop recovery | [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://proceedings.mlr.press/v306/yan26r.html) | — | [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://kakigo.github.io/VLA-FixBench/) |
| **REBOOT** | Precision-assembly failures and expert recovery trajectories | [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2609.22591) | [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/anon-robo-account/REBOOT) | [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://nanayawoa.github.io/REBOOT/) |

<a id="section-5-2"></a>
### 5.2 Evaluation Studies

<a id="section-5-2-1"></a>
#### Hardware and Deployment Performance

- **Characterizing Vision-Language-Action Models across XPUs: Constraints and Acceleration for On-Robot Deployment**. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2604.24447) [![Project](https://img.shields.io/badge/Project-007EC6?style=flat-square&logo=safari&logoColor=white)](https://vla-leaderboard-01.vercel.app/)
- **How Fast Can I Run My VLA? Demystifying VLA Inference Performance with VLA-Perf**. (2026, arXiv) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://arxiv.org/abs/2602.18397) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/NVlabs/vla-perf)

<a id="section-5-2-2"></a>
#### Runtime Timing and Resource Evaluation

- **End-to-end timing analysis in ROS2**. (2022, RTSS) [![Paper](https://img.shields.io/badge/Paper-B31B1B?style=flat-square&logo=readthedocs&logoColor=white)](https://daes.cs.tu-dortmund.de/storages/daes-cs/r/publications/teper_rtss_2022.pdf) [![Code](https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/HarunTeper/ros2-end-to-end)

<a id="contributing-and-citation"></a>
<a id="contributing"></a>
## 🤝 Contributing

Issues and pull requests are welcome for official resources, metadata corrections, and classification improvements. See [CONTRIBUTING.md](CONTRIBUTING.md) for the format, IDs, and counting rules.

<a id="citation"></a>
## 📝 Citation

### GitHub Repository Citation

```bibtex
@misc{zheng2026awesomeembodiedtrustworthyexecution,
  title        = {Awesome Embodied Trustworthy Execution},
  author       = {Zheng, Zihao and Cao, Hangyu and Mao, Zhihao},
  year         = {2026},
  howpublished = {\url{https://github.com/zhengzihaoPKU/Awesome-Embodied-Trustworthy-Execution}}
}
```


<a id="acknowledgements"></a>
## 🙏 Acknowledgements & Contributors

Thanks to the paper authors and open-source contributors. 

Figures reproduce Figs. 1–8 of the companion survey.

Paper titles, figures, and technical ideas belong to their respective authors and publishers. Figures in this repository are cropped representative excerpts used for scholarly review and navigation. Follow the original paper's license when reusing them. Authors may open an issue to request replacement or removal of a figure.


[![Contributors](https://contrib.rocks/image?repo=zhengzihaoPKU/Awesome-Embodied-Trustworthy-Execution)](https://github.com/zhengzihaoPKU/Awesome-Embodied-Trustworthy-Execution/graphs/contributors)

<a id="star-history"></a>
## ⭐ Star History

[![Star History Chart](https://api.star-history.com/svg?repos=zhengzihaoPKU/Awesome-Embodied-Trustworthy-Execution&type=Date)](https://www.star-history.com/#zhengzihaoPKU/Awesome-Embodied-Trustworthy-Execution&Date)
