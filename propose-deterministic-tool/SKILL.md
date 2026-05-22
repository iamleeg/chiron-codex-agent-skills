---
name: propose-deterministic-tool
description: Analyze failure patterns to identify a deterministic tool or script that can replace unreliable generative attempts.
license: AGPL-3.0-or-later
user-invocable: true
---

# Propose Deterministic Tool Skill

This skill implements the "Replace Vibes with Tools" pattern. It is used when an agent finds itself in a cycle of trial-and-error ("vibing") without reaching a stable solution, or when a task is fundamentally deterministic but generative prompts are failing to produce consistent results.

## Intent
To replace an unreliable generative process with a reproducible tool. The goal is to identify the "deterministic core" of a problem and propose a programmatic solution that ensures correctness and reduces context noise.

## Trigger Conditions
The model should invoke this skill (or be prompted to use it) when:
- It has made multiple failed attempts at the same subtask.
- The task involves updating structured files (e.g., project manifests, Xcode projects, complex XML/JSON) where small errors cause total failure.
- The output of a task is consistently "almost right" but requires tedious manual correction every time.

## Standard Workflow

### 1. Failure Analysis & Core Identification
Review the recent session history to analyze why generative attempts are failing.
- **Identify the Pattern**: Is it a syntax error? A failure to follow constraints? A misunderstanding of a complex file format?
- **Isolate the Deterministic Core**: Define exactly what part of the process can be handled by a program rather than a model (e.g., "The task is actually just extracting X from Y and inserting it into Z in a specific JSON schema").

### 2. Existing Tool Audit
Before proposing a new script, determine if a deterministic solution already exists:
- **Package Manager Check**: Check for the presence of common package managers (`brew`, `npm`, `pip`, `cargo`, `gem`, etc.) to see what ecosystem is available.
- **System Search**: Use `which` or `find` to check if there are existing binaries or scripts in the project or system path that can perform this task.
- **Capability Match**: Verify if an existing tool can be configured (via flags or config files) to solve the problem.

### 3. Solution Proposal
Propose the best deterministic path forward:
- **Option A: Use Existing Tool**: If a tool was found, provide the exact command and arguments required.
- **Option B: Create New Tool**: If no tool exists, propose a specification for a new script (e.g., Bash, Python). The specification must include:
    - **Input/Output**: Exactly what it takes in and what it produces.
    - **Behavior**: A description of the deterministic logic.
    - **Exit Codes**: How it signals success vs failure.

### 4. Request for Approval
**Crucially, you must not install any packages or create any files until the user has explicitly approved the proposal.**

Present the findings to the user as follows:
1. **The Problem**: Why "vibing" is failing.
2. **The Deterministic Core**: What part of the task we are automating.
3. **The Proposed Tool**: Either an existing tool or a spec for a new script.
4. **The Benefit**: How this will improve reliability and reduce context noise.

## Output Format
Your proposal should be structured as follows:

### Failure Analysis
- **Symptom**: [Describe the repetitive failure]
- **Root Cause**: [Why generative prompting is insufficient here]

### Tool Discovery
- **Environment**: [Package managers found]
- **Existing Tools**: [Tools checked and whether they are suitable]

### Proposed Solution
- **Recommendation**: [Use existing tool X / Create new script Y]
- **Technical Spec**: [Commands or logic description]
- **Verification**: [How we will know the tool is working correctly]

**Would you like me to [install this tool / implement this script]?**
