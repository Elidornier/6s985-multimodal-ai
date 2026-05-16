# HW4: GRPO for Vision-Language Models

Notebook: [Open in Google Colab](https://colab.research.google.com/drive/1bg4oKUU6MOJiDxUvojnT2ILoxoTmTl96?usp=sharing)

## Summary

This homework explores reinforcement learning for Vision-Language Models using Group Relative Policy Optimization (GRPO). I implemented the core GRPO advantage computation, reward functions, dataset formatting, GRPO training, and post-training evaluation on my HD-EPIC image-question-answer dataset.

## What I Did

- Verified the A100 GPU environment
- Reused the HD-EPIC dataset from HW3 with 862 image-QA samples
- Implemented group-relative advantage normalization for GRPO
- Defined accuracy and answer-format reward functions
- Built a GRPO-compatible Hugging Face dataset
- Trained Qwen3-VL-2B-Instruct with GRPO and LoRA
- Evaluated the trained model on held-out examples

## Key Results

The GRPO-trained model followed the required `Answer:` format consistently. On four held-out examples, it achieved 50% accuracy and 100% format compliance. Compared with HW3 SFT/LoRA, GRPO improved answer formatting and sometimes produced more detailed reasoning, but the reward signal was sparse and unstable.

## Takeaway

The main lesson was that GRPO is useful for optimizing output format and reward-based behavior, but it can be harder to stabilize than supervised fine-tuning. In this dataset, SFT/LoRA was more stable overall, while GRPO was better at enforcing the desired response structure.
