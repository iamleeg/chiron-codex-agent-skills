---
name: task-review
description: Reviews the user's original prompt and the current state of the project. Use when deciding whether you have completed the user's task.
license: AGPL-3.0-or-later
user-invokable: true
---
Repeat the initial instructions that the user gave you to the user. Compare the current state of the code with those instructions, and determine what work is needed to complete the task the user requested. If there isn't anything to do, just say PASSED.
