# natural-language-processing

# LoRA-Based Code Generation Fine-Tuning Project

This repository contains a Natural Language Processing project focused on improving code generation performance using **LoRA (Low-Rank Adaptation)** fine-tuning on a pretrained large language model.

---

##  Project Objective

The main goal of this project is to analyze how instruction-based fine-tuning with different dataset characteristics affects code generation performance.  
Two separate LoRA fine-tuned models are trained and compared against a base model using a standardized benchmark.

---

##  Models

- **Base Model:** Qwen2.5-Coder-1.5B-Instruct  
- **Deep Instruction Model:** Fine-tuned on CodeGen-Deep-5K  
- **Diverse Instruction Model:** Fine-tuned on CodeGen-Diverse-5K  

All models share the same architecture and training configuration to ensure a fair comparison.

---

##  Datasets

### Training Datasets
- **CodeGen-Deep-5K**  
- **CodeGen-Diverse-5K**

These datasets are used exclusively for LoRA fine-tuning.

### Evaluation Dataset
- **LiveCodeBench (AtCoder Easy)**

LiveCodeBench is used only for evaluation and is not included during training, ensuring an unbiased assessment of generalization.

---

##  Training Setup

- Fine-tuning method: **LoRA**
- Quantization: **8-bit**
- Precision: **FP16**
- Context length: 512
- Learning rate: 2e-4
- Gradient accumulation: 16
- Evaluation every 100 steps
- Early stopping enabled

---

##  Evaluation Method

Models are evaluated using the **Pass@1** metric on **41 AtCoder Easy problems** via the LiveCodeBench framework.

Evaluation includes:
- Aggregate Pass@1 scores
- Checkpoint-level comparisons
- Per-problem Pass/Fail analysis
- Qualitative case studies where models behave differently on the same problem

---

##  Key Results

- **Base Model:** 19.51% Pass@1 (8/41)
- **Deep Instruction Model:** 24.39% Pass@1 (10/41)
- **Diverse Instruction Model:** 29.27% Pass@1 (12/41)

Results show that LoRA fine-tuning improves code generation performance, with dataset diversity playing a significant role in generalization.

---

##  Repository Structure
```
.
├── training/
│   ├── deep_lora_training.ipynb
│   └── diverse_lora_training.ipynb
│
├── evaluation/
│   ├── livecodebench_results/
│   └── pass_fail_tables/
│
├── figures/
│   ├── loss_curves/
│   └── benchmark_comparisons/
│
├── report/
│   └── final_report.pdf
│
└── README.md

```
---

##  Notes

- All experiments were conducted in a Google Colab environment.
- Library versions and commands used for evaluation are documented in the final report.
- Detailed per-problem results and qualitative analyses are provided in the appendix section of the report.

---

##  Report

The complete project report, including methodology, results, figures, and analysis, is available in the `report/` directory.

---

