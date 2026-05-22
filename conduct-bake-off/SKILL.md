---
name: conduct-bake-off
description: Conduct a controlled experiment to compare two alternatives by varying one independent variable and measuring the resulting dependent variable.
license: AGPL-3.0-or-later
user-invocable: true
---

# Conduct Bake-Off Skill

This skill implements the "Bake Off" pattern. It replaces subjective "vibes" with a controlled experiment to determine which of two alternatives is superior for a specific task. To ensure scientific validity, the bake-off must isolate a single variable to avoid confounding results.

## Intent
To objectively compare two candidates (models, tools, or implementations) by varying exactly one Independent Variable (IV) while keeping all other factors constant, and measuring the impact on a single Dependent Variable (DV).

## Standard Workflow

### 1. Experiment Design
Before starting, define the parameters of the test:
- **Independent Variable (IV)**: The single parameter being varied (e.g., Model A vs. Model B; Tool X vs. Tool Y; Approach 1 vs. Approach 2).
- **Dependent Variable (DV)**: The single metric used to determine success (e.g., Pass/Fail on tests; Time to completion; Number of iterations; Lines of code produced).
- **Control Variables**: List everything that must remain identical for both trials to ensure a fair test (e.g., the prompt, the codebase state, the environment, the constraints).

### 2. Execution of Trials
Run the experiment in two isolated phases:
- **Trial A**: Execute the task using the first candidate. Record the value of the DV.
- **Trial B**: Reset the environment to the exact same starting state (e.g., `git reset --hard`). Execute the task using the second candidate. Record the value of the DV.

### 3. Comparison & Reporting
Compare the measured DVs for both trials without introducing new variables or assumptions.

## Output Format
The result must be presented as a **Bake-Off Comparison Report**:

### 🧪 Experiment Setup
- **Independent Variable (IV)**: [Candidate A] vs [Candidate B]
- **Dependent Variable (DV)**: [Metric being measured]
- **Control Variables**: [List of constants held fixed]

### 📊 Results
| Candidate | Measured DV Value | Notes |
| :--- | :--- | :--- |
| **[Candidate A]** | [Value] | [Observations during trial] |
| **[Candidate B]** | [Value] | [Observations during trial] |

### 🏆 Conclusion
- **Winner**: [Candidate with the superior DV value]
- **Delta**: [The magnitude of the difference]
- **Verdict**: [Brief statement on whether the difference is significant enough to warrant a change in tool/model/approach]
