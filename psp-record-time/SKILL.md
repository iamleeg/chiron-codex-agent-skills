---
name: psp-record-time
description: Record time spent in different development activities
license: AGPL-3.0-or-later
user-invocable: false
disable-model-invocation: false
---
# Personal Software Process time-recording skill

## Purpose
Tracks the time spent on development activities in a standard form. Record the time you start an activity, the time you finish, any time you were interrupted (for example, waiting for the user to answer a question), the total time spent on the activity, and optional comments.

## Inputs Required
- Project name
- Time Recording Log file (optional; the first time you use this skill you might need to create a new log from the template)
- Time Recording Log template (see [time-template.md](assets/time-template.md) relative to this skill folder)
- The time (use [time.sh](scripts/time.sh) relative to this skill folder, via the 'bash' tool)
- Activity undertaken

## Outputs Produced
- Time spent added to the Time Recording Log
- Comments on noteworthy contributions to the time spent, if relevant.

## Standard Workflow

### 1. Generate new log file

You only need to do this the first time you invoke this skill on a project. Read the [time-template.md](assets/time-template.md) file, fill out the header details, and save it as a new file in the `psp` folder in your project (you might need to create that folder). This new file is now your Time Recording Log. Here's what the header fields mean:

- Name: Your name
- Date: Date when you start the project (use [time.sh](scripts/time.sh))
- Program: The project name
- Language: The implementation language you use (if the problem statement doesn't specify a language and there isn't any existing code to help identify the language, leave this blank and fill it in later when you choose a language).

### 2. Record activity start

Create a new row in the Time Recording Log's table, using the fields in the table in the template file.
Fill out the following fields:

- Project: The project name
- Phase: The project phase, for example "Planning", "Design", "Development", or "Test"
- Start Date and Time: The current time (use [time.sh](scripts/time.sh))

### 3. (Optional) Record interruptions

When you're interrupted, for example to ask permission to use a tool or to ask the user a question, track the time when the interruption starts and the time when the interruption finishes. Record these times in the "Interruption Time" field in the table, adding to any existing value.

### 4. Record activity end

When you complete an activity, fill out the following fields in the table:

- Stop Date and Time: The current time
- Delta Time: The total time spent on the task _excluding interruption time_ (so calculate end time minus start time minus interruption time)
- Comments: Any notes on what made the work particularly slow, or particularly fast. These help with your post-mortem later.

## Rules

### Purpose
Use this skill to record the time you spend on each project activity. These data are used to complete the Project Plan Summary. Keep separate logs for each program.

### General
Record all of the time you spend on the project, and be as accurate as possible. If you forget to record the time, use your best estimate and indicate that you estimated in the Comments field.
