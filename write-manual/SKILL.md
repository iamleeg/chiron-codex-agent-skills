---
name: write-manual
description: Generate user instructions for software, describing how to deploy it, launch it, and use the principal flows.
license: AGPL-3.0-or-later
user-invokable: true
---
The user wants you to generate documentation that explains to someone how they use the software in this project. You need to write clear, comprehensive, unambiguous documentation that explains every step, including installation.

## Authoring principles

 - Use the second person to address the reader, and write in the present tense. You explain to them what they do to set up and use the software.
 - Avoid the passive voice. Always make it clear what the reader needs to do, what the software does for them, and what other agents or services do.
 - Write out complete steps in the correct order. You can refer to flows in other areas of the documentation, but never assume that the reader knows how to perform a task without providing an explanation.

## Documentation format

Create a markdown document with these sections:

<template>
# Software Name

Brief description of the software, how someone accesses it (command-line, web, or GUI), and its goals.

## Installation

### Prerequisites

List things the reader already needs to set up the software. This can include other software packages, operating system version, API keys for other services, or hardware requirements.

### Install the package

List user interface steps, or shell commands, that the reader completes to install the software.

## Setup and Configuration

List any steps that the reader completes to get ready to use the software. This might include getting API credentials from another service, setting environment variables, or completing a first-run configuration workflow in the software itself.

Clearly indicate whether any of the steps are optional, for example, if the software can work with local data, then getting API credentials for a remote service is optional.

## Usage

Create a level-three heading for each important user flow in the application, then give the reader numbered steps to follow to perform that flow.

## Troubleshooting and Support

Finally, give the reader information on how to diagnose problems, including enabling debugging modes or additional logging, and how to report issues to the support team.
</template>

There's an example of a user manual in examples/user-guide.md.

## Sources of information

Use any documentation in the project as the basis for your user guide, for example design documents, completed task tickets, and source comments. The **most valuable** source of information is the test suite, particularly any acceptance or end-to-end tests. These tests document the expected workflows in the software, so you should explain to the reader how they perform those workflows using the software's user interface.
