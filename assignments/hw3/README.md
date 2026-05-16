# HW3: Vision-Language Models and LoRA Fine-Tuning

Notebook: [Open in Google Colab](https://colab.research.google.com/drive/1vkuFZGRi5iXERmac6Tt-rrRBxYucRF-x?usp=sharing)

## Summary

This homework explores Vision-Language Models, prompt engineering, and LoRA fine-tuning. I prepared an HD-EPIC image-question-answer dataset, ran baseline inference with Qwen2.5-VL-3B-Instruct, tested different prompt strategies, and fine-tuned the model with LoRA.

## What I Did

- Built a dataset from HD-EPIC egocentric cooking videos
- Extracted frames from narrated action segments
- Created train/test JSONL files with image, question, and answer fields
- Ran zero-shot inference on held-out images using Qwen2.5-VL
- Tested prompt variants for fine-grained object prediction
- Fine-tuned Qwen2.5-VL with LoRA on the custom dataset
- Compared pretrained and fine-tuned model outputs

## Key Results

Prompt engineering helped slightly. The best constrained-label prompt improved full test accuracy from `27/174` to `34/174`. LoRA fine-tuning was less successful: on the four held-out examples, the model collapsed toward predicting `cupboard`, suggesting overfitting or unstable adaptation on a small dataset.

## Takeaway

The main lesson was that VLM performance depends heavily on the match between the visual input, the prompt, and the dataset label space. The pretrained model often gave semantically plausible answers, but they did not always match the exact noun labels. Fine-tuning also requires careful dataset design, label balance, and evaluation to avoid biased or collapsed outputs.
