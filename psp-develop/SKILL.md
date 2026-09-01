---
name: psp-develop
description: Implement a software project while tracking time spent and defects encountered and fixed.
license: AGPL-3.0-or-later
user-invocable: false
disable-model-invocation: false
---
# Personal Software Process development skill

## Purpose
Implements software (design, coding, and test) from a specification, while tracking information about the project progress.

## Inputs Required
- Requirements Specification
- Time Recording Log (use the psp-record-time skill to update this)
- Defect Recording Log (use the psp-record-defect skill to update this)

## Outputs Produced
- Quality software that satisfies the requirements and is well-tested

## Standard Workflow

You can perform any of these steps in any order, and use information from any of them to inform the others, but you must complete all of the following:

- Create a software design that implements the requirements specification.
- Create high-quality code that realises the software design.
- Create tests—unit tests and integration tests—that verify that the code meets the requirements.
- Ensure that all tests pass including existing tests (no regressions).
- Create documentation to show people how to use the software, and explains how the code works.
- Update any existing documentation, including project READMEs and user guides.

You _must_ record the time you spend in each phase using the psp-record-time skill, even if you enter and exit that phase multiple times. For example, if you write a test that takes 5 minutes, then write code for 3 minutes, then write another test for 3 minutes, then write more code for 4 minutes, you need to log each of these in your Time Recording Log.

You _must_ record all defects you find, and the time you spend fixing them, using the psp-record-defect skill. For example, if you build the software and encounter a compiler error, add a defect in the Compile phase with information about the error, fix the defect, then record the information about the fix.

## Rules

### Purpose

Use this skill to create quality software, and information about time spent and defects that you use later in your postmortem.
When you have completed executing this skill, you should be ready to move onto a project postmortem. You **MUST** get user approval to move to the postmortem phase: _NEVER_ decide yourself that you're complete.

### Subagents and Skills

You're allowed to delegate any of the work to subagents, including design, coding, testing, and documentation, and use any relevant skills. However, **YOU** are responsible for time and defect tracking in your logs.