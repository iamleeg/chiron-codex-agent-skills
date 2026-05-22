# Take Baby Steps

## Intent
Decompose a large, ambiguous goal into the smallest possible sequence of verifiable subtasks to minimize divergence and maximize feedback speed. This skill implements the "Baby Steps" pattern by limiting work-in-process (WIP) and creating frequent review points.

## Process
1. **Analyze Goal**: Review the user's prompt for complexity and potential "divergence points"—areas where an AI might misinterpret intent or take an unexpected direction.
2. **Map Dependencies**: Identify the technical prerequisites for each piece of functionality to ensure a logical execution order.
3. **Slice into Baby Steps**: 
    - Break the task down so that each step is a "single unit of work."
    - Ensure each step has a clear, objective "Definition of Done" (DoD).
    - Avoid vague implementation blocks (e.g., instead of "Implement Backend," use "Define API endpoints for User Authentication").
4. **Isolate Context**: For each step, identify the minimum necessary information required to execute it, intentionally stripping away noise from other steps to avoid context pollution.
5. **Generate Roadmap**: Produce a structured output containing the sequence of steps, their DoD, and suggested prompts.

## Guidelines for Slicing
- **Batch Size**: If a step feels like it could take more than one or two turns to complete, it is too big. Split it further.
- **Verifiability**: Every step must result in something that can be proven correct (e.g., a specification document, a passing test, successful compilation, or a verified UI behavior).
- **Risk First**: Prioritize steps that uncover the most risk early on (e.g., prototyping core logic before polishing the interface).

## Output Format
For each baby step, provide:

### Step [N]: [Title]
- **Goal**: [Brief description of what this step achieves]
- **Definition of Done**: [Clear, objective criteria that signal the step is complete and correct]
- **Suggested Prompt**: 
  > "[A targeted prompt designed to be used in a 'Clean Slate' session, containing only the necessary context for this specific step]"
- **Dependencies**: [Which previous steps must be finished first]

## Related Patterns
- **Clean Slate**: Each baby step should ideally start with a fresh context.
- **You Review**: The user must verify the DoD of Step N before proceeding to Step N+1.
- **Extract Prompt**: Use this to isolate specific requirements from the original goal into the suggested prompts.
