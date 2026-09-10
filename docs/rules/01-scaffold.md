# Project Scaffold

## Project Overview

### Purpose

<!-- What is this project? What problem does it solve?
Do not describe implementation details, individual components, or how the code currently works. -->

### Target Users

<!-- Who is this application for?
Do not list generic audiences that do not affect product or implementation decisions. -->

### Core Outcome

<!-- What should the finished product allow users to accomplish?
Do not list every feature or describe step-by-step implementation. -->

## Technology Stack

### Frontend

<!-- What frontend technologies are intentionally being used: framework, language, styling system, UI library, etc.
Do not copy the full dependency list or document versions that can be discovered from the project configuration. -->

### Backend / Data

<!-- What backend, database, authentication, and data technologies are intentionally being used.
Do not copy the database schema, table definitions, generated types, or other details already discoverable from the project. -->

### External Services

<!-- What important external APIs, storage providers, payment systems, AI services, or other integrations are intentionally part of the project.
Do not list every installed package or dependency that is not an important architectural dependency. -->

## Architecture

### Application Structure

<!-- Describe the major parts of the application and their responsibilities.
Do not reproduce the complete file tree or list every component, route, hook, or utility. -->

### Data Flow

<!-- Explain important flows between the frontend, backend, database, and external services.
Focus on non-obvious or architecturally important flows.
Do not document ordinary fetch/render behavior that can be understood from the code. -->

### Authentication & Authorization

<!-- Explain how users authenticate and how access is intentionally controlled.
Document important security boundaries and rules.
Do not copy implementation details, session code, or database policies that can be inspected directly from the project. -->

## Core Features

<!-- List the major capabilities the application must provide.
Do not turn this into a task list, implementation checklist, or description of every small UI feature. -->

- Feature 1
- Feature 2
- Feature 3

## Code Organization

<!-- Define the intended organization for NEW code and where major responsibilities belong.
Do not duplicate the complete file tree or list every file that currently exists. -->

- New feature code → ...
- Shared UI → ...
- Utilities → ...
- Server/data logic → ...

<!-- Keep this focused on placement rules, not an inventory of the current codebase. -->

## Constraints & Invariants

<!-- List rules that must remain true throughout development.
These should prevent important mistakes and protect architecture, security, data integrity, or product requirements.
Do not include temporary preferences, task-specific instructions, or rules about how the AI should behave; those belong elsewhere. -->

- ...
- ...
- ...

## External Service Boundaries

<!-- Document important contracts, limitations, ownership boundaries, failure expectations, or security rules that are not obvious from the code.
Do not duplicate API documentation, SDK usage instructions, or secrets/credentials. -->

- Service → purpose → important constraint

## Rejected Approaches

<!-- Record important technologies, architectural patterns, features, or approaches
that were considered and intentionally rejected, including why.
Do not record minor alternatives or temporary implementation choices. -->

- Approach → reason rejected

## Maintaining This Scaffold

- This document describes the project's intended architecture and requirements.
- Do not use it as a progress log; progress belongs in `docs/PROJECT-STATE.md`.
- Do not duplicate information that can be reliably discovered from the codebase.
- Update this document when the project's intended architecture, stack, major feature set, constraints, or important boundaries change.
- Do not update it for routine implementation progress.
- Never invent architectural decisions that the project has not actually made.
- If this document conflicts with the actual implementation, stop and determine whether the code or the scaffold represents the intended state before making a consequential change.
