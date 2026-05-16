# HW2: Multimodal Fusion and Alignment

Notebook: [Open in Google Colab](https://colab.research.google.com/drive/1jU1agXi4Wbe-Gqx097r-G_dMeXlbVoFS?usp=sharing)

## Summary

This homework explores multimodal fusion, alignment, and contrastive learning. I first answered reading questions on “align before fuse” and the Platonic Representation Hypothesis, then implemented tensor operations, unimodal models, fusion models, and contrastive alignment experiments.

In the notebook, I trained image-only and audio-only AV-MNIST models, tested late fusion with MultiBench, and then implemented early fusion, late fusion, Tensor Fusion, and Low-Rank Tensor Fusion on my EPIC-KITCHENS-based dataset from HW1. I also trained a contrastive image-text alignment model using CLIP features and evaluated retrieval performance.

## Main Experiments

- PyTorch tensor and einsum practice
- AV-MNIST unimodal image/audio classification
- Late fusion with image and audio encoders
- EPIC-KITCHENS video-text fusion models
- Comparison of early fusion, late fusion, Tensor Fusion, and LMF
- Contrastive learning for image-text alignment

## Key Results

On my EPIC-KITCHENS subset, Tensor Fusion achieved the best validation accuracy, followed by Early Fusion. The contrastive model achieved high top-5 retrieval accuracy, but top-1 was harder because many sampled frames had near-duplicate captions.

## Takeaway

The main takeaway is that multimodal fusion can significantly improve performance when modalities provide complementary information, but it also increases memory, parameter count, and training cost. The contrastive learning section also showed why alignment before fusion is useful: even when exact retrieval fails, the model often retrieves semantically similar actions.
