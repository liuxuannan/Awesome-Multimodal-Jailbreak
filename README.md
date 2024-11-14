
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
    - [📑Any-to-Text (LLM Backbone)](#Any-to-Text-LLM-Backbone)
    - [📖Any-to-Vision (Diffusion Backbone)](#Any-to-Vision-Diffusion-Backbone)
    - [📰Any-to-Any (Unified Backbone)](#Any-to-Any-Unified-Backbone)
  - [😈Jailbreak Attack](#Jailbreak-Attack)
    - [📖Attack-Intro](#Attack-Intro)
    - [📑Papers](#Papers)
  - [🛡️Jailbreak Defense](#️jailbreak-defense)
    - [📖Defense-Intro](#Defense-Intro)
    - [📑Papers](#Papers)
  - [💯Resources](#Resources)
    - [⭐️Datasets](#datasets)
      - [Used to Any-to-Text Models](#Used-to-Any-to-Text-Models)
      - [Used to Any-to-Vision Models](#Used-to-Any-to-Vision-Models)
    - [📚Detectors](#detectors)
      - [Used to Any-to-Text Models](#Used-to-Any-to-Text-Models)
      - [Used to Any-to-Text Models](#Used-to-Any-to-Vision-Models)



## 🔥Multimodal Generative Models

**Below are tables of model short name and representative generative models used for jailbreak. For input/output modalities, I: Image, T: Text, V: Video, A: Audio.**

### 📑Any-to-Text (LLM Backbone)
|  Short Name  |   Modality  |   Representative Model   |  
|:--------|:--------:|:--------:|
| IT2T | I + T -> T |[LLaVA](https://arxiv.org/abs/2304.08485), [MiniGPT4](https://arxiv.org/abs/2304.10592), [InstructBLIP](https://arxiv.org/abs/2305.06500) |
| VT2T | V + T -> T |[Video-LLaVA](https://arxiv.org/abs/2311.10122), [Video-LLaMA](https://arxiv.org/abs/2306.02858) |
| AT2T | A + T -> T |[Audio Flamingo](https://arxiv.org/abs/2402.01831), [Audiopalm](https://arxiv.org/abs/2306.12925) |

### 📖Any-to-Vision (Diffusion Backbone)
|  Short Name  |   Modality  |   Representative Model   |  
|:--------|:--------:|:--------:|
| T2T | T -> I |[Stable Diffusion](https://arxiv.org/abs/2112.10752), [Midjourney](https://www.midjourney.com/), [DALLE](https://platform.openai.com/docs/guides/moderation/overview) |
| IT2I | I + T -> I |[DreamBooth](https://arxiv.org/abs/2208.12242), [InstructP2P](https://arxiv.org/abs/2306.07154) |
| T2V | T -> V |[Open-Sora](https://github.com/hpcaitech/Open-Sora), [Stable Video Diffusion](https://arxiv.org/abs/2311.15127) |
| IT2V | I + T -> V |[VideoPoet](https://arxiv.org/abs/2312.14125), [CogVideoX](https://arxiv.org/abs/2408.06072) |

### 📰Any-to-Any (Unified Backbone)
|  Short Name  |   Modality  |   Representative Model   |  
|:--------|:--------:|:--------:|
| IT2IT | I + T -> I + T |[Next-GPT](https://arxiv.org/abs/2309.05519), [Chameleon](https://arxiv.org/abs/2304.09842) |
| A2A | A -> A |[GPT-4o](https://openai.com/index/gpt-4o-system-card/) |


## 😈JailBreak Attack

**In this part, we focus on discussing different advanced jailbreak attacks against multimodal models. We categorize attack methods into black-box, gray-box, and white-box attacks. in a black-box setting where the model is inaccessible to the attacker, the attack is limited to surface-level interactions, focusing solely on the model’s input and/or output. Regarding gray-box and white-box attacks, we consider model-level attacks, including attacks at both the encoder and generator.**

### 📖Attack-Intro
<img src="https://github.com/liuxuannan/Awesome-Multimodal-Jailbreak/blob/main/pic/jailbreak_attack_A.png" alt="jailbreak_attack_black_box" />

**As shown in Fig. A.1, attackers are compelled to develop more sophisticated input templates across prompt engineering, image engineering, and role-ploy techniques. These techniques can bypass the model’s safeguards, making the models more susceptible to executing prohibited instructions.** <br>
**As shown in Fig. A.2, attackers focus on querying outputs across multiple input variants. Driven by specific adversarial goals, attackers employ estimation-based and search-based attack techniques to iteratively refine these input variants.**

<img src="https://github.com/liuxuannan/Awesome-Multimodal-Jailbreak/blob/main/pic/jailbreal_attack_B.png" alt="jailbreak_attack_white_and_gray_box" />

**As shown in Fig. B.1, attackers are restricted to accessing only the encoders to provoke harmful responses. In this case, attackers typically seek to maximize cosine similarity within the latent space, ensuring the adversarial input retains similar semantics to the target malicious content while still being classified as safe.** <br>
**As shown in Fig. B.2, attackers have unrestricted access to the generative model’s architecture and checkpoint, enabling attackers to conduct thorough investigations and manipulations, thus enabling sophisticated attacks.**



### 📑Papers
All the papers related to jailbreak attacks can be found in [Jailbreak Attack](https://github.com/liuxuannan/Awesome-Multimodal-Jailbreak/blob/main/Jailbreak%20Attack.md).


## 🛡️Jailbreak Defense

### 📖Defense-Intro

<img src="https://github.com/liuxuannan/Awesome-Multimodal-Jailbreak/blob/main/pic/jailbreak_defense_all_00.png" alt="jailbreak_transformative_defense" />

**In order to cope with jailbreak attacks and improve the security of multimodal foundation models, existing work makes efforts in both Transformative defense and Discriminative defense.**


### 📑Papers

All the papers related to jailbreak attacks can be found in [Jailbreak Defense](https://github.com/liuxuannan/Awesome-Multimodal-Jailbreak/blob/main/Jailbreak%20Defense.md).


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
<img src="https://github.com/liuxuannan/Awesome-Multimodal-Jailbreak/blob/main/pic/jailbreak_evaluation_00.png" alt="jailbreak_evaluation" width="600" />

**Detector-based approaches utilize pre-trained classifiers to automatically detect and identify harmful content within generated outputs. These classifiers are trained on large, annotated datasets that cover a range of unsafe categories, such as toxicity, violence, or explicit material. By leveraging these pre-trained models, detector-based methods can efficiently flag inappropriate content.**

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



