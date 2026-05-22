---
name: triage-session-findings
description: Review session history to extract pending tasks, reusable prompts, and technical memories.
license: AGPL-3.0-or-later
user-invocable: true
---

# Triage Session Findings Skill

This skill is an operational tool designed to clean up the "cognitive load" of a session. It implements parts of the *Extract Prompt*, *Write Down TODOs*, and *Remember What We Did* patterns by distilling a long conversation into actionable assets.

## Intent
To prevent valuable information from being lost in a long chat history and to ensure that the model's context remains focused on the current task by moving secondary items into external storage.

## Standard Workflow

### 1. Transcript Scan & Categorization
Analyze the recent interaction history to identify four types of "findings":
- **Deferred Tasks**: Mentioned requirements or bugs that were postponed ("Let's fix this later", "I'll add a UI for this eventually").
- **Repetitive Subtasks**: Patterns where the agent was given similar instructions multiple times.
- **Technical Discoveries**: Facts about the system discovered during trial and error (e.g., "The API requires Header X to be present").
- **Process Rules**: User corrections on how the agent should work ("Stop using `sed` and use a proper parser instead").

### 2. Actionable Proposals
For each category, propose the appropriate output:
- **For Deferred Tasks** $\rightarrow$ Create entries in a task tracker (e.g., `beads`).
- **For Repetitive Subtasks** $\rightarrow$ Invoke `identify-extractable-prompts` to turn them into reusable sub-agent prompts.
- **For Discoveries & Rules** $\rightarrow$ Format these as "Memories" for the *Remember What We Did* pattern.

### 3. Memory Synthesis
Create a concise summary of "Institutional Knowledge" gained during this session. This should be stored in a way that it can be retrieved at the start of future sessions to avoid repeating mistakes.

## Output Format
Your output should be presented as a **Session Summary Report**:

### 📝 Pending TODOs
- [ ] Task A: [Description]
- [ ] Task B: [Description]

### 🛠️ Candidate Extracted Prompts
- [Proposed Prompt X]: [Why it's useful / what it automates]

### 🧠 Technical Memories (Remember What We Did)
- **Fact**: [The discovery/rule] $\rightarrow$ *Impact: [How this changes future work]*
- **Constraint**: [The limitation] $\rightarrow$ *Impact: [What to avoid]*

**Would you like me to [create these tasks / record these memories / identify the prompts]?**
