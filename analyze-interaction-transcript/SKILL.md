---
name: analyze-interaction-transcript
description: Analyze interaction dynamics to identify friction points and improve future collaboration patterns.
license: AGPL-3.0-or-later
user-invocable: true
---

# Analyze Interaction Transcript Skill

This skill is a strategic tool that implements the *You Reflect* and *Model Reflects* patterns. Rather than focusing on *what* was built, it focuses on *how* the interaction occurred, identifying behavioral patterns that lead to frustration or inefficiency.

## Intent
To diagnose systemic failures in the collaboration process—such as "prompt loops," attention drift, or emotional friction—and propose changes to the mindset, prompts, or tools used by both the human and the agent.

## Standard Workflow

### 1. Behavioral Analysis
Review the interaction transcript specifically for markers of friction:
- **Repetition Loops**: Identifying where the user repeated a requirement multiple times with no change in result.
- **Emotional Shifts**: Detecting changes in tone, aggressive language, or signs of frustration (e.g., "I already told you X").
- **Attention Drift**: Noting where the agent began to ignore constraints or forgot critical details after reading large files.
- **The "Vibe" Trap**: Identifying sequences where trial-and-error was used as a substitute for planning or tool use.

### 2. Root Cause Mapping
Map the observed behaviors to specific patterns:
- **If Repetition $\rightarrow$** Perhaps it's time to *Extract Prompt* or *Replace Vibes with Tools*.
- **If Attention Drift $\rightarrow$** The session may have become too long; a *Clean Slate* is needed.
- **If Emotional Friction $\rightarrow$** User expectations may not match the model's current capabilities; a *Stop and Plan* session is required to reset alignment.

### 3. Strategic Recommendations
Propose concrete changes to the interaction strategy:
- **Process Change**: "Instead of prompting me for X, let's use a specialized script."
- **Communication Change**: "I noticed I struggle with Y; please prompt me to confirm Z before proceeding."
- **Tooling Change**: Suggest creating a new agent skill or tool based on the failure patterns identified.

## Output Format
The analysis should be presented as a **Collaboration Post-Mortem**:

### 🚩 Friction Points
- **Pattern detected**: [e.g., The Repetition Loop] $\rightarrow$ [Context: "We spent 10 turns trying to fix the CSS without checking the browser console"].
- **Emotional Marker**: [Note any shifts in tone or frustration].

### 🔍 Root Cause Analysis
- [Explain why this happened from a technical or behavioral perspective].

### 🚀 Proposed Strategy Shift
- **Immediate Action**: [e.g., Use `propose-deterministic-tool` for the CSS task]
- **Long-term Change**: [e.g., "I will start every session by reviewing the project constraints file"]

**Do these observations align with your experience? Should we adopt this new strategy?**
