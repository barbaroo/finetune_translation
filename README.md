# finetune_translation
Fine-tuning of NMT and LLMs for English to Faroese translation

# Rethinking Low-Resource MT: The Surprising Effectiveness of Fine-Tuned Multilingual Models in the LLM Age

This repository accompanies the paper **"Rethinking Low-Resource MT: The Surprising Effectiveness of Fine-Tuned Multilingual Models in the LLM Age"**, providing the training configurations used for fine-tuning various models and experimenting with English-to-Faroese machine translation.

## Overview

This repository contains the configuration files used for:
1. Fine-tuning **GPT-SW3** for English-to-Faroese translation.
2. Fine-tuning **LLaMA 3.1** for English-to-Faroese translation.
3. Fine-tuning **NLLB-200** models with both human-annotated and LLM-generated synthetic parallel datasets.

The configuration files specify hyperparameters, dataset details, and other settings for training. 
---

## Configuration Files

### 1. `config_gptsw3.yaml`
- Used for fine-tuning the **GPT-SW3** model (1.3B and 6.7B versions).
- Includes settings for:
  - **Dataset**: Sprotin parallel corpus.
  - **Prompting**: Alpaca-style instruction-based prompts.
  - **LoRA fine-tuning**: Lightweight adaptation for causal language modeling.

### 2. `config_llama.yaml`
- Used for fine-tuning the **LLaMA 3.1** (8B version) model.
- Includes settings for:
  - **Tokenization**: Custom padding tokens.
  - **Dataset**: Sprotin parallel corpus.
  - **Training configuration**: Gradient accumulation and 8-bit precision training for resource efficiency.

### 3. `config_seq2seq.yaml`
- Used for fine-tuning the **NLLB-200** models (600M and 1.3B versions).
- Includes:
  - **Synthetic data integration**: Combining LLM-generated parallel sentences with the Sprotin corpus.
  - **Evaluation metrics**: SacreBLEU and ChrF++.
  - **Dataset splits**: FLORES-200 benchmark, Sprotin parallel corpus, and synthetic datasets.

---

## How to Use

1. Clone this repository:
   ```bash
   git clone https://github.com/your-repo-name
   cd your-repo-name

1. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
