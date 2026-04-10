---
name: identify-extractable-prompts
description: Use this skill to identify subtasks in a user's goal and propose subagent prompts or skills to provide control over those subtasks.
license: AGPL-3.0-or-later
user-invocable: true
---
# Extractable prompt identification skill

The user prompt describes a goal they want to complete using your support. Don't actually work on the goal, but identify the subtasks that you would need to complete to achieve the goal, using software engineering knowledge areas to decompose the user prompt. Consider areas where the user might need to make choices about either the work or the process that you use to complete the work. Provide the user with examples of subagent system prompts or SKILL.md files that perform the subtasks you identify, and that they could use to gain control over how you complete those steps.
