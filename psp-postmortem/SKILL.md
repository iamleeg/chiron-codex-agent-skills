---
name: psp-postmortem
description: Carry out a project postmortem on software you created following the Personal Software Process.
license: AGPL-3.0-or-later
user-invocable: true
disable-model-invocation: true
---
# Personal Software Process postmortem skill

## Purpose
Completes a project summary about the work you performed while implementing some software, and provides reflections on how you could improve your work.

## Inputs Required
- High-quality software that you built
- An incomplete Project Plan Summary File
- Template Project Plan Summary File (see [project-plan.md](assets/project-plan.md) relative to this skill folder)
- Time Recording Log
- Defect Recording Log
- Session transcript of your chat with the user

## Outputs Produced
- A complete Project Plan Summary File
- A complete Time Recording Log
- A complete Defect Recording Log
- A complete Size Recording Log
- Reflections on how to improve your work

## Standard Workflow

### 1. Ensure Time Recording Log is complete

Make sure that each of the entries in the Time Recording Log is complete and consistent. If there are any problems, use your best estimates to complete the log. Add an entry now using the psp-record-time skill to log when you start your postmortem.

### 2. Ensure Defect Recording Log is complete

Make sure that each of the entries in the Defect Recording Log indicates that it was fixed (it's OK if the user made a note saying they would accept the defect). If there are any open defects, you _MUST_ abandon the postmortem at this stage and tell the agent to go back to development and fix the defects. Ensure that the Defect Recording Log includes anything mentioned in the chat transcript: for example, if you failed to run a tool correctly, or built the software and got an error, or had to test multiple times because the tests kept failing, those need to be recorded in the Defect Recording Log.

### 3. Record the Size of Your Changes

Use the 'psp-size' skill to complete a Size Recording Log.

### 4. Complete the Project Plan Summary

Fill out the remaining fields in the project plan summary document, particularly:

- Language: if this is empty, record which implementation language you used.
- Time in Phase: use the Time Recording Log to complete the actual values and percentages in this table.
- Defects Injected: use the Defect Recording Log to complete the actual values and percentages in this table.
- Defects Removed: use the Defect Recording Log to complete the actual values and percentages in this table.

### 5. Reflect on Your Work

Produce a brief document that describes your experiences completing this project, and opportunities for improvement. Use the project time and defect reports as input to this reflection. Did you inject the same kind of defect multiple times, and could a change in your instructions or your process help to avoid that defect? Did you discover defects much later than they were injected, so earlier verification work could have caught them sooner? Did particular phases cost you more time than others, or were your estimates particularly inaccurate for some phases? Create a markdown file that outlines the most important issues and gives the user specific, actionable information about how to address them.

### 6. Make Memories

Use 'bd remember' to store important facts or actionable process improvements in your memory.

### 7. Report Back to the User

Tell the user where to find your Project Plan Summary and reflections document.

## Rules

### Purpose

Use this skill provide the user with ideas on how to improve your prompts, skills, subagents, and their interactions with you, and the quantitative data to support those suggestions. **IMPORTANT:** if you find any defects in the software are unaddressed, you _MUST_ abandon the postmortem and tell the agent to continue in the development phase until they address the defects, then the agent may ask the user again to proceed to postmortem.