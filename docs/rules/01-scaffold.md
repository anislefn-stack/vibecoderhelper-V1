# Project Scaffold

## Project Overview

### Purpose

IssueBoard is a small team issue-tracking application for organizing
projects and managing issues collaboratively.

The application is intended to provide a simple alternative to heavier
issue-tracking platforms, allowing users to create projects, manage
project membership, create and work on issues, and review project activity.

### Target Users

Small teams that need to organize and track work across shared projects.

### Core Outcome

Users should be able to securely manage projects and collaborate on issues
while maintaining clear ownership, membership boundaries, and project
history.


## Technology Stack

### Frontend

- React
- TypeScript
- Tailwind CSS
- shadcn/ui

### Backend / Data

- Supabase
- Supabase Authentication
- Supabase PostgreSQL
- Row Level Security (RLS)

### External Services

None.


## Architecture

### Application Structure

The application consists of:

- An authentication layer for registration, login, and session management.
- A project-management layer for project ownership, membership, and
  archive state.
- An issue-management layer for issues belonging to projects.
- A dashboard for project and issue summaries.
- A project activity-history layer for recording meaningful changes.
- Shared UI components and utilities following the existing project
  organization.

Keep responsibilities separated without introducing unnecessary
abstraction.

### Data Flow

Users authenticate through Supabase Authentication.

Authenticated users interact with projects and issues through the
application's data layer.

Projects determine the authorization boundary for their issues,
memberships, and activity history.

Issues belong to projects and may be assigned only to members of the
corresponding project.

Activity records belong to projects and preserve a historical record of
meaningful project and issue actions.

Database security policies must enforce access boundaries rather than
depending solely on frontend filtering.

### Authentication & Authorization

Users must authenticate before accessing application data.

A user may access a project only when they are either:

- the project owner, or
- a member of the project.

Issue access follows the user's authorization to its project.

Only project owners may manage project membership.

Issue assignment must only allow members of the corresponding project.

Activity history must only be visible to users authorized to access its
project.

Authorization must be enforced at the database/server boundary, not only
through UI visibility checks.


## Core Features

- Email/password authentication
- Project creation
- Project renaming
- Project archiving
- Project membership
- Issue creation
- Issue editing
- Issue deletion
- Issue status management
- Issue priority management
- Issue assignment
- Project dashboard
- Issue counts and status summaries
- Recently updated issues
- Project activity history
- Responsive desktop/mobile interface


## Code Organization

- New project-related functionality → existing project-management area
- New issue-related functionality → existing issue-management area
- Shared UI → existing shared component patterns
- Data access → existing Supabase/data-access patterns
- Authentication → existing authentication patterns
- Database changes → Supabase migrations/schema mechanisms already used
  by the project

Follow the existing project structure rather than introducing a parallel
architecture.


## Constraints & Invariants

- Users must never gain access to projects they do not own or belong to.
- Users must never gain access to issues belonging to unauthorized
  projects.
- Project membership must be enforced server-side/database-side.
- Only project owners can manage project membership.
- Issues can only be assigned to members of their project.
- Archived projects must not accept new issues.
- Archived projects must retain their existing issues and historical data.
- Existing project and issue data must not be lost during feature changes.
- Existing authentication and authorization behavior must remain intact.
- Activity history must survive deletion of the entity it describes.
- Activity history must remain available after a project is archived.
- Activity records must identify the actual authenticated user who
  performed the action.
- Historical records must not allow one user to impersonate another.
- Do not introduce Redux or another global state-management library.
- Do not introduce external services unless genuinely required.
- Avoid unnecessary dependencies and abstractions.


## External Service Boundaries

- Supabase Authentication → user authentication and session management.
- Supabase PostgreSQL → persistent application data.
- Supabase RLS → database-level authorization boundaries.

Do not move authorization responsibility to an external service or rely
solely on frontend checks.


## Rejected Approaches

- Redux or another global state-management library → unnecessary for the
  application's expected complexity.
- External activity/logging service → unnecessary; project history should
  remain part of the application's own data model.
- Client-only authorization → insufficient for protecting project,
  issue, membership, and activity data.
- Replacing the existing architecture for individual features →
  unnecessary risk and unnecessary scope.


## Maintaining This Scaffold

- This document describes the project's intended architecture and
  requirements.
- Do not use it as a progress log; progress belongs in
  `docs/PROJECT-STATE.md`.
- Do not duplicate information that can be reliably discovered from the
  codebase.
- Update this document when the project's intended architecture, stack,
  major feature set, constraints, or important boundaries change.
- Do not update it for routine implementation progress.
- Never invent architectural decisions that the project has not actually
  made.
- If this document conflicts with the actual implementation, stop and
  determine whether the code or the scaffold represents the intended
  state before making a consequential change.
