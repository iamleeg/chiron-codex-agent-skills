---
name: create-execution-plan
description: Transform high-level goals or requirements into a detailed, risk-aware execution plan and roadmap.
license: AGPL-3.0-or-later
user-invocable: true
---

# Create Execution Plan Skill

## Intent
To transform a high-level goal into a detailed, risk-aware execution plan for user review. This skill is designed to ensure that the agent and user are in complete agreement on the approach and roadmap before a single line of implementation code is written. 

**Crucially, the goal of this skill is planning, not implementation. You must present the final plan to the user and receive explicit approval before proceeding to any coding tasks.**

This skill implements the "Stop and Plan" pattern. It prevents "vibe coding" by requiring a structured analysis of the problem space, exploration of alternatives, and a concrete roadmap before implementation begins.

## Input Expectations
The agent should use this skill when the user provides:
- **A high-level goal or feature request** in the chat prompt.
- **Reference to existing design documents**, specifications, or architectural notes within the project folder.
- **An outline or "napkin sketch" plan** that needs formalization into a professional execution strategy.

If no sufficient information is provided, the agent must first ask the user for the necessary context before proceeding with the workflow.

## Standard Workflow

### 1. Context Synthesis & Gap Analysis
Gather all available information from the prompt and project files.
- Use the `ambiguity-resolution` skill to identify gaps in the requirements or conflicts in the design.
- Explicitly list "Knowns" vs "Unknowns".

### 2. Alternative Exploration
Do not settle on the first solution. Propose at least two distinct technical approaches:
- **Approach A (e.g., The Conservative Path)**: Lowest risk, uses existing patterns, potentially slower to implement or less performant.
- **Approach B (e.g., The Optimized/Modern Path)**: Higher potential reward, might introduce new dependencies or architectural changes.
- For each approach, provide a brief analysis of **Pros**, **Cons**, and **Trade-offs**.

### 3. Risk Assessment
Identify the "danger zones" for the chosen path:
- **Technical Risks**: Potential bottlenecks, compatibility issues, or complex integrations.
- **Process Risks**: Dependencies on other tasks, missing information, or tight deadlines.
- **Regressions**: Areas of the existing system most likely to be impacted by the change.

### 4. Verification Alignment
Integrate with the `design-verification-strategy` skill.
- Define how the success of this plan will be measured.
- Ensure that the roadmap includes specific checkpoints for verification (e.g., "Run integration tests for X" before moving to Y).

### 5. Detailed Roadmap (The Execution Sequence)
Break the work down into a sequence of small, manageable tasks.
- Each task should be atomic and verifiable.
- If using a task tracker like `beads`, the agent should propose the specific list of tasks to be created.
- Include "Check-and-Pivot" points where the agent is instructed to stop and review progress with the user.

**Final Step: User Review**
Once the plan is complete, present it clearly to the user. Stop all further action and explicitly ask for their feedback and approval of the plan before starting any implementation work.

## Output Format
The resulting execution plan should be structured as follows:

### 1. Goal & Scope
- **Objective**: [Clear statement of what is being achieved]
- **Out of Scope**: [What this plan explicitly does NOT cover]

### 2. Analysis & Alternatives
- **Ambiguities Resolved**: [Summary of resolutions from `ambiguity-resolution`]
- **Selected Approach**: [Approach A/B] and why it was chosen over the others.

### 3. Risk Matrix
| Risk | Impact | Mitigation Strategy |
| :--- | :--- | :--- |
| [Risk X] | [High/Med/Low] | [How to avoid or handle it] |

### 4. Verification Strategy
- [Brief summary of the verification plan, referencing `design-verification-strategy`]

### 5. Step-by-Step Roadmap
1. **Phase 1: Preparation** (e.g., Setup, scaffolding, basic tests)
2. **Phase 2: Core Implementation** (The "meat" of the work)
3. **Phase 3: Hardening & Verification** (Refactoring, edge cases, final tests)
4. **Phase 4: Final Validation** (User sign-off, documentation)
