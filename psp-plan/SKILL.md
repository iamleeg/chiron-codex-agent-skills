---
name: psp-plan
description: Create a project plan with estimates for implementing a programming project
license: AGPL-3.0-or-later
user-invocable: false
disable-model-invocation: false
---
# Personal Software Process planning skill

## Purpose
Creates a project plan from an initial problem statement, including requirements and a project summary that helps you track estimated and actual time spent, and defects encountered.

## Inputs Required
- Problem statement (the user prompt)
- Project Plan Summary template (use [project-plan.md](assets/project-plan.md) relative to this skill folder)

## Outputs Produced
- Requirements specification agreed with the user (use the ambiguity-resolution skill to discover inconsistencies and ambiguities and ask the user to resolve them)
- Project Plan Summary with estimated total time required, and time spent in planning phase (use psp-record-time skill)
- Time Recording Log, including time spent in planning phase (use psp-record-time skill)
- Defect Recording Log, including defects encountered in planning phase (use psp-record-defect skill)

## Standard Workflow

### 1. Review memories from previous postmortems

Check for memories with 'bd memories' to see what mistakes you made on previous tasks, and what you learned from them. Account for your learnings in your plan and development work.

### 2. Determine requirements

Use the problem statement as the initial requirements description, and work with the user to create a detailed set of requirements using the ambiguity-resolution skill. Your output is a problem specification that you use to design and implement the software, which you write as a markdown file to your project folder. **MANDATORY**: ask the user to sign off on requirements or propose corrections; you **MUST** get sign-off before you proceed to the next step. Use the psp-record-time skill to record the time you spend on this activity, including interruptions, and the psp-record-defects skill to record any defects you encounter in this step.

### 3. Create Project Plan Summary

Create a new file in the project folder based on [project-plan.md](assets/project-plan.md). Fill out the header fields:

- Name: Your name
- Date: The date you start work on the project (use the Time Recording Log that you generated in step 1 to get this)
- Program: Name of the project
- Language: The implementation language you use. If you haven't chosen an implementation language yet and there isn't existing code to suggest one, leave this blank for now and fill it out later.

### 4. Fill out time estimates

In the Project Plan Summary file you created in step 2, fill out the estimated time in each phase, and the actual time spent in the planning phase from your Time Recording Log. Ignore the Actual% column for now.

### 5. Record planning defects

If you have any defects in your Defect Recording Log from the planning phase, record the counts in the relevant fields in the Project Plan Summary file.

## Rules

### Purpose

Use this skill to create a project plan, as well as a summary that you use later in your postmortem.
When you have completed executing this skill, you should be ready to move onto designing and implementing the software.