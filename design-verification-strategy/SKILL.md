---
name: design-verification-strategy
description: Define a risk-based verification plan to ensure that software changes are correctly implemented and validated through external checks.
license: AGPL-3.0-or-later
user-invocable: true
---

# Design Verification Strategy Skill

This skill implements the "Trust the Tests" pattern. Its goal is to move away from relying on an agent's report that a task is "done" and instead establish a concrete, external system of verification and validation before implementation begins.

## Intent
To create a verifiable "Definition of Done" (DoD) based on risk analysis, ensuring that the resulting software is not only built correctly (verification) but is also the right thing to build (validation).

## Standard Workflow

### 1. Analysis & Risk Assessment
Analyze the proposed change or feature. Identify:
- **Critical Paths**: The most important functionality that must not fail.
- **High-Risk Areas**: Complex logic, legacy code interactions, or areas with a history of regressions.
- **Edge Cases**: Boundary conditions and unusual inputs that could trigger failures.

### 2. Propose Verification Activities
Based on the risk assessment, propose a tailored set of checks:

#### A. Automated Testing (The Test Pyramid)
- **Unit Tests**: Specific functions/methods to isolate and test.
- **Integration Tests**: How components interact; specific interfaces to verify.
- **Acceptance Tests**: End-to-end scenarios that prove the feature meets user requirements.
- **Property-Based Testing**: For complex logic, suggest properties (invariants) that should always hold true regardless of input.

#### B. Static & Dynamic Analysis
- **Static Analysis**: Specific linters, type checkers, or security scanners to run.
- **Compiler Diagnostics**: Specific flags (e.g., `-Wall`, `-Wextra`) to enable for this change.
- **Dynamic Analysis**: Suggestions for tools like sanitizers or symbolic execution if the risk is high.

#### C. Validation & Human Review
- **Manual Verification**: A checklist of steps a human should take to validate the behavior.
- **Stakeholder Review**: Specific aspects of the implementation that require explicit sign-off from the user or customers.

### 3. Define "Definition of Done" (DoD)
Synthesize the above into a final, objective checklist. The task is only considered "Done" when every item on this list is checked off with evidence (e.g., test logs, analysis reports).

## Output Format
Your output should be structured as follows:

### Risk Profile
- **High Risk**: [List areas]
- **Criticality**: [Explain why these are critical]

### Verification Plan
- **Unit Tests**: [Specific scenarios]
- **Integration/Acceptance**: [Key flows to verify]
- **Advanced Testing**: [Properties to check or tools to use]
- **Analysis Tools**: [Linters/flags/scanners]

### Definition of Done (Checklist)
- [ ] Evidence that X test passes.
- [ ] Static analysis report shows no new warnings in Y area.
- [ ] Manual verification of Z flow completed.
- [ ] User confirmation of W behavior.
