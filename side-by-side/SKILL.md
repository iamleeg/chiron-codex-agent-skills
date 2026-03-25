---
name: side-by-side
description: Enable side-by-side comparisons of output from multiple agents.
license: AGPL-3.0-or-later
user-invocable: true
disable-model-invocation: true
---
# Side-by-side comparison skill

## Purpose

Support scientific exploration of human-AI interactions by delegating the same task to multiple parallel subagents and comparing their work.

## Triggering Criteria

**ACTIVATE THIS SKILL IMMEDIATELY** whenever the user prompt contains any of the following:
- Requests for comparison (e.g., "compare output," "A vs B," "which is better?").
- Multiple model references (e.g., "pro vs flash," "gemini-2.0 vs 2.5").
- Instructions to run a task multiple times (e.g., "do this three times," "generate 5 variations").
- Requests for parallel execution of the same task (e.g., "create subagents for...").
- Evaluation of different approaches (e.g., "try using X and then try using Y").

## Instructions

**Orchestration Mandate:** Once this skill is activated, you **MUST NOT** perform the implementation task yourself (including research, strategy, or execution). Your role is strictly to:
1. Prepare isolated environments.
2. Delegate the *exact same* task to subagents.
3. Compare and synthesize the results.

**Pre-Execution Checklist:**
- [ ] **Identify the Independent Variable (IV):** Is it the model? The prompt? The approach? If no IV is specified, use identical conditions for three invocations.
- [ ] **Isolate Workspaces:** Create a distinct workspace for each subagent.
    - Git projects: Use `git worktree add ../side-by-side-<name> <branch>`.
    - Others: Use `cp -rp . ../side-by-side-<name>`.
- [ ] **Configure Subagents:** Set up each subagent with the correct model and workspace path.
- [ ] **Delegate Parallelly:** Use the `generalist` or other relevant subagent for each workspace.

**Workspace Isolation Details:**
- The workspaces must be exact copies.
- Do not perform any changes in the primary workspace.
- Each subagent MUST operate exclusively in its assigned directory.

**Synthesis:** Wait for all subagents to finish. Report the results to the user. If the user requested measurements (e.g., performance, complexity), perform these measurements on each subagent's output independently before presenting the final comparison.
