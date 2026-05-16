# HW5: AI Agents in the Wild

Notebook: [Open in Google Colab](https://colab.research.google.com/drive/1BtxFDC-xSkKOqo__r8Xkti1difQ5M9X6?usp=sharing)

## Summary

This homework explores goal-directed AI agents through a weekly planning agent called **WeekWeaver**. The agent takes calendar events, tasks, deadlines, priorities, and user constraints, then tries to produce a feasible weekly schedule through multi-step planning and tool use.

## What I Did

- Defined WeekWeaver as a sequential decision-making agent
- Built an offline evaluation set with 11 planning tasks
- Included normal, edge, ambiguous, adversarial, and revision cases
- Designed metrics for schedule correctness, tool/process correctness, and operational quality
- Implemented a baseline agent using `smolagents` with web search and webpage visit tools
- Built custom scheduling tools:
  - `find_free_blocks`
  - `schedule_tasks`
  - `check_schedule_validity`
- Compared baseline and custom-tool agent performance
- Reflected on failures caused by weak tool calling, invalid JSON formatting, and lack of explicit state control

## Key Results

The baseline agent completed runs but often produced plausible-looking schedules without reliably validating deadlines, durations, or conflicts. Manual grading gave the baseline a success rate of `1/5`. The custom-tool version improved the structure of the planning process by using explicit scheduling and validation tools, but it also exposed a major agent-design issue: the model often struggled to call tools with valid JSON arguments.

## Takeaway

The main lesson was that agents need more than fluent reasoning. For structured tasks like calendar planning, reliability depends on tool design, state representation, validation, and observability. Custom tools made the planning process more grounded, but the system still needed better tool-call robustness and stronger control over the agent loop.
