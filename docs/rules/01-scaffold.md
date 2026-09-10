# Project Scaffold

## Project Overview

### Purpose

A task management web application that allows authenticated users
to organize work into projects and manage tasks within those projects.

### Target Users

Authenticated users who need to organize and track tasks across
multiple projects.

### Core Outcome

Users can create projects, create and manage tasks within those
projects, track task status, and view project and task summaries
from a dashboard.


## Technology Stack

### Frontend

- React
- TypeScript
- Tailwind CSS
- shadcn/ui

### Backend / Data

- Supabase for authentication and persistent database storage
- Supabase database security policies for user data access control

### External Services

- Supabase is the only external service required by the current
  architecture.


## Architecture

### Application Structure

The application should use a simple React/TypeScript architecture.

Authentication, projects, tasks, and dashboard functionality should
have clear responsibilities without introducing unnecessary
architectural layers.

Use the existing project structure and conventions when adding new
functionality.

### Data Flow

Users interact with the application through the React frontend.

Authentication and application data are handled through Supabase.

Projects and tasks are persisted in the Supabase database.

A user's project and task data must remain isolated from other users.

### Authentication & Authorization

Users authenticate through Supabase Authentication.

Users can create and manage their own projects.

Tasks belong to projects and users must only be able to access tasks
belonging to projects they are authorized to access.

User data access must be enforced at the database/security layer,
not only through frontend visibility checks.


## Core Features

- User authentication
- User account access
- Project creation
- Project management
- Task creation inside projects
- Task title
- Task description
- Task status
- Todo status
- In-progress status
- Done status
- Dashboard showing projects
- Dashboard showing task counts
- Persistent database storage
- Responsive desktop interface
- Responsive mobile interface


## Code Organization

- Feature-specific code → follow the existing project structure and
  conventions.
- Shared UI → use the existing shared component system and shadcn/ui
  components where appropriate.
- Utilities → use the project's established utility location.
- Supabase/data logic → keep data access consistent with the existing
  Supabase integration patterns.

Prefer extending existing patterns over creating competing patterns.

Do not reproduce the complete file tree here. The actual codebase is
the source of truth for individual files and implementation details.


## Constraints & Invariants

- Keep the architecture simple.
- Do not introduce Redux or another global state-management library
  without a demonstrated architectural need.
- Do not add external services unless they are genuinely required.
- Users must only be able to access their own projects.
- Users must only be able to access tasks they are authorized to access.
- Authorization must not rely solely on client-side checks.
- Database-level access controls must protect user-owned data.
- New functionality should follow established project patterns.
- Do not unnecessarily rewrite working functionality.


## External Service Boundaries

- Supabase → authentication and persistent application data.
- Supabase database security policies → enforce access boundaries for
  user-owned projects and tasks.

No additional external service is currently part of the architecture.

Do not introduce one without a genuine requirement.


## Rejected Approaches

- Redux / unnecessary global state management → rejected to keep the
  architecture simple.
- Additional external services → rejected unless genuinely required.
- Client-only authorization → rejected because user data must be
  protected at the database/security layer.


## Maintaining This Scaffold

- This document describes the project's intended architecture and
  requirements.
- Do not use it as a progress log; progress belongs in
  `docs/PROJECT-STATE.md`.
- Do not duplicate information that can be reliably discovered from
  the codebase.
- Update this document when the project's intended architecture,
  stack, major feature set, constraints, or important boundaries
  change.
- Do not update it for routine implementation progress.
- Never invent architectural decisions that the project has not
  actually made.
- If this document conflicts with the actual implementation, stop and
  determine whether the code or the scaffold represents the intended
  state before making a consequential change.
