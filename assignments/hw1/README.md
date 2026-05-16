# HW1: Multimodal Dataset Preprocessing

Notebook: [Open in Google Colab](https://colab.research.google.com/drive/1rswDZkttnKmH-RFOqx47TnUsK6IOxjdM?usp=sharing)

## Summary

This homework focuses on preprocessing multimodal data for later model training. I explored datasets for next-action / intention prediction and used EPIC-KITCHENS because it provides egocentric video, segmentation masks, and narration/action annotations.

In the notebook, I selected a small subset of EPIC-KITCHENS videos, extracted RGB frames, linked videos with masks and narrations, created frame-level current-action and next-action labels, visualized dataset/input distributions, and implemented evaluation metrics such as top-k accuracy, macro-F1, and verb-noun pair accuracy.

## Modalities

- RGB video frames
- Segmentation masks
- Text narrations / action labels

## Takeaway

The main challenge was aligning sampled frames with narration timestamps and mask annotations. I originally considered Assembly101, but switched to EPIC-KITCHENS because the available sample data did not include usable labels.
