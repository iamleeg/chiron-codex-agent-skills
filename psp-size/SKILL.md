---
name: psp-record-size
description: Record the size of code you generate
license: AGPL-3.0-or-later
user-invocable: false
disable-model-invocation: false
---
# Personal Software Process size-recording skill

## Purpose
Record the amount of code you create, delete, modify, and reuse during development work. You record this in Lines of Code (LOC). The goal is not to produce more LOC with every change; in fact, removing and reusing LOC while keeping all the software functionality is beneficial. The goal is to track the amount of project churn caused by each change.

## Inputs Required
- Project name
- User requirements
- (Optional) existing software project
- Your well-tested code changes
- Template size report [size-template.md](assets/size-template.md)

## Outputs Produced
- Report of the amount of code added, removed, modified, and reused
- Net software size change

## Standard Workflow

### 1. Generate new report

Read the [size-template.md](assets/size-template.md) file, fill out the header details, and save it as a new file in the `psp` folder in your project (you might need to create that folder). This new file is now your Size Recording Log. Here's what the header fields mean:

- Name: Your name
- Date: Date when you start the project
- Program: The project name
- Language: The implementation language you use (if the problem statement doesn't specify a language and there isn't any existing code to help identify the language, leave this blank and fill it in later when you choose a language).

### 2. Record code size changes

Fill out the following fields:

- Base Size (Actual): The number of LOC in the project before your changes.
- Deleted Size (Actual): The LOC you deleted in your work.
- Modified Size (Actual): The LOC you changed in your work.
- Added Size (Actual): The LOC you added in your work.
- Reused Size (Actual): The LOC of existing code you reused in your work.
- Added & Modified (Actual): The total of LOC added and LOC modified.
- Total Size (Actual): The new number LOC in the project after your changes.
- New Reused Size (Actual): The new number of LOC in the project available for reuse.

## Rules

### Purpose
Use this skill to record the amount of code you add, change, reuse, and delete while working on a software project. These data are used to complete the project plan summary.

### General
Count every line of code in source files, including comments and white spaces. Don't try to "game" the metrics through any variation in your coding approach; the purpose of this skill is to get an honest assessment of the code churn on your project.
