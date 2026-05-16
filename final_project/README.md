# Preference-Aware Why Recognition in Egocentric Cooking Videos

## Research question

How can multimodal models recognize why a person performs an action in egocentric cooking videos when the explanation depends on user preferences, goals, or constraints?

## Motivation

Egocentric cooking videos capture actions from the viewpoint of the person acting. In this setting, the same visible action can have different reasons depending on hidden context such as dietary preferences, taste, safety concerns, timing, or task goals. This project investigates whether preference-aware prompting and evaluation can improve why-recognition beyond surface-level action descriptions.

## Method overview

The project studies multimodal why-recognition using video observations, natural-language preference context, and structured prompting. The core comparison is between baseline multimodal inference and variants that explicitly incorporate preference information.

## Pipeline

1. Select egocentric cooking video clips and define why-recognition examples.
2. Prepare preference contexts that may explain actions in the clips.
3. Run baseline multimodal model inference.
4. Run preference-aware prompting variants.
5. Evaluate outputs against expected explanations.
6. Analyze errors by action type, preference type, and failure mode.

## Experiments

- Baseline Qwen3-VL run.
- Preference prompting.
- Gated preference prompting.
- Randomized preference control.
- Error analysis across prompt variants.

## Results

Results will be collected in `results/`.

## Error analysis

The error analysis will track cases where the model:

- Describes what happened instead of why it happened.
- Ignores relevant preference context.
- Overuses preference context when it is irrelevant.
- Hallucinates motivations not supported by the clip or prompt.
- Produces vague explanations that are hard to evaluate.

## Future work

- Expand the evaluation set across more cooking tasks and preference categories.
- Compare additional multimodal models and prompting strategies.
- Add human evaluation for explanation quality.
- Explore automatic metrics for why-recognition consistency.

## My contributions

- Define the preference-aware why-recognition task.
- Build and organize the project pipeline.
- Design prompting variants and controls.
- Run experiments and analyze model outputs.
- Prepare the final report and supporting materials.

## Reproducibility

Code will be organized under `code/`. Results, figures, and error analysis notes will be stored under `results/`. The final report will document dataset choices, prompts, model settings, evaluation criteria, and major findings.
