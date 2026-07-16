---
name: write-epic
description: Create an Epic through user interview, codebase exploration, and component design, then submit as a GitHub issue. Use when user wants to write an Epic, create a feature epic, or plan a large body of work in a .NET web application.
---

This skill will be invoked when the user wants to create an Epic. You may skip steps if you don't consider them necessary.

The target stack is .NET (C# / ASP.NET Core) for backend and web UI (Razor Pages, Blazor, or a JS frontend). The scope can be any part of the app: domain classes, interfaces, API endpoints, services, UI components, database schema, etc.

1. Ask the user for a long, detailed description of the problem they want to solve and any potential ideas for solutions.

2. Explore the repo to verify their assertions and understand the current state of the codebase. Pay attention to:
   - Project structure (solution layout, layers: Domain, Application, Infrastructure, Web)
   - Existing patterns (CQRS, MediatR, repositories, minimal APIs vs controllers, etc.)
   - UI approach (Razor Pages, Blazor, or separate frontend)
   - ORM and database (EF Core, Dapper, etc.)

3. Interview the user relentlessly about every aspect of this plan until you reach a shared understanding. Walk down each branch of the design tree, resolving dependencies between decisions one-by-one. For .NET web apps, make sure to cover:
   - Which layer(s) are affected (domain model, application logic, infrastructure, API, UI)
   - Whether new endpoints, pages, or components are needed
   - Auth/authorization requirements
   - Any schema or migration changes

4. Sketch out the major components you will need to build or modify to complete the implementation. These can include:
   - Domain classes and interfaces
   - Application services, commands, queries, or handlers
   - API endpoints or Razor/Blazor pages and components
   - Infrastructure concerns (repositories, external services)
   - EF Core entities or migrations

   Actively look for opportunities to extract deep components that can be tested in isolation.

   A deep component (as opposed to a shallow one) is one which encapsulates a lot of functionality in a simple, testable interface which rarely changes.

   Check with the user that these components match their expectations. Check with the user which components they want tests written for.

5. Once you have a complete understanding of the problem and solution, use the template below to write the Epic. The Epic should be submitted as a GitHub issue.

<epic-template>

## Problem Statement

The problem that the user is facing, from the user's perspective.

## User Stories

A LONG, numbered list of user stories. Each user story should be in the format of:

1. As an <actor>, I want a <feature>, so that <benefit>

<user-story-example>
1. As a bank customer, I want to see the balance on my accounts, so that I can make better informed decisions about my spending
</user-story-example>

This list of user stories should be extremely extensive and cover all aspects of the feature.

## Acceptance Criteria

- [ ] Criterion 1
- [ ] Criterion 2
- [ ] Criterion 3

Specific, measurable conditions that must be met for the Epic to be considered complete. Each criterion should be testable and unambiguous.

## Dependencies

Other Epics, features, or work items that must be completed before this Epic can start, or that this Epic will impact.

- Blocked by: [list any dependencies]
- Blocks: [list any work this Epic blocks]

## Technical Notes

Implementation considerations and decisions. This can include:

- The components that will be built/modified (classes, interfaces, endpoints, pages, etc.)
- The public contracts (interfaces, DTOs, API routes) of those components
- Technical clarifications from the developer
- Architectural decisions and layer responsibilities
- Schema or migration changes
- API contracts (routes, request/response shapes)
- UI component structure and interactions
- Authorization rules

Do NOT include specific file paths or code snippets. They may end up being outdated very quickly.

## Out of Scope

A description of the things that are out of scope for this Epic.

## Further Notes

Any further notes about the Epic.

</epic-template>
