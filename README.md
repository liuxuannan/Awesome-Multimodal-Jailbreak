
# 🛡️Awesome-Jailbreak-against-Multimodal-Generative-Models
![survey model](https://github.com/liuxuannan/Awesome-Multimodal-Jailbreak/blob/main/pic/survey_model_00.png)


## 🤗Introduction


**Welcome to our Awesome-Jailbreak-against-Multimodal-Generative-Models! We provides a comprehensive overview of jailbreak vulnerabilities in multimodal generative models!** 🥰🥰🥰<br>

<br>
We've curated a collection of the latest 😋, most comprehensive 😎, and most valuable 🤩 resources on Jailbreak Attack and Defense Multimodel Generative Models.<br> 
But we don't stop there; Our repository is constantly updated to ensure you have the most current information at your fingertips.

> If a resource is relevant to multiple subcategories, we place it under each applicable section.<br>


**🧑‍💻 Our Work**
- Leveraging the layered structure of generative models, we systematically examine jailbreak attacks and corresponding defense strategies across the input, encoding, decoding, and output layers.<br>
- We establish a detailed taxonomy of attack vectors, defense mechanisms, and evaluation frameworks specific to multimodal generative models.<br>
- Our review encompasses a wide array of input-output configurations, offering a nuanced examination of jailbreak tactics and defenses applicable to any-to-text, any-to-vision, and any-to-any modalities within generative systems.<br>

**✔️ Perfect for Majority**
- For beginners curious about jailbreak attack and defense, our repository serves as a compass for grasping the big picture and diving into the details. 
The brief introductions to papers in different fields retained in the README provide a beginner-friendly navigation through interesting directions in the field;
- For seasoned researchers, this repository is a tool to keep you informed and fill any gaps in your knowledge. 
Within each subtopic, we are diligently updating all the latest content and continuously backfilling with previous work. 
Our thorough compilation and careful selection are time-savers for you.

**🧭 How to Use this Guide**
- Quick Start: In the README, users can find a curated list of select information, along with links to various consultations.
- In-Depth Exploration: If you have a special interest in a particular area of the paper, delve into the markdown file for more information.



## 🚀Table of Contents

- [🛡️Awesome-Jailbreak-against-Multimodal-Generative-Models🛡️](#️Awesome-Jailbreak-against-Multimodal-Generative-Models)
  - [🤗Introduction](#introduction)
  - [🚀Table of Contents](#table-of-contents)
  - [🔥Multimodal Generative Models](#Multimodal-Generative-Models)
    - [📑Any-to-Text (LLM Backbone)](#Any-to-Text (LLM Backbone))
    - [📖Any-to-Vision (Diffusion Backbone)](#Any-to-Vision (Diffusion Backbone))
    - [📰Any-to-Any (Unified Backbone)](#Any-to-Any (Unified Backbone))
  - [😈Jailbreak Attack](#jailbreak-attack)
    - [📖Introduction](#Introduction)
    - [📑Papers](#Papers)
  - [🛡️Jailbreak Defense](#️jailbreak-defense)
    - [📖Introduction](#Introduction)
    - [📑Papers](#Papers)
  - [💯Resources](#Resources)
    - [⭐️Datasets](#datasets)
      - [Used to Any-to-Text Models](#Used-to-Any-to-Text-Models)
      - [Used to Any-to-Vision Models](#Used-to-Any-to-Vision-Models)
    - [📚Detectors](#detectors)
      - [Used to Any-to-Text Models](#Used-to-Any-to-Text-Models)
      - [Used to Any-to-Text Models](#Used-to-Any-to-Vision-Models)
  - [📑Other Survey and Bench]



## 🔥Multimodal Generative Models
### 📑Any-to-Text (LLM Backbone)
**Any-to-Text Models integrate inputs from multiple modalities, encode them, and utilize an LLM as afoundational model for generating textual outputs.**
|  Title  |   Venue  |   Date   |   Code   | Taxonomy |
|:--------|:--------:|:--------:|:--------:|:--------:|

### 📖Any-to-Vision (Diffusion Backbone)
**Any-to-Vision Models encode inputs across different modalities as guided information and leverage diffusion models to generate visual outputs.**
|  Title  |   Venue  |   Date   |   Code   | Taxonomy |
|:--------|:--------:|:--------:|:--------:|:--------:|

### 📰Any-to-Any (Unified Backbone)
**Any-to-Any models perceive inputs and generate outputs in arbitrary combinations of text, image, video, and audio.**
|  Title  |   Venue  |   Date   |   Code   | Taxonomy |
|:--------|:--------:|:--------:|:--------:|:--------:|


## 😈JailBreak Attack

### 📖Introduction
<img src="https://github.com/liuxuannan/Awesome-Multimodal-Jailbreak/blob/main/pic/jailbreak_attack_all_00.png" alt="jailbreak_attack_overview" width="600" />

**Existing jailbreak attack methods mainly target the Any-to-Text Models and Any-to-Vision Models. JailBreak Attack methods can be categorized into white-box and black-box attacks. Regarding white-box attacks, we consider model-level attacks, including attacks at both the encoder and decoder. Regarding the black-box setting, the attack is limited to surface-level interactions, targeting the model’s input and/or output.**


### 📑Papers
All the papers related to jailbreak attacks can be found in both [Jailbreak Attack of Multimodal LLM-based Models](https://github.com/liuxuannan/Awesome-Multimodal-Jailbreak/blob/main/Jailbreak%20Attack%20of%20Multimodal%20LLM-based%20Models.md) and [Jailbreak Attack of Multimodal Diffusion-based Models](https://github.com/liuxuannan/Awesome-Multimodal-Jailbreak/blob/main/Jailbreak%20Attack%20of%20Multimodal%20Diffusion-based%20Models.md) files


## 🛡️Jailbreak Defense

### 📖Introduction

<img src="https://github.com/liuxuannan/Awesome-Multimodal-Jailbreak/blob/main/pic/jailbreak_defense_all_00.png" alt="jailbreak_transformative_defense" width="600" />
<img src="https://github.com/liuxuannan/Awesome-Multimodal-Jailbreak/blob/main/pic/jailbreak_discriminative_defense_00.png" alt="jailbreak_discriminative_defense" width="600" />

**In order to cope with jailbreak attacks and improve the security of multimodal foundation models, existing work makes efforts in both Transformative defense and Discriminative defense**


### 📑Papers

All the papers related to jailbreak attacks can be found in both [Jailbreak Defense of Multimodal LLM-based Models](https://github.com/liuxuannan/Awesome-Multimodal-Jailbreak/blob/main/Jailbreak%20Defense%20of%20Multimodal%20LLM-based%20Models.md) and [Jailbreak Defense of Multimodal Diffusion-based Models](https://github.com/liuxuannan/Awesome-Multimodal-Jailbreak/blob/main/Jailbreak%20Defense%20of%20Multimodal%20Diffusion-based%20Models.md) files


## 💯Resources

### ⭐️Datasets

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


### 📚Detectors


#### Used to Any-to-Text Models
|  Toxicity detector  |   Access  | 
|:--------|:--------:|
|**LLama-Guard** | [Huggingface](https://huggingface.co/meta-llama) |
|**LLama-Guard2** | [Huggingface](https://huggingface.co/meta-llama) |
|**Detoxify** | [Github](https://github.com/unitaryai/detoxify) |
|**GPTFUZZER** | [Huggingface](https://huggingface.co/hubert233/GPTFuzz/tree/main) |
|**Perspective API** | [Website](https://perspectiveapi.com/) |

#### Used to Any-to-Vision Models
|  Toxicity detector  |   Access  | 
|:--------|:--------:|
|**NudeNet** | [Github](https://github.com/platelminto/NudeNetClassifier) |
|**Q16** | [Github](https://github.com/ml-research/Q16) |
|**Safety Checker** | [Huggingface](https://huggingface.co/CompVis/stable-diffusion-safety-checker) |
|**Imgcensor** | [Github](https://github.com/lucasxlu/XCloud/tree/master/research/imgcensor) |
|**Multi-headed Safety Classifier** | [Github](https://github.com/YitingQu/unsafe-diffusion) |


## 📑Other Survey and Bench

Related survey and benchmark can be found in [Related survey](https://github.com/liuxuannan/Awesome-Multimodal-Jailbreak/blob/main/Related%20Survey.md), [Attack Bench of Multimodal Generative Models](https://github.com/liuxuannan/Awesome-Multimodal-Jailbreak/blob/main/Attack%20Bench%20of%20Multimodal%20Generative%20Models.md) and [Defense Bench of Multimodal Generative Models](https://github.com/liuxuannan/Awesome-Multimodal-Jailbreak/blob/main/Defense%20Bench%20of%20Multimodal%20Generative%20Models.md)

# Awesome Papers

# Related Survey
|  Title  |   Venue  |   Date   |   Code   | Taxonomy |
|:--------|:--------:|:--------:|:--------:|:--------:|
|[**A Survey of Attacks on Large Vision-Language Models: Resources, Advances, and Future Trends**](https://arxiv.org/pdf/2407.07403) | Arxiv 2024 | 2024/07/10 | [Github](https://github.com/liudaizong/Awesome-LVLM-Attack) | MLLM |
|[**Safety of Multimodal Large Language Models on Images and Texts**](https://arxiv.org/abs/2402.00357) | Arxiv 2024 | 2024/06/20 | [Github](https://github.com/isXinLiu/Awesome-MLLM-Safety) | MLLM |
|[**Unbridled Icarus: A Survey of the Potential Perils of Image Inputs in Multimodal Large Language Model Security**](https://arxiv.org/abs/2404.05264) | Arxiv 2024 | 2024/08/08 | None | MLLM |
|[**JailbreakZoo: Survey, Landscapes, and Horizons in Jailbreaking Large Language and Vision-Language Models**](https://arxiv.org/abs/2407.01599) | Arxiv 2024 | 2024/07/25 | [Github]( https://github.com/Allen-piexl/JailbreakZoo) | MLLM |
|[**Adversarial Attacks and Defenses on Text-to-Image Diffusion Models: A Survey**](https://arxiv.org/abs/2407.15861) | Arxiv 2024 | 2024/07/10 | [Github]( https://github.com/datar001/Awesome-AD-on-T2IDM) | Diffusion |



# Attack Bench of Multimodal Generative Models
|  Title  |   Venue  |   Date   |   Code   | Taxonomy |
|:--------|:--------:|:--------:|:--------:|:--------:|
|[**JailBreakV-28K: A Benchmark for Assessing the Robustness of MultiModal Large Language Models against Jailbreak Attacks**](https://arxiv.org/abs/2404.03027) | Arxiv 2024 | 2024/04/03 | [Github](https://eddyluo1232.github.io/JailBreakV28K/) | Encoder Level |
|[**MM-SafetyBench: A Benchmark for Safety Evaluation of Multimodal Large Language Models**](https://arxiv.org/abs/2311.09127) | ECCV 2024 | 2024/11/29 | None | Input Level |
|[**How Many Unicorns Are in This Image? A Safety Evaluation Benchmark for Vision LLMs**](https://arxiv.org/abs/2311.16101) | Arxiv 2023 | 2023/11/27 | [Github](https://github.com/UCSC-VLAA/vllm-safety-benchmark) | Encoder Level |
|[**✳Multimodal Pragmatic Jailbreak on Text-to-image Models**](https://www.arxiv.org/abs/2409.19149) | Arxiv 2024 | 2024/09/27 | [Github](https://github.com/multimodalpragmatic/multimodalpragmatic/tree/main) | Encoder Level |


# Defense Bench of Multimodal Generative Models
|  Title  |   Venue  |   Date   |   Code   | Taxonomy |
|:--------|:--------:|:--------:|:--------:|:--------:|
|[**✳SPA-VL: A Comprehensive Safety Preference Alignment Dataset for Vision Language Model**](https://arxiv.org/abs/2406.12030) | Arxiv 2024 | 2024/06/17 | [Github](https://github.com/EchoseChen/SPA-VL-RLHF) | Encoder Level |

## Jailbreak Attack of Multimodal LLM-based Models
|  Title  |   Venue  |   Date   |   Code   | Taxonomy |
|:--------|:--------:|:--------:|:--------:|:--------:|
|[**Jailbreak in pieces: Compositional Adversarial Attacks on Multi-Modal Language Models**](https://openreview.net/forum?id=plmBsXHxgR&trk=public_post_comment-text) | ICLR 2024 Spotlight | 2024/01/16 | [Github](https://github.com/erfanshayegani/Jailbreak-In-Pieces) | Encoder Level |
|[**FigStep: Jailbreaking Large Vision-language Models via Typographic Visual Prompts**](https://arxiv.org/abs/2311.05608) | Arxiv 2023 | 2023/11/09 | [Github](https://github.com/ThuCCSLab/FigStep) | Input Level |
|[**Jailbreaking Attack against Multimodal Large Language Model**](https://arxiv.org/abs/2402.02309) | Arxiv 2024 | 2024/02/04 | None| Model Level |
|[**Images are Achilles' Heel of Alignment: Exploiting Visual Vulnerabilities for Jailbreaking Multimodal Large Language Models**](https://arxiv.org/abs/2403.09792) | ECCV 2024 | 2024/05/14 | [Github](https://github.com/RUCAIBox/HADES)| Model Level |
|[**Visual-RolePlay: Universal Jailbreak Attack on MultiModal Large Language Models via Role-playing Image Character**](https://arxiv.org/abs/2405.20773) | Arxiv 2024 | 2024/05/25 | None | Input Level |
|[**Jailbreak Vision Language Models via Bi-Modal Adversarial Prompt**](https://arxiv.org/abs/2406.04031) | Arxiv 2024 | 2024/06/06 | [Github](https://github.com/NY1024/BAP-Jailbreak-Vision-Language-Models-via-Bi-Modal-Adversarial-Prompt) | Model Level |
|[**Image Hijacks: Adversarial Images can Control Generative Models at Runtime**](https://arxiv.org/abs/2309.00236) | Arxiv 2024 | 2024/09/01 | [Github](https://github.com/euanong/image-hijacks) | Model Level |
|[**Arondight: Red Teaming Large Vision Language Models with Auto-generated Multi-modal Jailbreak Prompts**](https://arxiv.org/abs/2407.15050) | ACM MM 2024 | 2024/07/21 | None | Input Level |
|[**Visual Adversarial Examples Jailbreak Aligned Large Language Models**](https://arxiv.org/abs/2306.13213) | AAAI 2024 | 2023/06/22 | [Github](https://github.com/Unispac/Visual-Adversarial-Examples-Jailbreak-Large-Language-Models) | Model Level |
|[**Are aligned neural networks adversarially aligned?**](https://arxiv.org/abs/2306.15447) | Arxiv 2023 | 2023/06/26 | None | Model Level |
|[**Voice Jailbreak Attacks Against GPT-4o**](https://arxiv.org/abs/2405.19103) | Arxiv 2024 | 2024/05/29 | [Github](https://github.com/TrustAIRLab/VoiceJailbreakAttack) | Input Level |
|[**Efficient LLM-Jailbreaking by Introducing Visual Modality**](https://arxiv.org/abs/2405.20015) | Arxiv 2024 | 2024/05/30 | None | Model Level |
|[**ImgTrojan: Jailbreaking Vision-Language Models with ONE Image**](https://arxiv.org/abs/2403.02910) | Arxiv 2024 | 2024/05/05 | [Github](https://github.com/xijia-tao/ImgTrojan) | Model Level |
|[**Jailbreaking GPT-4V via Self-Adversarial Attacks with System Prompts**](https://arxiv.org/abs/2311.09127) | Arxiv 2023 | 2023/11/15 | None | Input Level |
|[**White-box Multimodal Jailbreaks Against Large Vision-Language Models**](https://arxiv.org/abs/2405.17894) | Arxiv 2023 | 2024/05/28 | None | Model Level |
|[**From LLMs to MLLMs: Exploring the Landscape of Multimodal Jailbreaking**](https://arxiv.org/pdf/2406.14859v1) | Arxiv 2024 | 2024/06/21 | None | Encoder Level |
|[**Image-to-Text Logic Jailbreak: Your Imagination can Help You Do Anything**](https://arxiv.org/pdf/2407.02534) | Arxiv 2024 | 2024/07/01 | None | Input Level |
|[**Can Large Language Models Automatically Jailbreak GPT-4V?**](https://arxiv.org/pdf/2407.16686v2) | Arxiv 2024 | 2024/07/23 | None | Input Level |

## Jailbreak Attack of Multimodal Diffusion-based Models
|  Title  |   Venue  |   Date   |   Code   | Taxonomy |
|:--------|:--------:|:--------:|:--------:|:--------:|
|[**MMA-Diffusion: MultiModal Attack on Diffusion Models**](https://arxiv.org/abs/2311.17516) | CVPR 2024 | 2023/11/29 | [Github](https://github.com/cure-lab/MMA-Diffusion) | Encoder Level |
|[**Ring-A-Bell! How Reliable are Concept Removal Methods for Diffusion Models?**](https://arxiv.org/abs/2310.10012) | ICLR 2024 | 2023/10/16 | [Github]( https://github.com/chiayi-hsu/Ring-A-Bell) | Encoder Level |
|[**Jailbreaking Prompt Attack: A Controllable Adversarial Attack against Diffusion Models**](https://arxiv.org/abs/2404.02928) | Arxiv 2024 | 2024/08/02 | None | Encoder Level |
|[**To Generate or Not? Safety-Driven Unlearned Diffusion Models Are Still Easy To Generate Unsafe Images ... For Now**](https://arxiv.org/abs/2310.11868) | ECCV 2024 | 2023/07/07 | [Github](https://github.com/OPTML-Group/Diffusion-MU-Attack) | Model Level |
|[**Perception-guided Jailbreak against Text-to-Image Models**](https://arxiv.org/abs/2408.10848) | Arxiv 2024 | 2024/08/26 | None | Input Level |
|[**SneakyPrompt: Jailbreaking Text-to-image Generative Models**](https://arxiv.org/abs/2305.12082) | Symposium on Security and Privacy 2024 | 2023/11/10 | [Github](https://github.com/Yuchen413/text2image_safety) | Output Level |
|[**DiffZOO: A Purely Query-Based Black-Box Attack for Red-teaming Text-to-Image Generative Model via Zeroth Order Optimization**](https://arxiv.org/abs/2408.11071) | Arxiv 2024 | 2024/08/18 | None | Output Level |
|[**BSPA: Exploring Black-box Stealthy Prompt Attacks against Image Generators**](https://arxiv.org/abs/2402.15218) | Arxiv 2024 | 2024/02/23 | None | Encoder Level |
|[**Red-Teaming the Stable Diffusion Safety Filter**](https://arxiv.org/abs/2210.04610) | Arxiv 2022 | 2022/11/10 | None | Input Level |
|[**UPAM: Unified Prompt Attack in Text-to-Image Generation Models Against Both Textual Filters and Visual Checkers**](https://arxiv.org/abs/2405.11336) | ICML 2024 | 2024/05/18 | None | Input Level |
|[**Prompting4Debugging: Red-Teaming Text-to-Image Diffusion Models by Finding Problematic Prompts**](https://arxiv.org/abs/2309.06135) | ICML 2024 | 2024/06/08 | [Github](https://github.com/joycenerd/P4D) | Model Level |
|[**Divide-and-Conquer Attack: Harnessing the Power of LLM to Bypass Safety Filters of Text-to-Image Models**](https://arxiv.org/abs/2312.07130) | Arxiv 2024 | 2024/05/14 | [Github](https://github.com/researchcode001/Divide-and-Conquer-Attack) | Input Level |
|[**SurrogatePrompt: Bypassing the Safety Filter of Text-To-Image Models via Substitution**](https://arxiv.org/abs/2309.14122) | Arxiv 2024 | 2024/07/31 | [Github](https://github.com/researchcode001/Divide-and-Conquer-Attack) | Input Level |
|[**Automatic Jailbreaking of the Text-to-Image Generative AI Systems**](https://arxiv.org/abs/2405.16567) | Arxiv 2024 | 2024/05/28 | None | Input Level |
|[**Jailbreaking Text-to-Image Models with LLM-Based Agents**](https://arxiv.org/abs/2405.16567) | Arxiv 2024 | 2024/09/09 | None | Input Level |
|[**✳VA3: Virtually Assured Amplification Attack on Probabilistic Copyright Protection for Text-to-Image Generative Models**](https://arxiv.org/abs/2312.00057) | CVPR 2024 | 2024/08/02 | [Github](https://github.com/South7X/VA3) | Encoder Level |
|[**RT-Attack: Jailbreaking Text-to-Image Models via Random Token**](https://arxiv.org/abs/2408.13896) | Arxiv 2024 | 2024/08/27 | None | Encoder Level |


## Jailbreak Defense of Multimodal Diffusion-based Models
|  Title  |   Venue  |   Date   |   Code   | Taxonomy |
|:--------|:--------:|:--------:|:--------:|:--------:|
|[**EIUP: A Training-Free Approach to Erase Non-Compliant Concepts Conditioned on Implicit Unsafe Prompts**](https://arxiv.org/abs/2408.01014) | Arxiv 2024 | 2024/08/02 | None | Model Level |
|[**Direct Unlearning Optimization for Robust and Safe Text-to-Image Models**](https://arxiv.org/abs/2407.21035) | Arxiv 2024 | 2024/07/17 | None | Encoder Level |
|[**Reliable and Efficient Concept Erasure of Text-to-Image Diffusion Models**](https://arxiv.org/abs/2407.12383) | ECCV 2024 | 2024/07/17 | [Github](https://github.com/CharlesGong12/RECE) | Model Level |
|[**Pruning for Robust Concept Erasing in Diffusion Models**](https://arxiv.org/abs/2405.16534) | Arxiv 2024 | 2024/05/26 | None | Model Level |
|[**SafeGen: Mitigating Sexually Explicit Content Generation in Text-to-Image Models**](https://arxiv.org/abs/2404.06666) | ACM CCS 2024 | 2024/04/10 | [Github](https://github.com/LetterLiGo/SafeGen_CCS2024) | Model Level |
|[**GuardT2I: Defending Text-to-Image Models from Adversarial Prompts**](https://arxiv.org/abs/2403.01446) | Arxiv 2024 | 2024/03/03 | None | Input Level |
|[**Safe-CLIP: Removing NSFW Concepts from Vision-and-Language Models**](https://arxiv.org/abs/2403.01446) | ECCV 2024 | 2024/11/27 | [Github](https://github.com/aimagelab/safe-clip) | Encoder Level |
|[**Forget-Me-Not: Learning to Forget in Text-to-Image Diffusion Models**](https://arxiv.org/abs/2303.17591) | CVPR 2024 | 2023/05/30 | [Github](https://github.com/SHI-Labs/Forget-Me-Not) | Model Level |
|[**Latent Guard: a Safety Framework for Text-to-image Generation**](https://arxiv.org/abs/2404.08031) | ECCV 2024 | 2024/04/11 | [Github](https://github.com/rt219/LatentGuard) | Encoder Level |
|[**Safe Latent Diffusion: Mitigating Inappropriate Degeneration in Diffusion Models**](https://arxiv.org/abs/2211.05105) | CVPR 2023 | 2022/11/09 | [Github](https://github.com/ml-research/safe-latent-diffusion) | Model Level |
|[**Espresso: Robust Concept Filtering in Text-to-Image Models**](https://arxiv.org/abs/2404.19227) | Arxiv 2024 | 2024/04/30 | None | Output Level |
|[**Self-discovering interpretable diffusion latent directions for responsible text-to-image generation**](https://arxiv.org/abs/2311.17216) | CVPR 2024 | 2024/05/28 | [Github](https://github.com/hangligit/InterpretDiffusion) | Input Level |
|[**Implicit concept removal of diffusion models**](https://arxiv.org/abs/2310.05873) | Arxiv 2024 | 2024/10/08 | None | Input Level |
|[**Universal prompt optimizer for safe text-to-image generation**](https://arxiv.org/abs/2402.10882) | Arxiv 2024 | 2024/07/07 | None | Input Level |
|[**Defensive unlearning with adversarial training for robust concept erasure in diffusion models**](https://arxiv.org/abs/2405.15234) | Nips 2024 | 2024/10/09 | [Github](https://github.com/OPTML-Group/AdvUnlearn) | Encoder Level |
|[**Unlearning concepts in diffusion model via concept domain correction and concept preserving gradient**](https://arxiv.org/abs/2405.15304) | Arxiv 2024 | 2024/05/24 | None | Encoder Level |
|[**Erasediff: Erasing data influence in diffusion models**](https://arxiv.org/abs/2401.05779) | Arxiv 2024 | 2024/07/28 | None | Model Level |
|[**Salun: Empowering machine unlearning via gradient-based weight saliency in both image classification and generation**](https://arxiv.org/abs/2310.12508) | ICLR 2024 | 2024/04/04 | [Github](https://github.com/OPTML-Group/Unlearn-Saliency) | Model Level |
|[**Mace: Mass concept erasure in diffusion models**](https://arxiv.org/abs/2403.06135) | CVPR 2024 | 2024/05/10 | [Github](https://github.com/Shilin-LU/MACE) | Model Level |
|[**Unified concept editing in diffusion models**](https://arxiv.org/abs/2308.14761) | CVPR 2024 | 2023/08/25 | [Github](https://github.com/rohitgandikota/unified-concept-editing) | Model Level |
|[**Receler: Reliable concept erasing of text-to-image diffusion models via lightweight erasers**](https://arxiv.org/abs/2311.17717) | Arxiv 2024 | 2024/07/18 | None | Model Level |
|[**Dark miner: Defend against unsafe generation for text-to-image diffusion models**](https://arxiv.org/html/2409.17682) | Arxiv 2024 | 2024/09/26 | None | Model Level |
|[**Score forgetting distillation: A swift, data-free method for machine unlearning in diffusion models**](https://arxiv.org/abs/2409.11219) | Arxiv 2024 | 2024/08/08 | None | Model Level |
|[**Towards safe self-distillation of internet-scale text-to-image diffusion models**](https://arxiv.org/abs/2307.05977) | ICML 2023 | 2023/07/12 | [Github](https://github.com/nannullna/safe-diffusion) | Model Level |
|[**Erasing concepts from diffusion models**](https://arxiv.org/abs/2303.07345) | ICCV 2023 | 2023/06/21 | [Github](https://github.com/rohitgandikota/erasing) | Model Level |
|[**Conceptprune: Concept editing in diffusion models via skilled neuron pruning**](https://arxiv.org/abs/2405.19237) | ICCV 2023 | 2024/05/29 | [Github](https://github.com/ruchikachavhan/concept-prune) | Model Level |
|[**Localization and manipulation of immoral visual cues for safe text-to-image generation**](https://openaccess.thecvf.com/content/WACV2024/papers/Park_Localization_and_Manipulation_of_Immoral_Visual_Cues_for_Safe_Text-to-Image_WACV_2024_paper.pdf) | WACV 2024 | 2024 | None | Output Level |

## Jailbreak Defense of Multimodal LLM-based Models
|  Title  |   Venue  |   Date   |   Code   | Taxonomy |
|:--------|:--------:|:--------:|:--------:|:--------:|
|[**Adashield: Safeguarding multimodal large language models from structure-based attack via adaptive shield prompting**](https://arxiv.org/abs/2403.09513) | ECCV 2024 | 2024/05/14 | [Github](https://github.com/SaFoLab-WISC/AdaShield) | Input Level |
|[**Jailbreaking GPT-4V via Self-Adversarial Attacks with System Prompts**](https://arxiv.org/abs/2311.09127) | Arxiv 2024 | 2024/01/20 | None | Input Level |
|[**Sim-clip: Unsupervised siamese adversarial fine-tuning for robust and semantically-rich vision-language models**](https://arxiv.org/abs/2407.14971) | Arxiv 2024 | 2024/07/20 | None | Encoder Level |
|[**Securing Vision-Language Models with a Robust Encoder Against Jailbreak and Adversarial Attacks**](https://arxiv.org/abs/2409.07353) | Arxiv 2024 | 2024/09/11 | None | Encoder Level |
|[**Safety fine-tuning at (almost) no cost: A baseline for vision large language models**](https://arxiv.org/abs/2402.02207) | ICML 2024 | 2024/06/17 | [Github](https://github.com/ys-zong/VLGuard) | Model Level |
|[**Safety alignment for vision language models**](https://arxiv.org/abs/2405.13581) | Arxiv 2024 | 2024/05/22 | None | Model Level |
|[**Bathe: Defense against the jailbreak attack in multimodal large language models by treating harmful instruction as backdoor trigger**](https://arxiv.org/abs/2408.09093) | Arxiv 2024 | 2024/08/17 | None | Model Level |
|[**Cross-modal safety alignment: Is textual unlearning all you need?**](https://arxiv.org/abs/2406.02575) | Arxiv 2024 | 2024/05/27 | None | Model Level |
|[**Safety-tuned llamas: Lessons from improving the safety of large language models that follow instructions**](https://arxiv.org/abs/2309.07875) | ICLR 2024 | 2024/05/19 | [Github](https://github.com/vinid/safety-tuned-llamas) | Model Level |
|[**Mllm-protector: Ensuring mllm’s safety without hurting performance**](https://arxiv.org/abs/2401.02906) | Arxiv 2024 | 2024/06/17 | [Github](https://github.com/pipilurj/MLLM-protector) | Output Level |
|[**Information-theoretical principled trade-off between jailbreakability and stealthiness on vision language models**](https://arxiv.org/abs/2410.01438) | Arxiv 2024 | 2024/10/02 | None | Input Level |
|[**Defending jailbreak attack in vlms via cross-modality information detector**](https://arxiv.org/abs/2407.21659) | Arxiv 2024 | 2024/10/11 | [Github](https://github.com/pandragonxiii/cider) | Encoder Level |
|[**Inferaligner: Inference-time alignment for harmlessness through cross-model guidance**](https://arxiv.org/abs/2401.11206) | Arxiv 2024 | 2024/01/20 | [Github](https://github.com/Jihuai-wpy/InferAligner) | Encoder Level |
|[**Jailguard: A universal detection framework for llm prompt-based attacks**](https://arxiv.org/abs/2312.10766) | Arxiv 2024 | 2024/06/18 | None | Encoder Level |
