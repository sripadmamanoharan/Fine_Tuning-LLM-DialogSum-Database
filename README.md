# Fine_Tuning-LLM-DialogSum-Database

# Dialogue Summarization using PEFT on DialogSum Dataset

This project focuses on summarizing open-domain conversations using the [DialogSum](https://aclanthology.org/2021.acl-long.563/) dataset. It compares the performance of a baseline model with a Parameter-Efficient Fine-Tuned (PEFT) transformer model.

---

##  Dataset

- **Name**: DialogSum
- **Size**: 13,460 dialogues + 100 for topic generation
- **Content**: Each dialogue is paired with a manually-written summary and topic.

---

##  Task

> Generate concise and accurate summaries of dialogues.

- Input: A multi-turn conversation
- Output: One-sentence summary in natural language

---

##  Approach

### 1. **Baseline Model**
- Uses standard sequence-to-sequence transformer without fine-tuning
- Result: Inaccurate and generic summaries

### 2. **PEFT Model (LoRA/Tuners)**
- Fine-tuned on DialogSum using a small adapter layer (efficient training)
- Uses Hugging Face's `PEFT` and `transformers` libraries
- Evaluation based on qualitative analysis

---

##  Sample Output

** Input Dialogue:**


** Human Summary:**
> #Person1# thinks #Person2# has chicken pox and warns #Person2# about the possible hazards but #Person2# thinks it will be fine.

** Baseline Output:**
> Person1 is scratching so much that he can't stand it anymore.

** PEFT Model Output:**
> #Person2# is scratching too much and feels lightheaded and weak. #Person1# thinks he has chicken pox.

---

## Training Summary

| Metric                | Value     |
|-----------------------|-----------|
| Epochs                | 5         |
| Global Steps          | 160       |
| Training Loss         | 3.54      |
| Training Runtime      | 155 sec   |
| Steps/Sec             | 1.03      |
| Samples/Sec           | 4.03      |

---

##  Key Takeaways

- PEFT allows efficient fine-tuning with fewer parameters.
- Model captures better context than the baseline.
- Human summaries remain the gold standard for quality evaluation.

---

##  Dependencies

- Python 3.8+
- Transformers
- PEFT
- Datasets (Hugging Face)
- Accelerate
- Wandb (optional)

Install with:
```bash
pip install transformers peft datasets accelerate wandb

Author
Sri Padmavathi Manoharan
Purdue University | MS in Computer and Information Science

