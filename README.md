# LLM Fine-Tuning for Financial Question Answering

## Module
Generative AI and Reinforcement Learning (7043SCN)  
Coventry University  

## Project Overview
This project investigates domain adaptation of a Large Language Model (LLM) for Financial Question Answering using the FIQA dataset.

A comparative study was conducted between:

- Pre-trained DistilGPT2 (Baseline)
- LoRA-based Parameter-Efficient Fine-Tuning

The objective was to evaluate whether parameter-efficient fine-tuning improves performance under hardware constraints.

---

## Model Details

Base Model: DistilGPT2  
Architecture: Decoder-only Transformer  
Parameters: ~82M  
Fine-Tuning Method: LoRA (Low-Rank Adaptation)

Trainable Parameters with LoRA: 0.18%

---

## Dataset

Dataset: FIQA (Financial Question Answering)  
Source: Hugging Face - ExplodingGradients/fiqa  

Dataset split:
- Training subset: 1000 samples
- Validation subset: 200 samples
- Test subset: Used for evaluation

---

## Hardware Used

Experiments were conducted using:

- Google Colab
- NVIDIA Tesla T4 GPU
- 15GB VRAM

Full fine-tuning of larger LLMs was not feasible due to memory limitations.

---

## Training Configuration

- Batch size: 4
- Epochs: 3
- Learning rate: 1e-4
- LoRA rank (r): 8
- LoRA alpha: 16
- LoRA dropout: 0.1

---

## Results

| Model | Method | F1 Score |
|-------|--------|----------|
| DistilGPT2 | Baseline | 0.1189 |
| DistilGPT2 | LoRA | 0.0488 |

Under limited data conditions, LoRA did not outperform the pretrained baseline.

---

## Key Observations

- Pretrained baseline retained general financial knowledge.
- LoRA significantly reduced trainable parameters.
- Performance was sensitive to dataset size and training duration.
- Small-scale adaptation may require larger datasets to outperform baseline.

---

## How to Run

1. Install dependencies:
   pip install transformers datasets peft accelerate evaluate

2. Run the notebook:
   Clean_Task1_LLM_FineTuning.ipynb

---

## Ethical Considerations

Financial AI systems must ensure:
- Reliability of generated advice
- Avoidance of hallucinated financial recommendations
- Bias mitigation
- Responsible deployment

---

## Author

[Your Full Name]  
Coventry University  
