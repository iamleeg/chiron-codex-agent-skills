# Chiron Codex Agent Skills

These agent skills implement patterns in the Chiron Codex [Patterns in AI-Augmented Software Development](https://library.chironcodex.com/books/patterns-in-ai-augmented-software-development) catalog.

## Available Skills

- **ambiguity-resolution**: Identifies and resolves design conflicts and ambiguities in requirements or specifications to ensure a clear foundation before implementation. Implements [Disclose Ambiguity](https://library.chironcodex.com/books/patterns-in-ai-augmented-software-development/page/disclose-ambiguity).
- **analyze-interaction-transcript**: Diagnoses systemic failures in the collaboration process by analyzing interaction dynamics. Implements [You Reflect](https://library.chironcodex.com/books/patterns-in-ai-augmented-software-development/page/you-reflect) and [Model Reflects](https://library.chironcodex.com/books/patterns-in-ai-augmented-software-development/page/model-reflects).
- **conduct-bake-off**: Replaces subjective "vibes" with a controlled experiment to objectively compare two alternatives. Implements [Bake Off](https://library.chironcodex.com/books/patterns-in-ai-augmented-software-development/page/bake-off).
- **create-execution-plan**: Transforms high-level goals into detailed, risk-aware execution plans for user review before any coding begins. Implements [Stop and Plan](https://library.chironcodex.com/books/patterns-in-ai-augmented-software-development/page/stop-and-plan).
- **design-verification-strategy**: Establishes a concrete, external system of verification and validation to define a verifiable "Definition of Done." Implements [Trust the Tests](https://library.chironcodex.com/books/patterns-in-ai-augmented-software-development/page/trust-the-tests).
- **draft-engineering-log**: Synthesizes the day's interactions into a structured engineering log from the developer's perspective. Implements [Remember What We Did](https://library.chironcodex.com/books/patterns-in-ai-augmented-software-development/page/remember-what-we-did).
- **help-me-reflect**: Identifies points where human emotional responses have negatively impacted interaction quality and suggests improvements. Implements [You Reflect](https://library.chironcodex.com/books/patterns-in-ai-augmented-software-development/page/you-reflect).
- **identify-extractable-prompts**: Decomposes complex goals into subtasks and proposes specific prompts or skills to provide more control over execution. Implements [Extract Prompt](https://library.chironcodex.com/books/patterns-in-ai-augmented-software-development/page/extract-prompt).
- **propose-deterministic-tool**: Identifies the "deterministic core" of a problem to replace unreliable generative processes with reproducible tools. Implements [Replace Vibes with Tools](https://library.chironcodex.com/books/patterns-in-ai-augmented-software-development/page/replace-vibes-with-tools).
- **side-by-side**: Supports scientific exploration of human-AI interactions by delegating the same task to multiple parallel subagents for comparison. Implements [Bake Off](https://library.chironcodex.com/books/patterns-in-ai-augmented-software-development/page/bake-off).
- **take-baby-steps**: Decomposes large, ambiguous goals into a sequence of small, verifiable subtasks to minimize divergence and maximize feedback speed. Implements [Baby Steps](https://library.chironcodex.com/books/patterns-in-ai-augmented-software-development/page/baby-steps).
- **task-review**: Compares the current state of a project against initial instructions to determine if the task is complete or if further work is required. Implements [Model Reviews](https://library.chironcodex.com/books/patterns-in-ai-augmented-software-development/page/model-reviews).
- **triage-session-findings**: Distills long conversation histories into actionable assets, reusable prompts, and technical memories. Implements [Extract Prompt](https://library.chironcodex.com/books/patterns-in-ai-augmented-software-development/page/extract-prompt), [Write Down TODOs](https://library.chironcodex.com/books/patterns-in-ai-augmented-software-development/page/write-down-todos), and [Remember What We Did](https://library.chironcodex.com/books/patterns-in-ai-augmented-software-development/page/remember-what-we-did).
- **write-manual**: Generates clear, comprehensive, and unambiguous user instructions for software deployment and operational flows. Implements [Generate Documentation](https://library.chironcodex.com/books/patterns-in-ai-augmented-software-development/page/generate-documentation).

## Using the Skills

Clone this repo, and copy the skills definitions into your agent's skills folder (for example, `~/.agent/skills/`), or your project's agent skills folder (for example, `/path/to/project/.agent/skills`).

Support for agent marketplaces will come soon!

## Redistributing and Adapting the Skills

Chiron Codex makes these skills available under the terms of the [GNU Affero General Public License version 3.0](https://www.gnu.org/licenses/agpl-3.0.txt), or any later version accepted by the project's proxy. Pursuant to section 14 of the license, Dr. Graham Lee is the nominated proxy for accepting later versions.

If you require access to the skills under alternative license arrangements, discuss these with Dr. Graham Lee: use the email address in the commit messages, or send a direct message in the [Chiron Codex Patreon](https://patreon.com/chironcodex).

## Mutual Support

For information about these agent skills, or to help their continued development, join the [Chiron Codex Patreon](https://patreon.com/chironcodex).
