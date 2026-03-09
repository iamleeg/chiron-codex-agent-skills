---
name: ambiguity-resolution
description: Resolve design ambiguities
license: AGPL-3.0-or-later
user-invokable: true
---
# Ambiguity Resolution Skill

This skill helps you identify design ambiguities, and resolve them with the user's input.

Given a design document or a specification, identify conflicts in the requirements or design, or ambiguities in the requirements statement, by searching the document for instances of the word CONFLICT or AMBIGUITY. For each instance that you find, ask the user how to resolve the conflict or ambiguity. Use the user's answer to update the document, and remove the original conflict/ambiguity statement from the document.

The file examples/process.md shows an example in a process document.
