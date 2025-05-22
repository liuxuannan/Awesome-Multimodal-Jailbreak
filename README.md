
# 😈🛡️Awesome-Jailbreak-against-Multimodal-Generative-Models
🔥🔥🔥 **Jailbreak Attacks and Defenses against Multimodal Generative Models: A Survey**

**[Paper](https://arxiv.org/abs/2411.09259)**  

We've curated a collection of the latest 😋, most comprehensive 😎, and most valuable 🤩 resources on Jailbreak Attack and Defense against Multimodel Generative Models.<br> 
But we don't stop there; Our repository is constantly updated to ensure you have the most current information at your fingertips.

![survey model](https://github.com/liuxuannan/Awesome-Multimodal-Jailbreak/blob/main/pic/page_1_00.png)

## 🤗Introduction

**This survey presents a comprehensive review of existing jailbreak attack and defense against multimodal generative models.**<br>
**Given the generalized lifecycle of multimodal jailbreak, we systematically explore attacks and corresponding defense strategies across four levels: input, encoder, generator, and output.**<br>

**🧑‍💻 Four Levels of Multimodal Jailbreak lifecycle**
- Input Level: Attackers and defenders operate solely on the input data. Attackers modify inputs to execute attacks, while defenders incorporate protective cues to enhance detection.<br>
- Encoder Level: With access to the encoder, attackers optimize adversarial inputs to inject malicious information into the encoding process, while defenders work to prevent harmful information from being encoded within the latent space.<br>
- Generator Level: : With full access to the generative models, attackers leverage inference information, such as activations and gradients, and fine-tune models to increase adversarial effectiveness, while defenders use these techniques to strengthen model robustness.<br>
- Output Level: With the output from the generative model, attackers can iteratively refine adversarial inputs, while defenders can apply post-processing techniques to enhance detection.<br>

**Based on this analysis, we present a detailed taxonomy of attack methods, defense mechanisms, and evaluation frameworks specific to multimodal generative models.**<br>
**We cover a wide range of input-output configurations, including modalities such as Any-to-Text, Any-to-Vision, and Any-to-Any within generative systems.**<br>

![survey model](https://github.com/liuxuannan/Awesome-Multimodal-Jailbreak/blob/main/pic/survey_model.png)

## 🚀Table of Contents

- [😈🛡️Awesome-Jailbreak-against-Multimodal-Generative-Models🛡️](#️Awesome-Jailbreak-against-Multimodal-Generative-Models)
  - [🤗Introduction](#introduction)
  - [🚀Table of Contents](#table-of-contents)
  - [🔥Multimodal Generative Models](#Multimodal-Generative-Models)
    - [📑Any-to-Text Models (LLM Backbone)](#Any-to-Text-LLM-Backbone)
    - [📖Any-to-Vision Models (Diffusion Backbone)](#Any-to-Vision-Diffusion-Backbone)
    - [📰Any-to-Any Models (Unified Backbone)](#Any-to-Any-Unified-Backbone)
  - [😈Jailbreak Attack](#Jailbreak-Attack)
    - [📖Attack-Intro](#Attack-Intro)
    - [📑Papers](#Papers)
  - [🛡️Jailbreak Defense](#️jailbreak-defense)
    - [📖Defense-Intro](#Defense-Intro)
    - [📑Papers](#Papers)
  - [💯Evaluation](#Evaluation)
    - [⭐️Datasets](#datasets)
      - [Used to Any-to-Text Models](#Used-to-Any-to-Text-Models)
      - [Used to Any-to-Vision Models](#Used-to-Any-to-Vision-Models)
    - [📚Detectors](#detectors)
      - [Used to Any-to-Text Models](#Used-to-Any-to-Text-Models)
      - [Used to Any-to-Text Models](#Used-to-Any-to-Vision-Models)
  - [😉Citation](#Citation)



## 🔥Multimodal Generative Models

**Below are tables of model short name and representative generative models used for jailbreak. For input/output modalities, I: Image, T: Text, V: Video, A: Audio.**

### 📑Any-to-Text Models (LLM Backbone)
|  Short Name  |   Modality  |   Representative Model   |  
|:--------|:--------:|:--------:|
| I+T→T | I + T → T |[LLaVA](https://arxiv.org/abs/2304.08485), [MiniGPT4](https://arxiv.org/abs/2304.10592), [InstructBLIP](https://arxiv.org/abs/2305.06500) |
| VT2T | V + T → T |[Video-LLaVA](https://arxiv.org/abs/2311.10122), [Video-LLaMA](https://arxiv.org/abs/2306.02858) |
| AT2T | A + T → T |[Audio Flamingo](https://arxiv.org/abs/2402.01831), [Audiopalm](https://arxiv.org/abs/2306.12925) |

### 📖Any-to-Vision (Diffusion Backbone)
|  Short Name  |   Modality  |   Representative Model   |  
|:--------|:--------:|:--------:|
| T→I | T → I |[Stable Diffusion](https://arxiv.org/abs/2112.10752), [Midjourney](https://www.midjourney.com/), [DALLE](https://platform.openai.com/docs/guides/moderation/overview) |
| IT→I | I + T → I |[DreamBooth](https://arxiv.org/abs/2208.12242), [InstructP2P](https://arxiv.org/abs/2306.07154) |
| T2V | T → V |[Open-Sora](https://github.com/hpcaitech/Open-Sora), [Stable Video Diffusion](https://arxiv.org/abs/2311.15127) |
| IT2V | I + T → V |[VideoPoet](https://arxiv.org/abs/2312.14125), [CogVideoX](https://arxiv.org/abs/2408.06072) |

### 📰Any-to-Any (Unified Backbone)
|  Short Name  |   Modality  |   Representative Model   |  
|:--------|:--------:|:--------:|
| IT→IT | I + T → I + T |[Next-GPT](https://arxiv.org/abs/2309.05519), [Chameleon](https://arxiv.org/abs/2304.09842) |
| TIV2TIV | T + I + V → T + I + V |[EMU3](https://arxiv.org/abs/2409.18869)|
| Any2Any | Any → Any |[GPT-4o](https://openai.com/index/gpt-4o-system-card/), [Gemini Ultra](https://arxiv.org/abs/2312.11805)|


## 😈JailBreak Attack

### 📖Attack-Intro

**We categorize attack methods into black-box, gray-box, and white-box attacks. in a black-box setting where the model is inaccessible to the attacker, the attack is limited to surface-level interactions, focusing solely on the model’s input and/or output. Regarding gray-box and white-box attacks, we consider model-level attacks, including attacks at both the encoder and generator.**

- Input-level attack: attackers are compelled to develop more sophisticated input templates across prompt engineering, image engineering, and role-ploy techniques.
- Output-level attack: Attackers focus on querying outputs across multiple input variants. Driven by specific adversarial goals, attackers employ estimation-based and search-based attack techniques to iteratively refine these input variants.

<img src="https://github.com/liuxuannan/Awesome-Multimodal-Jailbreak/blob/main/pic/jailbreak_attack_A.png" alt="jailbreak_attack_black_box" />

- Encoder-level attack: Attackers are restricted to accessing only the encoders to provoke harmful responses. In this case, attackers typically seek to maximize cosine similarity within the latent space, ensuring the adversarial input retains similar semantics to the target malicious content while still being classified as safe.
- Generator-level attack: Attackers have unrestricted access to the generative model’s architecture and checkpoint, enabling attackers to conduct thorough investigations and manipulations, thus enabling sophisticated attacks.

<img src="https://github.com/liuxuannan/Awesome-Multimodal-Jailbreak/blob/main/pic/jailbreak_attack_B.png" alt="jailbreak_attack_white_and_gray_box" />

### 📑Papers
Below are the papers related to jailbreak attacks.
## Jailbreak Attack of Any-to-Text Models
|  Title  |   Venue  |   Date   |   Code   | Taxonomy |  Multimodal Model|
|:--------|:--------:|:--------:|:--------:|:--------:|:--------:|
|[**Video-SafetyBench: A Benchmark for Safety Evaluation of Video LVLMs**](https://arxiv.org/abs/2505.11842) | Arxiv 2025 | 2025/05/17 | [Homepage](https://liuxuannan.github.io/Video-SafetyBench.github.io/) | Input Level | V+T→T |
|[**Think in Safety: Unveiling and Mitigating Safety Alignment Collapse in Multimodal Large Reasoning Model**](https://arxiv.org/abs/2505.06538) | Arxiv 2025 | 2025/05/10 | [Github](https://github.com/xinyuelou/Think-in-Safety) | --- | I+T→T |
|[**SafeMLRM: Demystifying Safety in Multi-modal Large Reasoning Models**](https://arxiv.org/abs/2504.08813) | Arxiv 2025 | 2025/04/09 | [Github](https://github.com/fangjf1/OpenSafeMLRM) | --- | I+T→T |
|[**PiCo: Jailbreaking Multimodal Large Language Models via Pictorial Code Contextualization**](https://arxiv.org/abs/2504.01444) | Arxiv 2025 | 2025/04/02 | None | --- | I+T→T |
|[**Multilingual and Multi-Accent Jailbreaking of Audio LLMs**](https://arxiv.org/abs/2504.01094) | Arxiv 2025 | 2025/04/01 | None | --- | A+T→T |
|[**Playing the Fool: Jailbreaking LLMs and Multimodal LLMs with Out-of-Distribution Strategy**](https://arxiv.org/abs/2503.20823) | CVPR 2025 | 2025/03/26 | [Github](https://github.com/naver-ai/JOOD) | --- | I+T→T |
|[**MIRAGE: Multimodal Immersive Reasoning and Guided Exploration for Red-Team Jailbreak Attacks**](https://arxiv.org/abs/2503.19134) | Arxiv 2025 | 2025/03/24 | None | --- | I+T→T |
|[**Making Every Step Effective: Jailbreaking Large Vision-Language Models Through Hierarchical KV Equalization**](https://arxiv.org/abs/2503.11750) | Arxiv 2025 | 2025/03/14 | None | --- | I+T→T |
|[**ExtremeAIGC: Benchmarking LMM Vulnerability to AI-Generated Extremist Content**](https://arxiv.org/abs/2503.09964) | Arxiv 2025 | 2025/03/13 | None | --- | I+T→T |
|[**Utilizing Jailbreak Probability to Attack and Safeguard Multimodal LLMs**](https://arxiv.org/abs/2503.06989) | Arxiv 2025 | 2025/03/10 | None | --- | I+T→T |
|[**FC-Attack: Jailbreaking Large Vision-Language Models via Auto-Generated Flowcharts**](https://arxiv.org/abs/2502.21059) | Arxiv 2025 | 2025/02/28 | None | --- | I+T→T |
|[**EigenShield: Causal Subspace Filtering via Random Matrix Theory for Adversarially Robust Vision-Language Models**](https://arxiv.org/abs/2502.14976) | Arxiv 2025 | 2025/02/20 | None | --- | I+T→T |
|[**Can't See the Forest for the Trees: Benchmarking Multimodal Safety Awareness for Multimodal LLMs**](https://arxiv.org/abs/2502.11184) | Arxiv 2025 | 2025/02/16 | None | --- | I+T→T |
|[**Distraction is All You Need for Multimodal Large Language Model Jailbreaking**](https://arxiv.org/abs/2502.10794) | CVPR 2025 | 2025/02/15 | None | --- | I+T→T |
|[**ELITE: Enhanced Language-Image Toxicity Evaluation for Safety**](https://arxiv.org/abs/2502.04757) | Arxiv 2025 | 2025/02/07 | None | --- | I+T→T |
|[**`Do as I say not as I do': A Semi-Automated Approach for Jailbreak Prompt Attack against Multimodal LLMs**](https://arxiv.org/abs/2502.00735) | Arxiv 2025 | 2025/02/02 | None | --- | A+T→T |
|[**"I am bad": Interpreting Stealthy, Universal and Robust Audio Jailbreaks in Audio-Language Models**](https://arxiv.org/abs/2502.00718) | Arxiv 2025 | 2025/02/02 | [Github](https://isha-gpt.github.io/) | --- | A+T→T |
|[**Tune In, Act Up: Exploring the Impact of Audio Modality-Specific Edits on Large Audio Language Models in Jailbreak**](https://arxiv.org/abs/2501.13772) | Arxiv 2025 | 2025/01/23 | None | --- | A+T→T |
|[**Failures to Find Transferable Image Jailbreaks Between Vision-Language Models**](https://openreview.net/forum?id=wvFnqVVUhN) | ICLR 2025 | 2025/01/23 | [Github](https://github.com/RylanSchaeffer/AstraFellowship-When-Do-VLM-Image-Jailbreaks-Transfer) | Generator Level | I+T→T |
|[**Jailbreaking Multimodal Large Language Models via Shuffle Inconsistency**](https://arxiv.org/abs/2501.04931) | Arxiv 2025 | 2025/01/09 | None | --- | I+T→T |
|[**Divide and Conquer: A Hybrid Strategy Defeats Multimodal Large Language Models**](https://arxiv.org/abs/2412.16555) | Arxiv 2024 | 2024/12/21 | None | --- | I+T+A→T |
|[**AdvWave: Stealthy Adversarial Jailbreak Attack against Large Audio-Language Models**](https://arxiv.org/abs/2412.08608) | ICLR 2025 | 2024/12/11 | [Github](https://github.com/kangmintong/AdvWave) | Generator Level | A+T→T |
|[**Heuristic-Induced Multimodal Risk Distribution Jailbreak Attack for Multimodal Large Language Models**](https://arxiv.org/abs/2412.05934) | Arxiv 2024 | 2024/12/8 | [Github](https://github.com/MaTengSYSU/HIMRD-jailbreak) | --- | I+T→T |
|[**PBI-Attack: Prior-Guided Bimodal Interactive Black-Box Jailbreak Attack for Toxicity Maximization**](https://arxiv.org/abs/2412.05892) | Arxiv 2024 | 2024/12/8 | None | --- | I+T→T |
|[**Jailbreak Large Vision-Language Models Through Multi-Modal Linkage**](https://arxiv.org/abs/2412.00473) | Arxiv 2024 | 2024/11/30 | [Github](https://github.com/wangyu-ovo/MML) | --- | I+T→T |
|[**Exploring Visual Vulnerabilities via Multi-Loss Adversarial Search for Jailbreaking Vision-Language Models**](https://arxiv.org/abs/2411.18000) | CVPR 2025 | 2024/11/27 | None | --- | I+T→T |
|[**The VLLM Safety Paradox: Dual Ease in Jailbreak Attack and Defense**](https://arxiv.org/abs/2411.08410) | Arxiv 2024 | 2024/11/13 | None | --- | I+T→T |
|[**MMJ-Bench : A Comprehensive Study on Jailbreak Attacks and Defenses for Multimodal Large Language Models**](https://arxiv.org/abs/2408.08464) | Arxiv 2024 | 2024/08/16 | None | --- | I+T→T |
|[**Failures to Find Transferable Image Jailbreaks Between Vision-Language Models**](https://arxiv.org/abs/2407.15211) | NeurIPS 2024 Workshops | 2024/07/21 | None | --- | I+T→T |
|[**MLLMGuard: A Multi-dimensional Safety Evaluation Suite for Multimodal Large Language Models**](https://arxiv.org/abs/2406.07594) | NeurIPS 2024 | 2024/06/11 | [Github](https://github.com/Carol-gutianle/MLLMGuard) | --- | I+T→T |
|[**Unveiling the Safety of GPT-4o: An Empirical Study using Jailbreak Attacks**](https://arxiv.org/abs/2406.06302) | Arxiv 2024 | 2024/06/10 | [Github](https://github.com/NY1024/Jailbreak_GPT4o) | --- | I+T→T |
|[**Red Teaming GPT-4V: Are GPT-4V Safe Against Uni/Multi-Modal Jailbreak Attacks?**](https://arxiv.org/abs/2404.03411) | Arxiv 2024 | 2024/04/04 | [Github](https://github.com/chenxshuo/RedTeamingGPT4V) | --- | I+T→T |
|[**VLSBench: Unveiling Visual Leakage in Multimodal Safety**](https://arxiv.org/abs/2411.19939) | ACL 2025 | 2024/11/29 | [Homepage](https://hxhcreate.github.io/vlsbench.github.io/) | Input Level | I+T→T |
|[**Safe + Safe = Unsafe? Exploring How Safe Images Can Be Exploited to Jailbreak Large Vision-Language Models**](https://arxiv.org/abs/2411.11496) | Arxiv 2024 | 2024/11/18 | [Github](https://github.com/gzcch/Safety_Snowball_Agent) | Output Level | I+T→T |
|[**IDEATOR: Jailbreaking Large Vision-Language Models Using Themselves**](https://arxiv.org/abs/2411.00827) | Arxiv 2024 | 2024/11/15 | [Github](https://github.com/roywang021/IDEATOR) | Output Level | I+T→T |
|[**Zer0-Jack: A memory-efficient gradient-based jailbreaking method for black box Multi-modal Large Language Models**](https://arxiv.org/abs/2411.07559) | NeurIPS SafeGenAi Workshop 2024 | 2024/11/12 | None | Output Level | I+T→T |
|[**Audio is the achilles’heel: Red teaming audio large multimodal models**](https://arxiv.org/abs/2410.23861) | Arxiv 2024 | 2024/10/31 | [Github](https://github.com/YangHao97/RedteamAudioLMMs) | Input Level | A+T→T |
|[**Advweb: Controllable black-box attacks on vlm-powered web agents**](https://arxiv.org/abs/2410.17401) | Arxiv 2024 | 2024/10/22 | None | Input Level | I+T→T |
|[**Can Large Language Models Automatically Jailbreak GPT-4V?**](https://arxiv.org/abs/2407.16686) | NAACL Workshop 2024 | 2024/07/23 | None | Input Level | I+T→T |
|[**Arondight: Red Teaming Large Vision Language Models with Auto-generated Multi-modal Jailbreak Prompts**](https://arxiv.org/abs/2407.15050) | ACM MM 2024 | 2024/07/21 | None | Input Level | I+T→T |
|[**Image-to-Text Logic Jailbreak: Your Imagination can Help You Do Anything**](https://arxiv.org/abs/2407.02534) | Arxiv 2024 | 2024/07/01 | None | Input Level | I+T→T |
|[**From LLMs to MLLMs: Exploring the Landscape of Multimodal Jailbreaking**](https://arxiv.org/abs/2406.14859) | EMNLP 2024 | 2024/06/21 | None | Encoder Level | I+T→T |
|[**Jailbreak Vision Language Models via Bi-Modal Adversarial Prompt**](https://arxiv.org/abs/2406.04031) | Arxiv 2024 | 2024/06/06 | [Github](https://github.com/NY1024/BAP-Jailbreak-Vision-Language-Models-via-Bi-Modal-Adversarial-Prompt) | Generator Level | I+T→T |
|[**Efficient LLM-Jailbreaking by Introducing Visual Modality**](https://arxiv.org/abs/2405.20015) | Arxiv 2024 | 2024/05/30 | [Github](https://github.com/nobody235/LLM-jailbreak) | Generator Level | I+T→T |
|[**White-box Multimodal Jailbreaks Against Large Vision-Language Models**](https://arxiv.org/abs/2405.17894) | ACM MM 2024 | 2024/05/28 | [Github](https://github.com/roywang021/UMK) | Generator Level | I+T→T |
|[**Medical MLLM is Vulnerable: Cross-Modality Jailbreak and Mismatched Attacks on Medical Multimodal Large Language Models**](https://arxiv.org/abs/2405.20775) | Arxiv 2024 | 2024/05/26 | [Github](https://github.com/dirtycomputer/O2M_attack) | --- | I+T→T |
|[**Visual-RolePlay: Universal Jailbreak Attack on MultiModal Large Language Models via Role-playing Image Character**](https://arxiv.org/abs/2405.20773) | Arxiv 2024 | 2024/05/25 | [Github](https://github.com/SiyuanMaCS/VisualRoleplay) | Input Level | I+T→T |
|[**Images are Achilles' Heel of Alignment: Exploiting Visual Vulnerabilities for Jailbreaking Multimodal Large Language Models**](https://arxiv.org/abs/2403.09792) | ECCV 2024 | 2024/05/14 | [Github](https://github.com/RUCAIBox/HADES)| Generator Level | I+T→T |
|[**Agent Smith: A Single Image Can Jailbreak One Million Multimodal LLM Agents Exponentially Fast**](https://arxiv.org/abs/2402.08567) | ICML 2024 | 2024/02/13 | [Github](https://github.com/sail-sg/Agent-Smith) | Generator Level | I+T→T |
|[**Jailbreaking Attack against Multimodal Large Language Model**](https://arxiv.org/abs/2402.02309) | Arxiv 2024 | 2024/02/04 | None| Generator Level | I+T→T |
|[**Jailbreak in pieces: Compositional Adversarial Attacks on Multi-Modal Language Models**](https://arxiv.org/abs/2307.14539) | ICLR 2024 Spotlight | 2024/01/16 | [Github](https://github.com/erfanshayegani/Jailbreak-In-Pieces) | Encoder Level | I+T→T |
|[**MM-SafetyBench: A Benchmark for Safety Evaluation of Multimodal Large Language Models**](https://arxiv.org/abs/2311.17600) | ECCV 2024 | 2023/11/29 | [Github](https://github.com/isXinLiu/MM-SafetyBench) | Input Level | I+T→T |
|[**How Many Unicorns Are in This Image? A Safety Evaluation Benchmark for Vision LLMs**](https://arxiv.org/abs/2311.16101) | ECCV 2024 | 2023/11/27 | [Github](https://github.com/UCSC-VLAA/vllm-safety-benchmark) | Encoder Level | I+T→T |
|[**Jailbreaking GPT-4V via Self-Adversarial Attacks with System Prompts**](https://arxiv.org/abs/2311.09127) | Arxiv 2023 | 2023/11/15 | None | Output Level | I+T→T |
|[**FigStep: Jailbreaking Large Vision-language Models via Typographic Visual Prompts**](https://arxiv.org/abs/2311.05608) | AAAI 2025 | 2023/11/09 | [Github](https://github.com/ThuCCSLab/FigStep) | Input Level | I+T→T |
|[**Image Hijacks: Adversarial Images can Control Generative Models at Runtime**](https://arxiv.org/abs/2309.00236) | ICML 2024 | 2023/09/01 | [Github](https://github.com/euanong/image-hijacks) | Generator Level | I+T→T |
|[**Are aligned neural networks adversarially aligned?**](https://arxiv.org/abs/2306.15447) | NeurIPS 2023 | 2023/06/26 | None | Generator Level | I+T→T |
|[**Visual Adversarial Examples Jailbreak Aligned Large Language Models**](https://arxiv.org/abs/2306.13213) | AAAI 2024 | 2023/06/22 | [Github](https://github.com/Unispac/Visual-Adversarial-Examples-Jailbreak-Large-Language-Models) | Generator Level | I+T→T |
|[**On Evaluating Adversarial Robustness of Large Vision-Language Models**](https://proceedings.neurips.cc/paper_files/paper/2023/hash/a97b58c4f7551053b0512f92244b0810-Abstract-Conference.html) | NeurIPS 2023 | 2023/05/26 | [Homepage](https://yunqing-me.github.io/AttackVLM/) | Encoder Level | I+T→T |


## Jailbreak Attack of Any-to-Vision Models
|  Title  |   Venue  |   Date   |   Code   | Taxonomy | Multimodal Model |
|:--------|:--------:|:--------:|:--------:|:--------:|:--------:|
|[**TokenProber: Jailbreaking Text-to-image Models via Fine-grained Word Impact Analysis**](https://arxiv.org/abs/2505.08804) | Arxiv 2025 | 2025/05/11 | None | --- | T→I |
|[**Inception: Jailbreak the Memory Mechanism of Text-to-Image Generation Systems**](https://arxiv.org/abs/2504.20376) | Arxiv 2025 | 2025/04/29 | None | --- | T→I |
|[**Token-Level Constraint Boundary Search for Jailbreaking Text-to-Image Models**](https://arxiv.org/abs/2504.11106) | Arxiv 2025 | 2025/04/15 | None | --- | T→I |
|[**Mind the Trojan Horse: Image Prompt Adapter Enabling Scalable and Deceptive Jailbreaking**](https://arxiv.org/abs/2504.05838) | CVPR 2025 Highlight | 2025/04/08 | [Github](https://github.com/fhdnskfbeuv/attackIPA) | --- | T→I |
|[**Reason2Attack: Jailbreaking Text-to-Image Models via LLM Reasoning**](https://arxiv.org/abs/2503.17987) | Arxiv 2025 | 2025/03/23 | None | --- | T→I |
|[**Jailbreaking Safeguarded Text-to-Image Models via Large Language Models**](https://arxiv.org/abs/2503.01839) | Arxiv 2025 | 2025/03/03 | None | --- | T→I |
|[**Unified Prompt Attack Against Text-to-Image Generation Models**](https://arxiv.org/abs/2502.16423) | TPAMI 2025 | 2024/02/23 | None | --- | T→I |
|[**T2ISafety: Benchmark for Assessing Fairness, Toxicity, and Privacy in Image Generation**](https://arxiv.org/abs/2501.12612) | Arxiv 2025 | 2025/02/22 | [Github](https://github.com/adwardlee/t2i_safety) | --- | T→I |
|[**CogMorph: Cognitive Morphing Attacks for Text-to-Image Models**](https://arxiv.org/abs/2501.11815) | Arxiv 2025 | 2024/01/21 | None | --- | T→I |
|[**FameBias: Embedding Manipulation Bias Attack in Text-to-Image Models**](https://arxiv.org/abs/2412.18302) | Arxiv 2024 | 2024/12/24 | None | --- | T→I |
|[**Antelope: Potent and Concealed Jailbreak Attack Strategy**](https://arxiv.org/abs/2412.08156) | Arxiv 2024 | 2024/12/11 | None | --- | T→I |
|[**Multimodal Pragmatic Jailbreak on Text-to-image Models**](https://arxiv.org/abs/2409.19149) | Arxiv 2024 | 2024/09/27 | None | --- | T→I |
|[**In-Context Experience Replay Facilitates Safety Red-Teaming of Text-to-Image Diffusion Models**](https://arxiv.org/abs/2411.16769) | Arxiv 2024 | 2024/11/25 | None | Output Level | T→I |
|[**Unfiltered and Unseen: Universal Multimodal Jailbreak Attacks on Text-to-Image Model Defenses**](https://openreview.net/forum?id=sshYEYQ82L) | Openreview | 2024/11/13 | None | --- | T→I |
|[**AdvI2I: Adversarial Image Attack on Image-to-Image Diffusion models**](https://arxiv.org/abs/2410.21471) | Arxiv 2024 | 2024/10/28 | [Github](https://github.com/Spinozaaa/AdvI2I) | Encoder Level | T→I |
|[**Chain-of-Jailbreak Attack for Image Generation Models via Editing Step by Step**](https://arxiv.org/abs/2410.03869) | Arxiv 2024 | 2024/10/4 | None | Output Level | T→I |
|[**ColJailBreak: Collaborative Generation and Editing for Jailbreaking Text-to-Image Deep Generation**](https://openreview.net/forum?id=eGIzeTmAtE) | NeurIPS 2024 | 2024/9/25 | [Github](https://github.com/tsingqguo/coljailbreak) | Input Level | T→I |
|[**HTS-Attack: Heuristic Token Search for Jailbreaking Text-to-Image Models**](https://arxiv.org/abs/2408.13896) | Arxiv 2024 | 2024/08/25 | None | Output Level | T→I |
|[**Perception-guided Jailbreak against Text-to-Image Models**](https://arxiv.org/abs/2408.10848) | AAAI 2025 | 2024/08/20 | [Github](https://github.com/LeLiang-SJTU/Perception-guided-Jailbreak-) | Input Level | T→I |
|[**DiffZOO: A Purely Query-Based Black-Box Attack for Red-teaming Text-to-Image Generative Model via Zeroth Order Optimization**](https://arxiv.org/abs/2408.11071) | NAACL 2025 | 2024/08/18 | [Github](https://github.com/CherryBlueberry/DiffZOO) | Output Level | T→I |
|[**Jailbreaking Prompt Attack: A Controllable Adversarial Attack against Diffusion Models**](https://arxiv.org/abs/2404.02928) | Arxiv 2024 | 2024/08/02 | None | Encoder Level | T→I |
|[**Jailbreaking Text-to-Image Models with LLM-Based Agents**](https://arxiv.org/abs/2408.00523) | Arxiv 2024 | 2024/08/01 | None | Output Level | T→I |
|[**Automatic Jailbreaking of the Text-to-Image Generative AI Systems**](https://arxiv.org/abs/2405.16567) | ICML 2024 Workshop NextGenAISafety | 2024/05/26 | [Github](https://github.com/Kim-Minseon/APGP) | Output Level | T→I |
|[**UPAM: Unified Prompt Attack in Text-to-Image Generation Models Against Both Textual Filters and Visual Checkers**](https://arxiv.org/abs/2405.11336) | ICML 2024 | 2024/05/18 | None | Input Level | T→I |
|[**BSPA: Exploring Black-box Stealthy Prompt Attacks against Image Generators**](https://arxiv.org/abs/2402.15218) | Arxiv 2024 | 2024/02/23 | None | Input Level | T→I |
|[**Harnessing LLM to Attack LLM-Guarded Text-to-Image Models**](https://arxiv.org/abs/2312.07130) | Arxiv 2023 | 2023/12/12 | [Github](https://github.com/researchcode001/Divide-and-Conquer-Attack) | Input Level | T→I |
|[**MMA-Diffusion: MultiModal Attack on Diffusion Models**](https://arxiv.org/abs/2311.17516) | CVPR 2024 | 2023/11/29 | [Github](https://github.com/cure-lab/MMA-Diffusion) | Encoder Level | T→I |
|[**VA3: Virtually Assured Amplification Attack on Probabilistic Copyright Protection for Text-to-Image Generative Models**](https://arxiv.org/abs/2312.00057) | CVPR 2024 | 2023/11/29 | [Github](https://github.com/South7X/VA3) | Generator Level | T→I |
|[**To Generate or Not? Safety-Driven Unlearned Diffusion Models Are Still Easy To Generate Unsafe Images ... For Now**](https://arxiv.org/abs/2310.11868) | ECCV 2024 | 2023/10/18 | [Github](https://github.com/OPTML-Group/Diffusion-MU-Attack) | Generator Level | T→I |
|[**Ring-A-Bell! How Reliable are Concept Removal Methods for Diffusion Models?**](https://arxiv.org/abs/2310.10012) | ICLR 2024 | 2023/10/16 | [Github]( https://github.com/chiayi-hsu/Ring-A-Bell) | Encoder Level | T→I |
|[**SurrogatePrompt: Bypassing the Safety Filter of Text-To-Image Models via Substitution**](https://arxiv.org/abs/2309.14122) | CCS 2024 | 2023/09/25 | None | Input Level | T→I |
|[**Prompting4Debugging: Red-Teaming Text-to-Image Diffusion Models by Finding Problematic Prompts**](https://arxiv.org/abs/2309.06135) | ICML 2024 | 2023/09/12 | [Github](https://github.com/joycenerd/P4D) | Generator Level | T→I |
|[**SneakyPrompt: Jailbreaking Text-to-image Generative Models**](https://arxiv.org/abs/2305.12082) | Symposium on Security and Privacy 2024 | 2023/05/20 | [Github](https://github.com/Yuchen413/text2image_safety) | Output Level | T→I |
|[**Red-Teaming the Stable Diffusion Safety Filter**](https://arxiv.org/abs/2210.04610) | NeurIPSW 2022 | 2022/10/03 | None | Input Level | T→I |




## Jailbreak Attack of Any-to-Any Models
|  Title  |   Venue  |   Date   |   Code   | Taxonomy | Multimodal Model |
|:--------|:--------:|:--------:|:--------:|:--------:|:--------:|
|[**Gradient-based Jailbreak Images for Multimodal Fusion Models**](https://arxiv.org/abs/2410.03489) | Arxiv 2024 | 2024/10/4 | [Github](https://github.com/facebookresearch/multimodal-fusion-jailbreaks) | Generator Level | I+T→I+T |
|[**Voice jailbreak attacks against gpt-4o**](https://arxiv.org/abs/2405.19103) | Arxiv 2024 | 2024/05/29 | [Github](https://github.com/TrustAIRLab/VoiceJailbreakAttack) | Output Level | Any→Any |

## 🛡️Jailbreak Defense

### 📖Defense-Intro

**Current efforts made in the jailbreak defense of multimodal generative models include two lines of work: Discriminative defense and Transformative defense.**
- Discriminative defenses: is constrained to classification tasks for assigning binary labels. 

<img src="https://github.com/liuxuannan/Awesome-Multimodal-Jailbreak/blob/main/pic/jailbreak_discriminative_defense.png" alt="jailbreak_discriminative_defense" />

- Transformative Defense: aims to produce appropriate and safe responses in the presence of malicious or adversarial inputs.

<img src="https://github.com/liuxuannan/Awesome-Multimodal-Jailbreak/blob/main/pic/jailbreak_transformative_defense.png" alt="jailbreak_transformative_defense" />

### 📑Papers

Below are the papers related to jailbreak defense.

## Jailbreak Defense of Any-to-Text Models
|  Title  |   Venue  |   Date   |   Code   | Taxonomy | Multimodal Model |
|:--------|:--------:|:--------:|:--------:|:--------:|:--------:|
|[**Do We Really Need Curated Malicious Data for Safety Alignment in Multi-modal Large Language Models?**](https://arxiv.org/abs/2504.10000) | CVPR 2025 | 2025/04/14 | None | --- | I+T→T |
|[**JailDAM: Jailbreak Detection with Adaptive Memory for Vision-Language Model**](https://arxiv.org/abs/2504.03770) | Arxiv 2025 | 2025/04/3 | [Github](https://github.com/ShenzheZhu/JailDAM) | --- | I+T→T |
|[**Hyperbolic Safety-Aware Vision-Language Models**](https://arxiv.org/abs/2503.12127) | CVPR 2025 | 2025/03/15 | [Github](https://github.com/aimagelab/HySAC) | --- | I+T→T |
|[**Tit-for-Tat: Safeguarding Large Vision-Language Models Against Jailbreak Attacks via Adversarial Defense**](https://arxiv.org/abs/2503.11619) | Arxiv 2025 | 2025/03/14 | None | --- | I+T→T |
|[**Utilizing Jailbreak Probability to Attack and Safeguard Multimodal LLMs**](https://arxiv.org/abs/2503.06989) | Arxiv 2025 | 2025/03/10 | None | --- | I+T→T |
|[**Adversarial Training for Multimodal Large Language Models against Jailbreak Attacks**](https://arxiv.org/abs/2503.04833) | Arxiv 2025 | 2025/03/05 | None | --- | I+T→T |
|[**HiddenDetect: Detecting Jailbreak Attacks against Large Vision-Language Models via Monitoring Hidden States**](https://arxiv.org/abs/2502.14744) | ACL 2025 | 2025/02/20 | [Github](https://github.com/leigest519/HiddenDetect) | --- | I+T→T |
|[**SafeEraser: Enhancing Safety in Multimodal Large Language Models through Multimodal Machine Unlearning**](https://arxiv.org/abs/2502.12520) | Arxiv 2025 | 2025/02/18 | None | --- | I+T→T |
|[**Understanding and Rectifying Safety Perception Distortion in VLMs**](https://arxiv.org/abs/2502.13095) | Arxiv 2025 | 2025/02/18 | None | --- | I+T→T |
|[**Adversary-Aware DPO: Enhancing Safety Alignment in Vision Language Models via Adversarial Training**](https://arxiv.org/abs/2502.11455) | Arxiv 2025 | 2025/02/17 | None | --- | I+T→T |
|[**Towards Robust Multimodal Large Language Models Against Jailbreak Attacks**](https://arxiv.org/abs/2502.00653) | Arxiv 2025 | 2025/02/02 | None | --- | I+T→T |
|[**Rethinking Bottlenecks in Safety Fine-Tuning of Vision Language Models**](https://arxiv.org/abs/2501.18533) | Arxiv 2025 | 2025/01/30 | [Github](https://github.com/DripNowhy/MIS) | --- | I+T→T |
|[**Internal Activation Revision: Safeguarding Vision Language Models Without Parameter Update**](https://arxiv.org/abs/2501.16378) | Arxiv 2025 | 2025/01/24 | None | --- | I+T→T |
|[**MSTS: A Multimodal Safety Test Suite for Vision-Language Models**](https://arxiv.org/abs/2501.10057) | Arxiv 2025 | 2025/01/17 | [Github](https://github.com/paul-rottger/msts-multimodal-safety) | --- | I+T→T |
|[**Spot Risks Before Speaking! Unraveling Safety Attention Heads in Large Vision-Language Models**](https://arxiv.org/abs/2501.02029) | Arxiv 2025 | 2025/01/03 | [Github](https://github.com/Ziwei-Zheng/SAHs) | --- | I+T→T |
|[**Defending LVLMs Against Vision Attacks through Partial-Perception Supervision**](https://arxiv.org/abs/2412.12722) | Arxiv 2024 | 2024/12/17 | None | --- | I+T→T |
|[**VLMGuard: Defending VLMs against Malicious Prompts via Unlabeled Data**](https://arxiv.org/abs/2410.00296) | Arxiv 2024 | 2024/10/01 | None | --- | I+T→T |
|[**Immune: Improving Safety Against Jailbreaks in Multi-modal LLMs via Inference-Time Alignment**](https://arxiv.org/abs/2411.18688) | CVPR 2025 | 2024/11/27 | [Github](https://github.com/itsvaibhav01/Immune) | Output Level | I+T→T |
|[**Steering Away from Harm: An Adaptive Approach to Defending Vision Language Model Against Jailbreaks**](https://arxiv.org/abs/2411.16721) | CVPR 2025 | 2024/11/23 | [Github](https://github.com/ASTRAL-Group/ASTRA) | Generator Level | I+T→T |
|[**Uniguard: Towards universal safety guardrails for jailbreak attacks on multimodal large language models**](https://arxiv.org/abs/2411.01703) | Arxiv 2024 | 2024/11/03 | None | Input Level | I+T→T |
|[**Effective and Efficient Adversarial Detection for Vision-Language Models via A Single Vector**](https://arxiv.org/abs/2410.22888) | Arxiv 2024 | 2024/10/30 | None | Generator Level | I+T→T |
|[**BlueSuffix: Reinforced Blue Teaming for Vision-Language Models Against Jailbreak Attacks**](https://arxiv.org/abs/2410.20971) | ICLR 2025 | 2024/10/28 | [Github](https://github.com/Vinsonzyh/BlueSuffix) | Input Level | I+T→T |
|[**The Great Contradiction Showdown: How Jailbreak and Stealth Wrestle in Vision-Language Models?**](https://arxiv.org/abs/2410.01438) | Arxiv 2024 | 2024/10/02 | None | Input Level | I+T→T |
|[**CoCA: Regaining Safety-awareness of Multimodal Large Language Models with Constitutional Calibration**](https://arxiv.org/abs/2409.11365) | COLM 2024 | 2024/9/17 | None | Output Level | I+T→T |
|[**Securing Vision-Language Models with a Robust Encoder Against Jailbreak and Adversarial Attacks**](https://arxiv.org/abs/2409.07353) | Arxiv 2024 | 2024/09/11 | None | Encoder Level | I+T→T |
|[**Bathe: Defense against the jailbreak attack in multimodal large language models by treating harmful instruction as backdoor trigger**](https://arxiv.org/abs/2408.09093) | Arxiv 2024 | 2024/08/17 | None | Generator Level | I+T→T |
|[**Defending jailbreak attack in vlms via cross-modality information detector**](https://arxiv.org/html/2407.21659v2) | Arxiv 2024 | 2024/07/31 | [Github](https://github.com/pandragonxiii/cider) | Encoder Level | I+T→T |
|[**Sim-clip: Unsupervised siamese adversarial fine-tuning for robust and semantically-rich vision-language models**](https://arxiv.org/abs/2407.14971) | Arxiv 2024 | 2024/07/20 | [Github](https://github.com/speedlab-git/SimCLIP) | Encoder Level | I+T→T |
|[**Cross-modal safety alignment: Is textual unlearning all you need?**](https://arxiv.org/abs/2406.02575) | Arxiv 2024 | 2024/05/27 | None | Generator Level | I+T→T |
|[**Safety alignment for vision language models**](https://arxiv.org/abs/2405.13581) | Arxiv 2024 | 2024/05/22 | None | Generator Level | I+T→T |
|[**Adashield: Safeguarding multimodal large language models from structure-based attack via adaptive shield prompting**](https://arxiv.org/abs/2403.09513) | ECCV 2024 | 2024/05/14 | [Github](https://github.com/SaFoLab-WISC/AdaShield) | Input Level | I+T→T |
|[**Eyes Closed, Safety On: Protecting Multimodal LLMs via Image-to-Text Transformation**](https://arxiv.org/abs/2403.09572) | ECCV 2024 | 2024/03/14 | [Github](https://github.com/gyhdog99/ECSO) | Output Level | I+T→T |
|[**Safety fine-tuning at (almost) no cost: A baseline for vision large language models**](https://arxiv.org/abs/2402.02207) | ICML 2024 | 2024/02/03 | [Github](https://github.com/ys-zong/VLGuard) | Generator Level | I+T→T |
|[**Inferaligner: Inference-time alignment for harmlessness through cross-model guidance**](https://arxiv.org/abs/2401.11206) | EMNLP 2024 | 2024/01/20 | [Github](https://github.com/Jihuai-wpy/InferAligner) | Generator Level | I+T→T |
|[**Mllm-protector: Ensuring mllm’s safety without hurting performance**](https://arxiv.org/abs/2401.02906) | EMNLP 2024 | 2024/01/05 | [Github](https://github.com/pipilurj/MLLM-protector) | Output Level | I+T→T |
|[**Jailguard: A universal detection framework for llm prompt-based attacks**](https://arxiv.org/abs/2312.10766) | Arxiv 2023 | 2023/12/17 | [Github](https://github.com/shiningrain/JailGuard) | Output Level | I+T→T |
|[**Safety-tuned llamas: Lessons from improving the safety of large language models that follow instructions**](https://arxiv.org/abs/2309.07875) | ICLR 2024 | 2023/09/14 | [Github](https://github.com/vinid/safety-tuned-llamas) | Generator Level | I+T→T |



## Jailbreak Defense of Any-to-Vision Models
|  Title  |   Venue  |   Date   |   Code   | Taxonomy | Multimodal Model |
|:--------|:--------:|:--------:|:--------:|:--------:|:--------:|
|[**T2VShield: Model-Agnostic Jailbreak Defense for Text-to-Video Models**](https://arxiv.org/abs/2504.15512) | Arxiv 2025 | 2025/04/22 | None | --- | T→V |
|[**Towards NSFW-Free Text-to-Image Generation via Safety-Constraint Direct Preference Optimization**](https://arxiv.org/abs/2504.14290) | Arxiv 2025 | 2025/04/19 | None | --- | T→I |
|**I2VGuard: Safeguarding Images against Misuse in Diffusion-based Image-to-Video Models** | CVPR 2025 | --- | None | --- | T→V |
|[**Hyperbolic Safety-Aware Vision-Language Models**](https://arxiv.org/abs/2503.12127) | CVPR 2025 | 2025/03/15 | [Github](https://github.com/aimagelab/HySAC) | --- | T→I |
|[**Distorting Embedding Space for Safety: A Defense Mechanism for Adversarially Robust Diffusion Models**](https://arxiv.org/abs/2503.07389) | Arxiv 2025 | 2025/03/10 | [Github](https://github.com/ddgoodgood/TRCE) | --- | T→I |
|[**SafeText: Safe Text-to-image Models via Aligning the Text Encoder**](https://arxiv.org/abs/2502.20623) | Arxiv 2025 | 2025/02/28 | None | --- | T→I |
|[**Comprehensive Assessment and Analysis for NSFW Content Erasure in Text-to-Image Diffusion Models**](https://arxiv.org/abs/2502.12527) | Arxiv 2025 | 2025/02/18 | None | --- | T→I |
|[**A Comprehensive Survey on Concept Erasure in Text-to-Image Diffusion Models**](https://arxiv.org/abs/2502.14896) | Arxiv 2025 | 2025/02/17 | None | --- | T→I |
|[**Training-Free Safe Denoisers for Safe Use of Diffusion Models**](https://arxiv.org/abs/2502.08011) | Arxiv 2025 | 2025/02/11 | None | --- | T→I |
|[**Beautiful Images, Toxic Words: Understanding and Addressing Offensive Text in Generated Images**](https://arxiv.org/abs/2502.05066) | Arxiv 2025 | 2025/02/07 | None | --- | T→I |
|[**Distorting Embedding Space for Safety: A Defense Mechanism for Adversarially Robust Diffusion Models**](https://arxiv.org/abs/2501.18877) | Arxiv 2025 | 2025/01/30 | [Github](https://github.com/aei13/DES) | --- | T→I |
|[**CE-SDWV: Effective and Efficient Concept Erasure for Text-to-Image Diffusion Models via a Semantic-Driven Word Vocabulary**](https://arxiv.org/abs/2501.15562) | Arxiv 2025 | 2025/01/26 | None | --- | T→I |
|[**CROPS: Model-Agnostic Training-Free Framework for Safe Image Synthesis with Latent Diffusion Models**](https://arxiv.org/abs/2501.05359) | Arxiv 2025 | 2025/01/09 | None | --- | T→I |
|[**PromptGuard: Soft Prompt-Guided Unsafe Content Moderation for Text-to-Image Models**](https://arxiv.org/abs/2501.03544) | Arxiv 2025 | 2025/01/07 | [Homepage](https://prompt-guard.github.io/) | --- | T→I |
|[**DuMo: Dual Encoder Modulation Network for Precise Concept Erasure**](https://arxiv.org/abs/2501.01125) | AAAI 2025 | 2025/01/02 | [Github](https://github.com/Maplebb/DuMo) | --- | T→I |
|[**AEIOU: A Unified Defense Framework against NSFW Prompts in Text-to-Image Models**](https://arxiv.org/abs/2412.18123) | Arxiv 2024 | 2024/12/24 | None | --- | T→I |
|[**SafeCFG: Redirecting Harmful Classifier-Free Guidance for Safe Generation**](https://arxiv.org/abs/2412.16039) | Arxiv 2024 | 2024/12/20 | None | --- | T→I |
|[**SafetyDPO: Scalable Safety Alignment for Text-to-Image Generation**](https://arxiv.org/abs/2412.10493) | Arxiv 2024 | 2024/12/13 | [Github](https://github.com/Visualignment/SafetyDPO) | --- | T→I |
|[**TraSCE: Trajectory Steering for Concept Erasure**](https://arxiv.org/abs/2412.07658) | Arxiv 2024 | 2024/12/10 | [Github](https://github.com/anubhav1997/TraSCE/) | --- | T→I |
|[**Buster: Incorporating Backdoor Attacks into Text Encoder to Mitigate NSFW Content Generation**](https://arxiv.org/abs/2412.07249) | Arxiv 2024 | 2024/12/10 | None | --- | T→I |
|[**Safeguarding Text-to-Image Generation via Inference-Time Prompt-Noise Optimization**](https://arxiv.org/abs/2412.03876) | Arxiv 2024 | 2024/12/05 | [Github](https://github.com/JonP07/Diffusion-PNO) | --- | T→I |
|[**Safety Alignment Backfires: Preventing the Re-emergence of Suppressed Concepts in Fine-tuned Text-to-Image Diffusion Models**](https://arxiv.org/abs/2412.00357) | Arxiv 2024 | 2024/11/30 | None | --- | T→I |
|[**Safety Without Semantic Disruptions: Editing-free Safe Image Generation via Context-preserving Dual Latent Reconstruction**](https://arxiv.org/abs/2411.13982) | Arxiv 2024 | 2024/11/21 | None | --- | T→I |
|[**Safe Text-to-Image Generation:Simply Sanitize the Prompt Embedding**](https://arxiv.org/abs/2411.10329) | Arxiv 2024 | 2024/11/15 | None | Encoder Level | T→I |
|[**Safree: Training-free and adaptive guard for safe text-to-image and video generation**](https://arxiv.org/abs/2410.12761) | ICLR 2025 | 2024/10/16 | [Github](https://github.com/jaehong31/SAFREE) | Generator Level | T→I/T→V |
|[**Shielddiff: Suppressing sexual content generation from diffusion models through reinforcement learning**](https://arxiv.org/abs/2410.05309) | Arxiv 2024 | 2024/10/04 | None | Generator Level | T→I |
|[**Dark miner: Defend against unsafe generation for text-to-image diffusion models**](https://arxiv.org/html/2409.17682) | Arxiv 2024 | 2024/09/26 | None | Generator Level | T→I |
|[**Score forgetting distillation: A swift, data-free method for machine unlearning in diffusion models**](https://arxiv.org/abs/2409.11219) | ICLR 2025 | 2024/09/17 | None | Generator Level | T→I |
|[**EIUP: A Training-Free Approach to Erase Non-Compliant Concepts Conditioned on Implicit Unsafe Prompts**](https://arxiv.org/abs/2408.01014) | Arxiv 2024 | 2024/08/02 | None | Generator Level | T→I |
|[**Direct Unlearning Optimization for Robust and Safe Text-to-Image Models**](https://arxiv.org/abs/2407.21035) | NeurIPS 2024 | 2024/07/17 | [Github](https://github.com/naver-ai/DUO) | Generator Level | T→I |
|[**Reliable and Efficient Concept Erasure of Text-to-Image Diffusion Models**](https://arxiv.org/abs/2407.12383) | ECCV 2024 | 2024/07/17 | [Github](https://github.com/CharlesGong12/RECE) | Generator Level | T→I |
|[**Conceptprune: Concept editing in diffusion models via skilled neuron pruning**](https://arxiv.org/abs/2405.19237) | Arxiv 2024 | 2024/05/29 | [Github](https://github.com/ruchikachavhan/concept-prune) | Generator Level | T→I |
|[**Pruning for Robust Concept Erasing in Diffusion Models**](https://arxiv.org/abs/2405.16534) | NeurIPS SafeGenAi Workshop 2024 | 2024/05/26 | None | Generator Level | T→I |
|[**Defensive unlearning with adversarial training for robust concept erasure in diffusion models**](https://arxiv.org/abs/2405.15234) | NeurIPS 2024 | 2024/05/24 | [Github](https://github.com/OPTML-Group/AdvUnlearn) | Encoder Level | T→I |
|[**Unlearning concepts in diffusion model via concept domain correction and concept preserving gradient**](https://arxiv.org/abs/2405.15304) | AAAI 2025 | 2024/05/24 | [Github](https://github.com/yongliang-wu/DoCo) | Generator Level | T→I |
|[**Espresso: Robust Concept Filtering in Text-to-Image Models**](https://arxiv.org/abs/2404.19227) | CODASPY 2025 | 2024/04/30 | None | Output Level | T→I |
|[**Latent Guard: a Safety Framework for Text-to-image Generation**](https://arxiv.org/abs/2404.08031) | ECCV 2024 | 2024/04/11 | [Github](https://github.com/rt219/LatentGuard) | Encoder Level | T→I |
|[**SafeGen: Mitigating Sexually Explicit Content Generation in Text-to-Image Models**](https://arxiv.org/abs/2404.06666) | ACM CCS 2024 | 2024/04/10 | [Github](https://github.com/LetterLiGo/SafeGen_CCS2024) | Generator Level | T→I |
|[**Salun: Empowering machine unlearning via gradient-based weight saliency in both image classification and generation**](https://arxiv.org/abs/2310.12508) | ICLR 2024 | 2024/04/04 | [Github](https://github.com/OPTML-Group/Unlearn-Saliency) | Generator Level | T→I |
|[**GuardT→I: Defending Text-to-Image Models from Adversarial Prompts**](https://arxiv.org/abs/2403.01446) | NeurIPS 2024 | 2024/03/03 | None | Encoder Level | T→I |
|[**Universal prompt optimizer for safe text-to-image generation**](https://arxiv.org/abs/2402.10882) | NAACL 2024 | 2024/02/16 | [Github](https://github.com/Wu-Zongyu/POSI) | Input Level | T→I |
|[**Erasediff: Erasing data influence in diffusion models**](https://arxiv.org/abs/2401.05779) | Arxiv 2024 | 2024/01/11 | None | Generator Level | T→I |
|[**Localization and manipulation of immoral visual cues for safe text-to-image generation**](https://openaccess.thecvf.com/content/WACV2024/papers/Park_Localization_and_Manipulation_of_Immoral_Visual_Cues_for_Safe_Text-to-Image_WACV_2024_paper.pdf) | WACV 2024 | 2024/01/01 | None | Output Level | T→I |
|[**Receler: Reliable concept erasing of text-to-image diffusion models via lightweight erasers**](https://arxiv.org/abs/2311.17717) | ECCV 2024 | 2023/11/29 | [Github](https://github.com/jasper0314-huang/Receler) | Generator Level | T→I |
|[**Self-discovering interpretable diffusion latent directions for responsible text-to-image generation**](https://arxiv.org/abs/2311.17216) | CVPR 2024 | 2023/11/28 | [Github](https://github.com/hangligit/InterpretDiffusion) | Encoder Level | T→I |
|[**Safe-CLIP: Removing NSFW Concepts from Vision-and-Language Models**](https://arxiv.org/abs/2311.16254) | ECCV 2024 | 2023/11/27 | [Github](https://github.com/aimagelab/safe-clip) | Encoder Level | T→I |
|[**Mace: Mass concept erasure in diffusion models**](https://arxiv.org/abs/2403.06135) | CVPR 2024 | 2023/10/19 | [Github](https://github.com/Shilin-LU/MACE) | Generator Level | T→I |
|[**Implicit concept removal of diffusion models**](https://arxiv.org/abs/2310.05873) | ECCV 2024 | 2023/10/09 | None | Input Level | T→I |
|[**Unified concept editing in diffusion models**](https://arxiv.org/abs/2308.14761) | WACV 2024 | 2023/08/25 | [Github](https://github.com/rohitgandikota/unified-concept-editing) | Generator Level | T→I |
|[**Towards safe self-distillation of internet-scale text-to-image diffusion models**](https://arxiv.org/abs/2307.05977) | ICML 2023 Workshop on Challenges in Deployable Generative AI | 2023/07/12 | [Github](https://github.com/nannullna/safe-diffusion) | Generator Level | T→I |
|[**Forget-Me-Not: Learning to Forget in Text-to-Image Diffusion Models**](https://arxiv.org/abs/2303.17591) | CVPR 2024 | 2023/05/30 | [Github](https://github.com/SHI-Labs/Forget-Me-Not) | Generator Level | T→I |
|[**Erasing concepts from diffusion models**](https://arxiv.org/abs/2303.07345) | ICCV 2023 | 2023/05/13 | [Github](https://github.com/rohitgandikota/erasing) | Generator Level | T→I |
|[**Safe Latent Diffusion: Mitigating Inappropriate Degeneration in Diffusion Models**](https://arxiv.org/abs/2211.05105) | CVPR 2023 | 2022/11/09 | [Github](https://github.com/ml-research/safe-latent-diffusion) | Generator Level | T→I |


## Jailbreak Defense of Any-to-Any Models
|  Title  |   Venue  |   Date   |   Code   | Taxonomy | Multimodal Model |
|:--------|:--------:|:--------:|:--------:|:--------:|:--------:|


## 💯Evaluation

### ⭐️Evaluation Datasets
**Below is a comparison table of publicly available representative evaluation datasets and a description of each attribute in the table.**
- Collected: raw data created by humans or collected from real-world websites.<br> 
- Reconstructed: Data reorganized from other existing datasets.<br> 
- Synthesized: AI-generated data using LLM or diffusion models.<br> 
- Adversarial: Adversarial data generated by jailbreak attack methods.<br>
#### Used to Any-to-Text Models
|  Dataset  | Text Source   |   Image Source   | Volume | Theme | Access  | 
|:--------|:--------:|:--------:|:--------:|:--------:|:--------:|
|**Figstep** | Synthesized | Adversarial | 500 | 10 | [Github](https://github.com/ThuCCSLab/FigStep)  |
|**AdvBench** | Synthesized | --- | 500 | --- | [Github](https://github.com/llm-attacks/llm-attacks)  |
|**ReadTeam-2K** | Collected & Reconstructed & Synthesized | N/A | 2000 | 16 | [Huggingface](https://huggingface.co/datasets/JailbreakV-28K/JailBreakV-28k)  |
|**HarmBench** | Collected | --- | 510 | 4 | [Github](https://github.com/centerforaisafety/HarmBench)  |
|**HADES** | Synthesized | Collected & Synthesized & Adversarial | 750 | 5 | [Github](https://github.com/AoiDragon/HADES)  |
|**MM-SafetyBench** | Synthesized | Synthesized & Adversarial | 5040 | 13 | [Github](https://github.com/isXinLiu/MM-SafetyBench)  |
|**JailBreakV-28K** | Adversarial | Reconstructed & Synthesized | 28000 | 16 | [Huggingface](https://huggingface.co/datasets/JailbreakV-28K/JailBreakV-28k)  |

#### Used to Any-to-Vision Models
|  Dataset  |   Text Source   |   Image Source   | Volume |  Access  | Theme |
|:--------|:--------:|:--------:|:--------:|:--------:|:--------:|
|**NSFW-200** | Synthesized | --- | 200 | --- | [Github](https://github.com/Yuchen413/texT→Imagesafety)  |
|**MMA** | Reconstructed & Adversarial | Adversarial | 1000 | --- | [Huggingface](https://huggingface.co/datasets/YijunYang280/MMA-Diffusion-NSFW-adv-prompts-benchmark)  |
|**VBCDE** | Reconstructed & Adversarial | --- | 100 | 5 | [Github](https://github.com/researchcode001/Divide-and-Conquer-Attack)  |
|**I2P** | Collected | Collected | 4703 | 7 | [Huggingface](https://huggingface.co/datasets/AIML-TUDA/i2p)  |
|**Unsafe Diffusion** | Collected & Reconstructed | --- | 1434 | --- | [Github](https://github.com/YitingQu/unsafe-diffusion)  |
|**MACE-Celebrity** | Collected | --- | 1000 | --- | [Github](https://github.com/Shilin-LU/MACE)  |
|**MACE-Art** | Reconstructed | --- | 1000 | --- | [Github](https://github.com/Shilin-LU/MACE)  |
|**MPUP** | Synthesized | --- | 1200 | 4 | [Huggingface](https://huggingface.co/datasets/tongliuphysics/multimodalpragmatic)  |
|**T2VSafetyBench** | Reconstructed & Synthesized & Adversarial | --- | 4400 | 12 |  [Github](https://github.com/yibo-miao/T2VSafetyBench/tree/main)  |


### 📚Evaluation Methods
**Current evaluation methods are primarily classified into two categories: manual evaluation and automated evaluation.**
- Manual evaluation involves human assessment to determine if the content is toxic, offering a direct and interpretable method of evaluation.
- Automated approaches assess the safety of multimodal generative models by employing a range of techniques, including detector-based, GPT-based, and rule-based methods.

<img src="https://github.com/liuxuannan/Awesome-Multimodal-Jailbreak/blob/main/pic/jailbreak_evaluation.png" alt="jailbreak_evaluation" width="600" />

<!-- **Detector-based approaches utilize pre-trained classifiers to automatically detect and identify harmful content within generated outputs. These classifiers are trained on large, annotated datasets that cover a range of unsafe categories, such as toxicity, violence, or explicit material. By leveraging these pre-trained models, detector-based methods can efficiently flag inappropriate content.** -->

#### Text Detector
|  Toxicity detector  |   Access  | 
|:--------|:--------:|
|**LLama-Guard** | [Huggingface](https://huggingface.co/meta-llama) |
|**LLama-Guard2** | [Huggingface](https://huggingface.co/meta-llama) |
|**Detoxify** | [Github](https://github.com/unitaryai/detoxify) |
|**GPTFUZZER** | [Huggingface](https://huggingface.co/hubert233/GPTFuzz/tree/main) |
|**Perspective API** | [Website](https://perspectiveapi.com/) |

#### Image Detector
|  Toxicity detector  |   Access  | 
|:--------|:--------:|
|**NudeNet** | [Github](https://github.com/platelminto/NudeNetClassifier) |
|**Q16** | [Github](https://github.com/ml-research/Q16) |
|**Safety Checker** | [Huggingface](https://huggingface.co/CompVis/stable-diffusion-safety-checker) |
|**Imgcensor** | [Github](https://github.com/lucasxlu/XCloud/tree/master/research/imgcensor) |
|**Multi-headed Safety Classifier** | [Github](https://github.com/YitingQu/unsafe-diffusion) |

## 😉Citation

If you find this work useful in your research, Please kindly cite using the following BibTex:
```bib
@article{liu2024jailbreak,
    title={Jailbreak Attacks and Defenses against Multimodal Generative Models: A Survey},
    author={Liu, Xuannan and Cui, Xing and Li, Peipei and Li, Zekun and Huang, Huaibo and Xia, Shuhan and Zhang, Miaoxuan and Zou, Yueying and He, Ran},
    journal={arXiv preprint arXiv:2411.09259},
    year={2024},
}
```


