---
name: draft-engineering-log
description: Review the conversation with the user to create a daily engineering log entry summarizing work done, tasks completed/started/abandoned, and technical details.
license: AGPL-3.0-or-later
user-invocable: true
---

# Draft Engineering Log Skill

This skill is designed to help the user maintain a professional engineering logbook by synthesizing the day's interactions into a structured summary. It transforms the conversational history of the current session into a formal record from the developer's perspective.

## Intent
To capture technical decisions, obstacles overcome, and progress made during a development session, ensuring that "institutional knowledge" is documented in a human-readable log rather than buried in chat transcripts.

## Voice and Perspective
The log must be written from the **Developer's perspective** (the User):
- Use "**I**" to refer to the user.
- Refer to the AI as "**pi**" or "**the assistant**".

## Standard Workflow

### 1. Session Review
Analyze the conversation transcripts from **today only** (unless otherwise specified by the user). Identify:
- All projects worked on.
- Specific tasks undertaken within each project.
- The status of each task (Completed, Started but still open, or Abandoned/Reverted).
- The technical narrative: prompts used, models leveraged, specific bugs found, and solutions implemented.

### 2. Log Construction
Structure the log as follows:
- **H1**: The Date (`YYYY-MM-DD`).
- **H2**: Project Name(s).
- **H3**: Task Name.
    - A narrative summary of the work.
    - Mention specific prompts or AI models if they contributed significantly to the solution.
    - Detail problems encountered and how they were resolved (including failed attempts).

### 3. File Generation
Create a markdown file named `engineering-log-YYYY-mm-DD.md` in the project root or a designated logs directory.

## Output Format Example
# 2026-07-07

## Project: onthewing

### Serving static resources
Fixed a bug where the server was reporting HTTP 502 errors with too many parallel requests for static resources. I prompted pi version x.y and the google/gemma-4-31b model to [your initial prompt], and it found that the default HTTP adapter has one working thread and the accessors to change the number of working threads are unimplemented.

Solution: Added an nginx sidecar repo to the app pod, that serves requests for the static resources itself and passes other requests through to the app.
Problems encountered: It took three attempts for the assistant to generate the YAML for the sidecar correctly, before "skaffold dev" started cleanly. The reasons were [errors from the conversation].

## Project: core-api

### Database Migration
Started implementing the migration to PostgreSQL. I worked with pi to define the schema for the user profiles table.
Status: Started but still open. Need to verify index performance on the `email` column.
