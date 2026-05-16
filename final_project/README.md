# Final Project: Modeling User Preference for Personalized Video Question Answering in Egocentric Video

Report: `Modeling_User_Preference_for_Personalized_Video_Question_Answering_in_Egocentric_Video.pdf`  
Presentation: [Open Google Slides](https://docs.google.com/presentation/d/1q-BsYuH3nhkbrrsucLD6vgpZPfHK28GxvAfwU0jdQv0/edit?usp=sharing)

## Summary

This project studies whether user preference information can improve fine-grained why-recognition in egocentric video question answering. In household cooking videos, the same visible action can have different explanations depending on a person's habits, such as cleanup style, tool choice, workflow order, measurement routine, or workspace organization.

We evaluate preference-conditioned prompting on the HD-EPIC fine-grained why-recognition VQA task using Qwen3-VL-4B. The core question is whether participant-specific behavioral profiles help the model answer why a person performed an action.

## Research Question

Can user-level behavioral preference profiles improve personalized video question answering for egocentric why-recognition?

## Method

We compare several ways of constructing and injecting participant preference profiles:

- No-preference baseline
- LLM-generated numbered preference ratings
- LLM-generated paragraph summaries
- LLM-extracted past-behavior memories
- Semi-manual hand-labeled profiles
- Randomized-profile controls
- Action-conditioned gated preference prompting
- Reasoning-output prompt variants

The gated method uses the action verb to decide whether the model should rely mostly on visual evidence, mostly on preference evidence, or a balanced combination.

## Dataset and Model

- Dataset: HD-EPIC fine-grained why-recognition VQA
- Evaluation size: 500 multiple-choice questions
- Participants: 9
- Input clip: 32-second context window, sampled at 1 FPS
- Model: Qwen3-VL-4B
- Metric: exact-match multiple-choice accuracy

## Key Results

| Method | Accuracy |
|---|---:|
| Baseline | 55.0% |
| LLM numbered ranking | 51.6% |
| LLM paragraph summary | 50.4% |
| LLM past-behavior memory | 54.2% |
| Hand-labeled profile | 56.6% |
| Random hand-labeled profile | 53.4% |
| Hand-labeled profile + gate | 58.6% |
| Random hand-labeled profile + gate | 53.4% |

The best result comes from hand-labeled profiles with action-conditioned gating. This improves the baseline from 55.0% to 58.6%.

## Main Takeaway

Preference information is useful only when it is concrete, participant-specific, and selectively applied. Naively adding LLM-generated preference profiles often hurts performance and behaves similarly to randomized-profile controls. Hand-labeled profiles help modestly, and action-conditioned gating helps further by reducing cases where preference overwhelms visual evidence.

## Files

- `README.md`: final project overview
- `report/`: final project report
- `presentation/`: final presentation slides or link
- `code/`: evaluation, prompting, and analysis code
- `results/`: result tables, figures, and error analysis
- `assets/`: pipeline diagrams and qualitative examples

## Future Work

Future directions include learning preference embeddings instead of using text prompts, training a relevance gate instead of hand-designing one, using contrastive learning with true versus randomized profiles, and improving long-context profile extraction with denser video sampling and uncertainty estimates.
