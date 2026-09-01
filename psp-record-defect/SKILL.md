---
name: psp-record-defect
description: Record defects spent in different development activities
license: AGPL-3.0-or-later
user-invocable: false
disable-model-invocation: false
---
# Personal Software Process defect-recording skill

## Purpose
Tracks the defects you encounter in a programming project, along with information about when you created the defect and when you found and fixed the defect.

## Inputs Required
- Project name
- Defect Recording Log file (optional; the first time you use this skill you might need to create a new log from the template)
- Defect Recording Log template (see [defect-template.md](assets/defect-template.md) relative to this skill folder)
- The time (use the 'psp-record-time' skill to get the time)
- Defect Type Standard (see [defect-standard.md](assets/defect-standard.md) relative to this skill folder). If none of the categories seem to fit, use your best judgement.
- Type of defect
- Phase of project in which the defect was introduced
- Phase of project in which you fixed the defect

## Outputs Produced
- Defects discovered added to the Defect Recording Log
- Description of the defect to help you reflect on how to avoid it.

## Standard Workflow

### 1. Generate new log file

You only need to do this the first time you invoke this skill on a project. Read the [defect-template.md](assets/defect-template.md) file, fill out the header details, and save it as a new file in the `psp` folder in your project (you might need to create that folder). This new file is now your Defect Recording Log. Here's what the header fields mean:

- Name: Your name
- Date: Date when you start the project
- Program: The project name
- Language: The implementation language you use (if the problem statement doesn't specify a language and there isn't any existing code to help identify the language, leave this blank and fill it in later when you choose a language).

### 2. Record defect discovery

Create a new row in the Time Recording Log's table, using the fields in the table in the template file.
Fill out the following fields:

- Project: The project name
- Time: The time at which you discover the defect
- Number: An incrementing number to identify the defect; the first defect you discover is 1, the second 2, and so on
- Type: The type of defect you discover (refer to [defect-standard.md](assets/defect-standard.md) for the codes to use)
- Inject: The project phase in which the defect was introduced (for example: planning, design, coding)
- Fix Ref (optional): If you introduced this defect while fixing another defect, record the number of the defect you were trying to fix here.
- Description: A very brief (one-sentence) description of the defect.

### 3. Record defect fix

When you fix a defect, fill out the following fields in the table:

- Remove: The project phase in which you remove the defect (for example: design, coding, testing)
- Fix Time: The time spent fixing the defect (use the psp-record-time skill and your Time Recording Log to get this information)
- Description (optional): You can update the description with information you found while you were fixing the defect.

## Rules

### Purpose
Use this skill to record the defects you discover and fix while working on a software project. These data are used to complete the project plan summary.

### General
Record each defect separately and completely.