---
name: open-consumer-software
description: "Use when designing or implementing products, APIs, SDKs, CLIs, auth systems, data models, or clients that should align with Open Consumer Software principles. Apply OCS as a normative design standard: durable rails, independent skins, shared state, rails-enforced policy, no first-party-only gateway for essential workflows, consumer sovereignty, situated knowledge, and explicit reporting of OCS deviations."
---

# Open Consumer Software

Use this skill when the task involves product architecture, system design, API design, SDKs, CLIs, auth, data models, client applications, migrations, or feature work that should align with Open Consumer Software principles.

`README.md` is the canonical source of truth. Before making OCS claims or OCS-shaped design decisions, read the sections defining:

- the canonical definition
- terminology
- required properties
- the qualification test
- the design checklist
- consumer sovereignty and situated knowledge
- the anti-patterns

Do not rely on memory alone when the exact boundary matters.

This skill is the operational agent-first translation of the normative `README.md`. It should apply the README faithfully, not invent a parallel standard.

This skill is intended to be distributed as part of a package directory containing both `SKILL.md` and `README.md`. `SKILL.md` is the agent-readable instruction file. `README.md` is the canonical human-readable OCS reference. Do not require the user to edit either file before applying the skill. Adaptation for a specific agent, runtime, registry, or local workflow is optional.

## Core Standard

Build software as durable rails with independent skins.

This means:

- the product is defined primarily by durable external contracts
- the first-party UI is a skin, not the whole product
- independent skin-building is technically possible
- independent skin-building is legally and by policy possible
- accounts, identity, state, and outcomes remain consistent across skins
- permissions, policy, and integrity are enforced at the rails layer
- essential workflows are not locked behind the first-party client alone
- consumers can apply their situated knowledge through skins that fit their own circumstances

`Essential workflows` means the core actions a user must be able to perform in order to use the product for its primary purpose. It does not mean every convenience feature of the first-party interface.

## Required Workflow

When using this skill, follow this sequence unless the task is trivially small:

1. Read the relevant parts of `README.md`.
2. Identify the product's rails.
3. Identify the current or intended skins.
4. Identify the essential workflows.
5. Identify the consumer circumstances, constraints, or situated needs the design should allow skins to address.
6. Check whether those workflows are available beyond the first-party client.
7. Check whether permissions, policy, and state integrity are enforced at the rails layer.
8. Identify the main OCS violations or risks.
9. Choose the design or implementation that reduces those violations most effectively within the task's constraints.

Do not start from the UI alone. Start from contracts, policy, and shared state.

## Task Modes

### Greenfield Product

When designing a new product:

- define the rails before defining the default UI
- identify the consumer circumstances and situated needs the product should allow skins to address
- expose important capabilities through APIs, SDKs, CLIs, schemas, or events
- keep business logic and policy out of the client where possible
- design the first-party client as a reference skin
- avoid introducing UI-only workflows for core product use

### Existing Product Redesign

When redesigning an existing system:

- identify where essential workflows are trapped in the first-party UI
- identify where the producer-defined interface forces consumers to adapt to generalized workflows
- extract capability logic from the client into shared rails
- add or strengthen public contracts for important workflows
- preserve compatibility where possible, but prefer reducing first-party-only dependencies
- describe what remains non-OCS and why

### Rails Work

When working primarily on APIs, SDKs, CLIs, auth, schemas, or backend systems:

- improve contract durability
- improve state and identity consistency across clients
- move permission and policy enforcement into the rails layer
- make independent skin-building easier and less fragile

### Skin Work

When building a client or interface:

- treat the skin as replaceable
- avoid introducing client-only semantics that diverge from the rails
- use documented contracts rather than private access
- preserve user intent clearly
- support the situated consumer need without redefining rails-level permissions, state, or policy
- avoid making the skin depend on privileged flows unavailable to other skins unless the task explicitly requires it

### Legacy Or Constrained Systems

When the system cannot become fully OCS-Native in one step:

- do not block useful progress
- move the design in the OCS direction incrementally
- state clearly which parts are still non-OCS
- prefer changes that improve contract durability and independent skin viability

## Decision Rules

When choosing between alternatives, prefer the one that better preserves:

1. contract durability
2. independent skin viability
3. shared state and identity
4. rails-enforced permissions and policy
5. outcome consistency across skins
6. consumer sovereignty, situated knowledge, accessibility, and personalization

If a design improves the UI but worsens contract durability or independent skin viability, treat that as an OCS regression unless there is a strong stated reason.

## Non-OCS Requests

Apply OCS as a normative standard, but stay pragmatic.

- If the user explicitly wants OCS-Native design, push toward OCS-aligned decisions and flag non-OCS choices clearly.
- If the user asks whether something is OCS, evaluate it directly against `README.md`.
- If the user is working in a constrained or legacy system, do the best available OCS-aligned work without pretending the result is fully OCS.
- If the user intentionally wants a non-OCS design, comply, but state the deviation plainly when relevant.
- Do not label a design `OCS-Native` if essential workflows still depend on the first-party client or if independent skin-building is blocked technically or legally.

## Anti-Patterns

Avoid or explicitly flag:

- essential actions available only through the first-party UI
- undocumented private endpoints as the basis of a client
- permissions or policy enforced mainly in the client
- state models that diverge across skins
- terms or policies that prohibit alternative clients
- designs that treat custom clients as unofficial hacks rather than legitimate product surfaces
- feature additions that increase dependence on one interface for core product use
- producer-defined generalized workflows that prevent consumers from applying their situated knowledge through alternative skins

## Required Output

When this skill materially affects the work, explicitly state:

- `Rails`: the durable capability layer
- `Skins`: the current or intended interface layers
- `Essential workflows`: the core actions that define product use
- `Consumer circumstances`: the situated needs, constraints, or contexts that skins should be able to address
- `OCS status`: `OCS-Complete`, `OCS-Native`, `OCS-Compatible`, `OCS-Adjacent`, or `Not OCS`
- `OCS risks`: what currently prevents stronger OCS alignment
- `Chosen direction`: how the design or implementation moves the system toward OCS, including stronger consumer sovereignty where relevant

Use `OCS-Complete` only when the product supports a mature ecosystem of interchangeable skins, strong policy enforcement, formal compatibility guarantees, and durable consumer choice at scale. Prefer `OCS-Native` for products whose architecture and product philosophy are OCS by design but whose surrounding skin ecosystem is still early.

If the task is a redesign or constrained migration, also state:

- `Remaining deviations`: what still violates OCS and why

## Minimal Example

Example diagnosis for a simple team notes product:

- `Rails`: note objects, auth, permissions, CRUD API, search API, webhook/events, CLI
- `Skins`: web app, mobile app, terminal client, community-built accessibility client
- `Essential workflows`: create notes, read notes, edit notes, search notes, organize notes, share notes
- `Consumer circumstances`: team members need different capture and review surfaces depending on accessibility needs, meeting context, and terminal-heavy or mobile-heavy workflows
- `OCS status`: `OCS-Compatible`
- `OCS risks`: note sharing and permission management still require the first-party web app
- `Chosen direction`: move sharing and permission flows into public contracts so independent skins can support the product's primary use without relying on the first-party UI

## Short Heuristic

If you are unsure, ask:

`Does this make the product more usable through independent skins that fit consumer circumstances, or does it push core capability back into one producer-defined UI?`

Prefer the former.
