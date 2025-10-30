# Measuring How Tutors Think : A Meta Reasoning Evaluation for LLMs
This repository showcases my research and codebase for evaluating and advancing the meta-reasoning capabilities of AI tutors powered by large language models (LLMs)—specifically using DeBERTa-v3 with efficient LoRA adapters. The project centers around two vital educational challenges inspired by the BEA 2025 Shared Task:

Track-1: Mistake Identification — Can the AI pinpoint student mistakes in multi-turn math dialogues?

Track-2: Providing Guidance — Can the AI offer meaningful feedback and hints, not just answers?

The project leverages public MathDial and Bridge datasets and is designed with model efficiency and interpretability in mind.

## 🏆 Results At-a-Glance

| Track   | Macro F1 (Val) | Accuracy (Val) | Innovations                         |
| ------- | -------------- | -------------- | ----------------------------------- |
| Track-1 | 0.816          | 0.853          | LoRA-tuned DeBERTa, class balancing |
| Track-2 | 0.92/0.89*     | —              | Hierarchical + feature fusion       |

* Guidance is staged — see notebook for details.
  
Compared to earlier baselines (simple voting/majority classifiers, vanilla RoBERTa):

Macro F1 is boosted by 15–30% for challenging “No” and “To some extent” classes.

Parameter-efficient fine-tuning enables training on moderate hardware and ensures reproducibility.

Feature fusion and ablation clarify model behavior, supporting both performance and explainability.

## ⚙️ Key Features

DeBERTa-v3 Backbone: Top-tier transformer for nuanced dialogue understanding

LoRA Fine-tuning: Adapts to tutoring with less than 1% of weights updated

Balanced Training: Combats real-world class imbalance with reweighting and sampling

Input Engineering: Segregated [history|student|tutor] structure

Hierarchical Architecture: Multi-stage classifier for open-ended guidance tracks

Linguistic Feature Fusion: Boosts performance on partial/ambiguous cases using surface cues

Clear Validation: Macro F1 aligns with the official BEA 2025 evaluation

## 📈 Sample Outputs

Macro F1 (Mistake ID): 0.816 — matches scores of top BEA 2025 systems

Guidance Staged F1: 0.92 (Stage A), 0.89 (Stage B) — robust even on nuanced responses

Check out plots, confusion matrices, and more inside the notebooks!

## 🧑‍💻 Usage

Clone this repo and open Track-1.ipynb or Track-2.ipynb in Colab/Jupyter.

Place trainset.json/testset.json in the root.

Run all cells—models train, predict, and auto-generate submission results.

Detailed logs and outputs appear in line; see the output/ directory if created.

## 📚 References

Kochmar et al., “Findings of the BEA 2025 Shared Task on Pedagogical Ability Assessment of AI-Powered Tutors”, 2025.

Tack & Piech, “The AI Teacher Test: Measuring the Pedagogical Ability of Blender and GPT-3”, EDM 2022.

Macina et al., “MathDial: A Dialogue Tutoring Dataset with Rich Pedagogical Properties”, EMNLP Findings 2023.

He et al., “DeBERTa: Decoding-Enhanced BERT with Disentangled Attention”, ICLR 2021.

Hu et al., “LoRA: Low-Rank Adaptation of Large Language Models”, arXiv:2106.09685.

## ⭐ Acknowledgements

This work would not be possible without the guidance of Dr. Tameem Ahmed and the data/support of the BEA and IndoML organizers.

Feel free to star, fork, or contact for collaboration!
