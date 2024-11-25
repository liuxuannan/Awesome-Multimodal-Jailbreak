
# 😈🛡️Awesome-Jailbreak-against-Multimodal-Generative-Models
🔥🔥🔥 **Jailbreak Attacks and Defenses against Multimodal Generative Models: A Survey**

**[Paper](https://arxiv.org/abs/2411.09259)**  

We've curated a collection of the latest 😋, most comprehensive 😎, and most valuable 🤩 resources on Jailbreak Attack and Defense Multimodel Generative Models.<br> 
But we don't stop there; Our repository is constantly updated to ensure you have the most current information at your fingertips.

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

![survey model](https://github.com/liuxuannan/Awesome-Multimodal-Jailbreak/blob/main/pic/survey_model_00.png)

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



## 🔥Multimodal Generative Models

**Below are tables of model short name and representative generative models used for jailbreak. For input/output modalities, I: Image, T: Text, V: Video, A: Audio.**

### 📑Any-to-Text Models (LLM Backbone)
|  Short Name  |   Modality  |   Representative Model   |  
|:--------|:--------:|:--------:|
| IT2T | I + T → T |[LLaVA](https://arxiv.org/abs/2304.08485), [MiniGPT4](https://arxiv.org/abs/2304.10592), [InstructBLIP](https://arxiv.org/abs/2305.06500) |
| VT2T | V + T → T |[Video-LLaVA](https://arxiv.org/abs/2311.10122), [Video-LLaMA](https://arxiv.org/abs/2306.02858) |
| AT2T | A + T → T |[Audio Flamingo](https://arxiv.org/abs/2402.01831), [Audiopalm](https://arxiv.org/abs/2306.12925) |

### 📖Any-to-Vision (Diffusion Backbone)
|  Short Name  |   Modality  |   Representative Model   |  
|:--------|:--------:|:--------:|
| T2I | T → I |[Stable Diffusion](https://arxiv.org/abs/2112.10752), [Midjourney](https://www.midjourney.com/), [DALLE](https://platform.openai.com/docs/guides/moderation/overview) |
| IT2I | I + T → I |[DreamBooth](https://arxiv.org/abs/2208.12242), [InstructP2P](https://arxiv.org/abs/2306.07154) |
| T2V | T → V |[Open-Sora](https://github.com/hpcaitech/Open-Sora), [Stable Video Diffusion](https://arxiv.org/abs/2311.15127) |
| IT2V | I + T → V |[VideoPoet](https://arxiv.org/abs/2312.14125), [CogVideoX](https://arxiv.org/abs/2408.06072) |

### 📰Any-to-Any (Unified Backbone)
|  Short Name  |   Modality  |   Representative Model   |  
|:--------|:--------:|:--------:|
| IT2IT | I + T → I + T |[Next-GPT](https://arxiv.org/abs/2309.05519), [Chameleon](https://arxiv.org/abs/2304.09842) |
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

<img src="https://github.com/liuxuannan/Awesome-Multimodal-Jailbreak/blob/main/pic/jailbreal_attack_B.png" alt="jailbreak_attack_white_and_gray_box" />

### 📑Papers
Below are the papers related to jailbreak attacks.
## Jailbreak Attack of Any-to-Text Models
|  Title  |   Venue  |   Date   |   Code   | Taxonomy |  Multimodal Model|
|:--------|:--------:|:--------:|:--------:|:--------:|:--------:|
|[**Audio is the achilles’heel: Red teaming audio large multimodal models**](https://arxiv.org/abs/2410.23861) | Arxiv 2024 | 2024/10/31 | None | Input Level | AT2T |
|[**Advweb: Controllable black-box attacks on vlm-powered web agents**](https://arxiv.org/abs/2410.17401) | Arxiv 2024 | 2024/10/22 | None | Input Level | IT2T |
|[**Image Hijacks: Adversarial Images can Control Generative Models at Runtime**](https://arxiv.org/abs/2309.00236) | Arxiv 2024 | 2024/09/01 | [Github](https://github.com/euanong/image-hijacks) | Generator Level | IT2T |
|[**Can Large Language Models Automatically Jailbreak GPT-4V?**](https://arxiv.org/abs/2407.16686) | CCS 2024 | 2024/07/23 | None | Input Level | IT2T |
|[**Arondight: Red Teaming Large Vision Language Models with Auto-generated Multi-modal Jailbreak Prompts**](https://arxiv.org/abs/2407.15050) | ACM MM 2024 | 2024/07/21 | None | Input Level | IT2T |
|[**Image-to-Text Logic Jailbreak: Your Imagination can Help You Do Anything**](https://arxiv.org/abs/2407.02534) | Arxiv 2024 | 2024/07/01 | None | Input Level | IT2T |
|[**From LLMs to MLLMs: Exploring the Landscape of Multimodal Jailbreaking**](https://arxiv.org/abs/2406.14859) | Arxiv 2024 | 2024/06/21 | None | Encoder Level | IT2T |
|[**Jailbreak Vision Language Models via Bi-Modal Adversarial Prompt**](https://arxiv.org/abs/2406.04031) | Arxiv 2024 | 2024/06/06 | [Github](https://github.com/NY1024/BAP-Jailbreak-Vision-Language-Models-via-Bi-Modal-Adversarial-Prompt) | Generator Level | IT2T |
|[**Efficient LLM-Jailbreaking by Introducing Visual Modality**](https://arxiv.org/abs/2405.20015) | Arxiv 2024 | 2024/05/30 | None | Generator Level | IT2T |
|[**White-box Multimodal Jailbreaks Against Large Vision-Language Models**](https://arxiv.org/abs/2405.17894) | Arxiv 2024 | 2024/05/28 | None | Generator Level | IT2T |
|[**Visual-RolePlay: Universal Jailbreak Attack on MultiModal Large Language Models via Role-playing Image Character**](https://arxiv.org/abs/2405.20773) | Arxiv 2024 | 2024/05/25 | None | Input Level | IT2T |
|[**Images are Achilles' Heel of Alignment: Exploiting Visual Vulnerabilities for Jailbreaking Multimodal Large Language Models**](https://arxiv.org/abs/2403.09792) | ECCV 2024 | 2024/05/14 | [Github](https://github.com/RUCAIBox/HADES)| Generator Level | IT2T |
|[**Agent Smith: A Single Image Can Jailbreak One Million Multimodal LLM Agents Exponentially Fast**](https://arxiv.org/abs/2402.08567) | ICML 2024 | 2024/02/13 | [Github](https://github.com/sail-sg/Agent-Smith) | Decoder Level | IT2T |
|[**Jailbreaking Attack against Multimodal Large Language Model**](https://arxiv.org/abs/2402.02309) | Arxiv 2024 | 2024/02/04 | None| Generator Level | IT2T |
|[**Jailbreak in pieces: Compositional Adversarial Attacks on Multi-Modal Language Models**](https://openreview.net/forum?id=plmBsXHxgR&trk=public_post_comment-text) | ICLR 2024 Spotlight | 2024/01/16 | [Github](https://github.com/erfanshayegani/Jailbreak-In-Pieces) | Encoder Level | IT2T |
|[**How Many Unicorns Are in This Image? A Safety Evaluation Benchmark for Vision LLMs**](https://arxiv.org/abs/2311.16101) | ECCV 2024 | 2023/11/27 | [Github](https://github.com/UCSC-VLAA/vllm-safety-benchmark) | Encoder Level | IT2T |
|[**Jailbreaking GPT-4V via Self-Adversarial Attacks with System Prompts**](https://arxiv.org/abs/2311.09127) | Arxiv 2023 | 2023/11/15 | None | Input Level | IT2T |
|[**FigStep: Jailbreaking Large Vision-language Models via Typographic Visual Prompts**](https://arxiv.org/abs/2311.05608) | Arxiv 2023 | 2023/11/09 | [Github](https://github.com/ThuCCSLab/FigStep) | Input Level | IT2T |
|[**Are aligned neural networks adversarially aligned?**](https://arxiv.org/abs/2306.15447) | Arxiv 2023 | 2023/06/26 | None | Generator Level | IT2T |
|[**Visual Adversarial Examples Jailbreak Aligned Large Language Models**](https://arxiv.org/abs/2306.13213) | AAAI 2024 | 2023/06/22 | [Github](https://github.com/Unispac/Visual-Adversarial-Examples-Jailbreak-Large-Language-Models) | Generator Level | IT2T |

## Jailbreak Attack of Any-to-Vision Models
|  Title  |   Venue  |   Date   |   Code   | Taxonomy | Multimodal Model |
|:--------|:--------:|:--------:|:--------:|:--------:|:--------:|
|[**RT-Attack: Jailbreaking Text-to-Image Models via Random Token**](https://arxiv.org/abs/2408.13896) | Arxiv 2024 | 2024/08/25 | None | Encoder Level | T2I |
|[**Perception-guided Jailbreak against Text-to-Image Models**](https://arxiv.org/abs/2408.10848) | Arxiv 2024 | 2024/08/20 | None | Input Level | T2I |
|[**DiffZOO: A Purely Query-Based Black-Box Attack for Red-teaming Text-to-Image Generative Model via Zeroth Order Optimization**](https://arxiv.org/abs/2408.11071) | Arxiv 2024 | 2024/08/18 | None | Output Level | T2I |
|[**Jailbreaking Prompt Attack: A Controllable Adversarial Attack against Diffusion Models**](https://arxiv.org/abs/2404.02928) | Arxiv 2024 | 2024/08/02 | None | Encoder Level | T2I |
|[**Jailbreaking Text-to-Image Models with LLM-Based Agents**](https://arxiv.org/abs/2408.00523) | Arxiv 2024 | 2024/08/01 | None | Input Level | T2I |
|[**Automatic Jailbreaking of the Text-to-Image Generative AI Systems**](https://arxiv.org/abs/2405.16567) | Arxiv 2024 | 2024/05/26 | None | Input Level | T2I |
|[**UPAM: Unified Prompt Attack in Text-to-Image Generation Models Against Both Textual Filters and Visual Checkers**](https://arxiv.org/abs/2405.11336) | ICML 2024 | 2024/05/18 | None | Input Level | T2I |
|[**BSPA: Exploring Black-box Stealthy Prompt Attacks against Image Generators**](https://arxiv.org/abs/2402.15218) | Arxiv 2024 | 2024/02/23 | None | Encoder Level | T2I |
|[**Divide-and-Conquer Attack: Harnessing the Power of LLM to Bypass Safety Filters of Text-to-Image Models**](https://arxiv.org/abs/2312.07130) | Arxiv 2023 | 2023/12/12 | [Github](https://github.com/researchcode001/Divide-and-Conquer-Attack) | Input Level | T2I |
|[**MMA-Diffusion: MultiModal Attack on Diffusion Models**](https://arxiv.org/abs/2311.17516) | CVPR 2024 | 2023/11/29 | [Github](https://github.com/cure-lab/MMA-Diffusion) | Encoder Level | T2I |
|[**VA3: Virtually Assured Amplification Attack on Probabilistic Copyright Protection for Text-to-Image Generative Models**](https://arxiv.org/abs/2312.00057) | CVPR 2024 | 2023/11/29 | [Github](https://github.com/South7X/VA3) | Encoder Level | T2I |
|[**To Generate or Not? Safety-Driven Unlearned Diffusion Models Are Still Easy To Generate Unsafe Images ... For Now**](https://arxiv.org/abs/2310.11868) | ECCV 2024 | 2023/10/18 | [Github](https://github.com/OPTML-Group/Diffusion-MU-Attack) | Generator Level | T2I |
|[**Ring-A-Bell! How Reliable are Concept Removal Methods for Diffusion Models?**](https://arxiv.org/abs/2310.10012) | ICLR 2024 | 2023/10/16 | [Github]( https://github.com/chiayi-hsu/Ring-A-Bell) | Encoder Level | T2I |
|[**SurrogatePrompt: Bypassing the Safety Filter of Text-To-Image Models via Substitution**](https://arxiv.org/abs/2309.14122) | CCS 2024 | 2023/09/25 | [Github](https://github.com/researchcode001/Divide-and-Conquer-Attack) | Input Level | T2I |
|[**Prompting4Debugging: Red-Teaming Text-to-Image Diffusion Models by Finding Problematic Prompts**](https://arxiv.org/abs/2309.06135) | ICML 2024 | 2023/09/12 | [Github](https://github.com/joycenerd/P4D) | Generator Level | T2I |
|[**SneakyPrompt: Jailbreaking Text-to-image Generative Models**](https://arxiv.org/abs/2305.12082) | Symposium on Security and Privacy 2024 | 2023/05/20 | [Github](https://github.com/Yuchen413/text2image_safety) | Output Level | T2I |
|[**Red-Teaming the Stable Diffusion Safety Filter**](https://arxiv.org/abs/2210.04610) | NeurIPSW 2022 | 2022/10/03 | None | Input Level | T2I |




## Jailbreak Attack of Any-to-Any Models
|  Title  |   Venue  |   Date   |   Code   | Taxonomy | Multimodal Model |
|:--------|:--------:|:--------:|:--------:|:--------:|:--------:|
|[**Voice jailbreak attacks against gpt-4o**](https://arxiv.org/abs/2405.19103) | Arxiv 2024 | 2024/05/29 | [Github](https://github.com/TrustAIRLab/VoiceJailbreakAttack) | Input Level | Any2Any |

## 🛡️Jailbreak Defense

### 📖Defense-Intro

**Current efforts made in the jailbreak defense of multimodal generative models include two lines of work: Discriminative defense and Transformative defense.**
- Discriminative defenses: is constrained to classification tasks for assigning binary labels. 

<img src="https://github.com/liuxuannan/Awesome-Multimodal-Jailbreak/blob/main/pic/jailbreak_discriminative_defense_00.png" alt="jailbreak_discriminative_defense" />

- Transformative Defense: aims to produce appropriate and safe responses in the presence of malicious or adversarial inputs.

<img src="https://github.com/liuxuannan/Awesome-Multimodal-Jailbreak/blob/main/pic/jailbreak_defense_all_00.png" alt="jailbreak_transformative_defense" />

### 📑Papers

Below are the papers related to jailbreak defense.

## Jailbreak Defense of Any-to-Text Models
|  Title  |   Venue  |   Date   |   Code   | Taxonomy | Multimodal Model |
|:--------|:--------:|:--------:|:--------:|:--------:|:--------:|
|[**Uniguard: Towards universal safety guardrails for jailbreak attacks on multimodal large language models**](https://arxiv.org/abs/2411.01703) | Arxiv 2024 | 2024/11/03 | None | Input Level | IT2T |
|[**Effective and Efficient Adversarial Detection for Vision-Language Models via A Single Vector**](https://arxiv.org/abs/2410.22888) | Arxiv 2024 | 2024/10/30 | None | Generator Level | IT2T |
|[**BlueSuffix: Reinforced Blue Teaming for Vision-Language Models Against Jailbreak Attacks**](https://arxiv.org/abs/2410.20971) | Arxiv 2024 | 2024/10/28 | None | Input Level | IT2T |
|[**Information-theoretical principled trade-off between jailbreakability and stealthiness on vision language models**](https://arxiv.org/abs/2410.01438) | Arxiv 2024 | 2024/10/02 | None | Input Level | IT2T |
|[**Securing Vision-Language Models with a Robust Encoder Against Jailbreak and Adversarial Attacks**](https://arxiv.org/abs/2409.07353) | Arxiv 2024 | 2024/09/11 | None | Encoder Level | IT2T |
|[**Bathe: Defense against the jailbreak attack in multimodal large language models by treating harmful instruction as backdoor trigger**](https://arxiv.org/abs/2408.09093) | Arxiv 2024 | 2024/08/17 | None | Generator Level | IT2T |
|[**Defending jailbreak attack in vlms via cross-modality information detector**](https://arxiv.org/html/2407.21659v2) | Arxiv 2024 | 2024/07/31 | [Github](https://github.com/pandragonxiii/cider) | Encoder Level | IT2T |
|[**Sim-clip: Unsupervised siamese adversarial fine-tuning for robust and semantically-rich vision-language models**](https://arxiv.org/abs/2407.14971) | Arxiv 2024 | 2024/07/20 | None | Encoder Level | IT2T |
|[**Cross-modal safety alignment: Is textual unlearning all you need?**](https://arxiv.org/abs/2406.02575) | Arxiv 2024 | 2024/05/27 | None | Generator Level | IT2T |
|[**Safety alignment for vision language models**](https://arxiv.org/abs/2405.13581) | Arxiv 2024 | 2024/05/22 | None | Generator Level | IT2T |
|[**Adashield: Safeguarding multimodal large language models from structure-based attack via adaptive shield prompting**](https://arxiv.org/abs/2403.09513) | ECCV 2024 | 2024/05/14 | [Github](https://github.com/SaFoLab-WISC/AdaShield) | Input Level | IT2T
|[**Safety fine-tuning at (almost) no cost: A baseline for vision large language models**](https://arxiv.org/abs/2402.02207) | ICML 2024 | 2024/02/03 | [Github](https://github.com/ys-zong/VLGuard) | Generator Level | IT2T |
|[**Inferaligner: Inference-time alignment for harmlessness through cross-model guidance**](https://arxiv.org/abs/2401.11206) | Arxiv 2024 | 2024/01/20 | [Github](https://github.com/Jihuai-wpy/InferAligner) | Encoder Level | IT2T |
|[**Mllm-protector: Ensuring mllm’s safety without hurting performance**](https://arxiv.org/abs/2401.02906) | Arxiv 2024 | 2024/01/05 | [Github](https://github.com/pipilurj/MLLM-protector) | Output Level | IT2T |
|[**Jailguard: A universal detection framework for llm prompt-based attacks**](https://arxiv.org/abs/2312.10766) | Arxiv 2023 | 2023/12/17 | None | Encoder Level | IT2T |
|[**Safety-tuned llamas: Lessons from improving the safety of large language models that follow instructions**](https://arxiv.org/abs/2309.07875) | ICLR 2024 | 2023/09/14 | [Github](https://github.com/vinid/safety-tuned-llamas) | Generator Level | IT2T |





## Jailbreak Defense of Any-to-Vision Models
|  Title  |   Venue  |   Date   |   Code   | Taxonomy | Multimodal Model |
|:--------|:--------:|:--------:|:--------:|:--------:|:--------:|
|[**Dark miner: Defend against unsafe generation for text-to-image diffusion models**](https://arxiv.org/html/2409.17682) | Arxiv 2024 | 2024/09/26 | None | Generator Level | T2I |
|[**Score forgetting distillation: A swift, data-free method for machine unlearning in diffusion models**](https://arxiv.org/abs/2409.11219) | Arxiv 2024 | 2024/09/17 | None | Generator Level | T2I |
|[**EIUP: A Training-Free Approach to Erase Non-Compliant Concepts Conditioned on Implicit Unsafe Prompts**](https://arxiv.org/abs/2408.01014) | Arxiv 2024 | 2024/08/02 | None | Generator Level | T2I |
|[**Direct Unlearning Optimization for Robust and Safe Text-to-Image Models**](https://arxiv.org/abs/2407.21035) | ICML GenLaw workshop 2024 | 2024/07/17 | None | Encoder Level | T2I |
|[**Reliable and Efficient Concept Erasure of Text-to-Image Diffusion Models**](https://arxiv.org/abs/2407.12383) | ECCV 2024 | 2024/07/17 | [Github](https://github.com/CharlesGong12/RECE) | Generator Level | T2I |
|[**Conceptprune: Concept editing in diffusion models via skilled neuron pruning**](https://arxiv.org/abs/2405.19237) | Arxiv 2024 | 2024/05/29 | [Github](https://github.com/ruchikachavhan/concept-prune) | Generator Level | T2I |
|[**Pruning for Robust Concept Erasing in Diffusion Models**](https://arxiv.org/abs/2405.16534) | Arxiv 2024 | 2024/05/26 | None | Generator Level | T2I |
|[**Defensive unlearning with adversarial training for robust concept erasure in diffusion models**](https://arxiv.org/abs/2405.15234) | Nips 2024 | 2024/05/24 | [Github](https://github.com/OPTML-Group/AdvUnlearn) | Encoder Level | T2I |
|[**Unlearning concepts in diffusion model via concept domain correction and concept preserving gradient**](https://arxiv.org/abs/2405.15304) | Arxiv 2024 | 2024/05/24 | None | Encoder Level | T2I |
|[**Espresso: Robust Concept Filtering in Text-to-Image Models**](https://arxiv.org/abs/2404.19227) | Arxiv 2024 | 2024/04/30 | None | Output Level | T2I |
|[**Latent Guard: a Safety Framework for Text-to-image Generation**](https://arxiv.org/abs/2404.08031) | ECCV 2024 | 2024/04/11 | [Github](https://github.com/rt219/LatentGuard) | Encoder Level | T2I |
|[**SafeGen: Mitigating Sexually Explicit Content Generation in Text-to-Image Models**](https://arxiv.org/abs/2404.06666) | ACM CCS 2024 | 2024/04/10 | [Github](https://github.com/LetterLiGo/SafeGen_CCS2024) | Generator Level | T2I |
|[**Salun: Empowering machine unlearning via gradient-based weight saliency in both image classification and generation**](https://arxiv.org/abs/2310.12508) | ICLR 2024 | 2024/04/04 | [Github](https://github.com/OPTML-Group/Unlearn-Saliency) | Generator Level | T2I |
|[**GuardT2I: Defending Text-to-Image Models from Adversarial Prompts**](https://arxiv.org/abs/2403.01446) | NIPS 2024 | 2024/03/03 | None | Input Level | T2I |
|[**Universal prompt optimizer for safe text-to-image generation**](https://arxiv.org/abs/2402.10882) | Arxiv 2024 | 2024/02/16 | None | Input Level | T2I |
|[**Erasediff: Erasing data influence in diffusion models**](https://arxiv.org/abs/2401.05779) | Arxiv 2024 | 2024/01/11 | None | Generator Level | T2I |
|[**Localization and manipulation of immoral visual cues for safe text-to-image generation**](https://openaccess.thecvf.com/content/WACV2024/papers/Park_Localization_and_Manipulation_of_Immoral_Visual_Cues_for_Safe_Text-to-Image_WACV_2024_paper.pdf) | WACV 2024 | 2024/01/01 | None | Output Level | T2I |
|[**Receler: Reliable concept erasing of text-to-image diffusion models via lightweight erasers**](https://arxiv.org/abs/2311.17717) | ECCV 2024 | 2023/11/29 | None | Generator Level | T2I |
|[**Self-discovering interpretable diffusion latent directions for responsible text-to-image generation**](https://arxiv.org/abs/2311.17216) | CVPR 2024 | 2023/11/28 | [Github](https://github.com/hangligit/InterpretDiffusion) | Input Level | T2I |
|[**Safe-CLIP: Removing NSFW Concepts from Vision-and-Language Models**](https://arxiv.org/abs/2311.16254) | ECCV 2024 | 2023/11/27 | [Github](https://github.com/aimagelab/safe-clip) | Encoder Level | T2I |
|[**Mace: Mass concept erasure in diffusion models**](https://arxiv.org/abs/2403.06135) | CVPR 2024 | 2023/10/19 | [Github](https://github.com/Shilin-LU/MACE) | Generator Level | T2I |
|[**Implicit concept removal of diffusion models**](https://arxiv.org/abs/2310.05873) | ECCV 2024 | 2023/10/09 | None | Input Level | T2I |
|[**Towards safe self-distillation of internet-scale text-to-image diffusion models**](https://arxiv.org/abs/2307.05977) | ICML 2023 Workshop on Challenges in Deployable Generative AI | 2023/07/12 | [Github](https://github.com/nannullna/safe-diffusion) | Generator Level | T2I |
|[**Unified concept editing in diffusion models**](https://arxiv.org/abs/2308.14761) | WACV 2024 | 2023/08/25 | [Github](https://github.com/rohitgandikota/unified-concept-editing) | Generator Level | T2I |
|[**Forget-Me-Not: Learning to Forget in Text-to-Image Diffusion Models**](https://arxiv.org/abs/2303.17591) | CVPR 2024 | 2023/05/30 | [Github](https://github.com/SHI-Labs/Forget-Me-Not) | Generator Level | T2I |
|[**Erasing concepts from diffusion models**](https://arxiv.org/abs/2303.07345) | ICCV 2023 | 2023/05/13 | [Github](https://github.com/rohitgandikota/erasing) | Generator Level | T2I |
|[**Safe Latent Diffusion: Mitigating Inappropriate Degeneration in Diffusion Models**](https://arxiv.org/abs/2211.05105) | CVPR 2023 | 2022/11/09 | [Github](https://github.com/ml-research/safe-latent-diffusion) | Generator Level | T2I |

## Jailbreak Defense of Any-to-Any Models
|  Title  |   Venue  |   Date   |   Code   | Taxonomy | Multimodal Model |
|:--------|:--------:|:--------:|:--------:|:--------:|:--------:|
|[**Safree: Training-free and adaptive guard for safe text-to-image and video generation**](https://arxiv.org/abs/2410.12761) | Arxiv 2024 | 2024/10/16 | None | Output Level | T2V |

## 💯Evaluation

### ⭐️Evaluation Datasets

#### Used to Any-to-Text Models
|  Dataset  |   Task  |   Text Source   |   Image Source   | Volume |  Access  | 
|:--------|:--------:|:--------:|:--------:|:--------:|:--------:|
|**SafeBench** | Attack | GPT generation | Typography | 500 | [Github](https://github.com/ThuCCSLab/FigStep)  |
|**AdvBench** | Attack | LLM generation | N/A | 500 | [Github](https://github.com/llm-attacks/llm-attacks)  |
|**ReadTeam-2K** | Attack | Exist. & GPT Generation | N/A | 2000 | [Huggingface](https://huggingface.co/datasets/JailbreakV-28K/JailBreakV-28k)  |
|**HarmBench** | Attack & Defense | Unpublished | N/A | 320 | [Github](https://github.com/centerforaisafety/HarmBench)  |
|**HADES** | Defense | GPT generation | Typography & Diffusion Generation | 750 | [Github](https://github.com/AoiDragon/HADES)  |
|**MM-SafetyBench** | Defense | GPT generation | Typography & Diffusion Generation | 5040 | [Github](https://github.com/isXinLiu/MM-SafetyBench)  |
|**JailBreakV-28K** | Defense | Adv. Prompt on ReadTeam-2K | Blank & Noise & Natural & Synthesize | 28000 | [Huggingface](https://huggingface.co/datasets/JailbreakV-28K/JailBreakV-28k)  |
|**VLGuard** | Defense | GPT generation | Exist. | 3000 | [Huggingface](https://huggingface.co/datasets/ys-zong/VLGuard)  |

#### Used to Any-to-Vision Models
|  Dataset  |   Task  |   Text Source   |   Image Source   | Volume |  Access  | 
|:--------|:--------:|:--------:|:--------:|:--------:|:--------:|
|**NSFW-200** | Attack | Human curation | N/A | 200 | [Github](https://github.com/Yuchen413/text2imagesafety)  |
|**MMA** | Attack | Exist.& Adv. Prompt | N/A | 1000 | [Huggingface](https://huggingface.co/datasets/YijunYang280/MMA-Diffusion-NSFW-adv-prompts-benchmark)  |
|**VBCDE-100** | Attack | Human curation | N/A | 100 | [Github](https://github.com/researchcode001/Divide-and-Conquer-Attack)  |
|**I2P** | Attack & Defense | Real-world Website | Real-world Website | 4703 | [Huggingface](https://huggingface.co/datasets/AIML-TUDA/i2p)  |
|**Unsafe Diffusion** | Defense | Human curation& Website&Exist. | N/A | 1434 | [Github](https://github.com/YitingQu/unsafe-diffusion)  |
|**MACE** | Defense | Human curation | Diffusion Generation | 200 | [Github](https://github.com/Shilin-LU/MACE)  |


### 📚Evaluation Methods
**Current evaluation methods are primarily classified into two categories: manual evaluation and automated evaluation.**
- Manual evaluation involves human assessment to determine if the content is toxic, offering a direct and interpretable method of evaluation.
- Automated approaches assess the safety of multimodal generative models by employing a range of techniques, including detector-based, GPT-based, and rule-based methods.

<img src="https://github.com/liuxuannan/Awesome-Multimodal-Jailbreak/blob/main/pic/jailbreak_evaluation_00.png" alt="jailbreak_evaluation" width="600" />

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



