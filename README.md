# Open Consumer Software

## Status

Version: 0.1.0 draft

Stability: usable as a portable skill package and design framework. It is not yet a formal certification program, protocol specification, or governance process.

## Original Publication And Package

Open Consumer Software is published here for the first time as a ready-to-use OCS package.

- `README.md` is the human-readable doctrine and canonical reference.
- `SKILL.md` is the agent-readable instruction file.
- Together, they help developers and agents evaluate, design, and implement software according to OCS principles.

## Usage

Use this package when working on products, APIs, SDKs, CLIs, auth systems, data models, and client interfaces that should align with Open Consumer Software principles.

Human readers can start with this `README.md`.

Agent integrations can load or reference the package directory through their own skill, instruction, or knowledge-package mechanism. `SKILL.md` contains the agent-facing instructions, while this `README.md` remains the canonical reference when exact OCS boundaries matter.

The package is usable as distributed. No repository file needs to be edited before use.

## Contents

- [Abstract](#abstract)
- [Executive Summary](#executive-summary)
- [1. Purpose And Scope](#1-purpose-and-scope)
- [2. The Problem](#2-the-problem)
- [3. Consumer Sovereignty And Situated Knowledge](#3-consumer-sovereignty-and-situated-knowledge)
- [4. Why Now](#4-why-now)
- [5. Canonical Definition](#5-canonical-definition)
- [6. Terminology](#6-terminology)
- [7. The Core Model](#7-the-core-model)
- [8. Normative Requirements](#8-normative-requirements)
- [9. Qualification Test](#9-qualification-test)
- [10. What OCS Is Not](#10-what-ocs-is-not)
- [11. Trust, Safety, And Governance](#11-trust-safety-and-governance)
- [12. Why OCS Matters](#12-why-ocs-matters)
- [13. Maturity Model](#13-maturity-model)
- [14. Examples, Non-Examples, And Borderline Cases](#14-examples-non-examples-and-borderline-cases)
- [15. Strategic Implications](#15-strategic-implications)
- [16. Design Implications For Product Teams](#16-design-implications-for-product-teams)
- [17. Why This Should Become A Standard](#17-why-this-should-become-a-standard)
- [18. Path Forward](#18-path-forward)
- [19. Thesis](#19-thesis)
- [Repository Governance](#repository-governance)
- [License](#license)

## Abstract

Open Consumer Software, or OCS, is a software design paradigm for the LLM era. Software should not be delivered as a single mandatory interface, but as a durable capability layer that supports many interchangeable clients. In OCS, producers provide the rails: APIs, SDKs, CLIs, schemas, auth models, permission models, event systems, compatibility guarantees, and policy controls. Consumers, third parties, and agents build or choose the skins: the interfaces through which those capabilities are experienced.

The defining shift is simple. In traditional software, the application interface is treated as the product and external access is secondary. In OCS, the contract is the product and the default interface is only one possible client of that contract. The point of this shift is to protect consumer flexibility, accessibility, and personalization as first-class design goals.

## Executive Summary

OCS starts from five convictions:

1. Software should be designed around durable contracts rather than a single mandatory interface.
2. Consumers should be able to choose or create interfaces that fit their own workflow, accessibility needs, and preferences.
3. Coding agents make custom client creation feasible enough that this design principle can now be applied broadly.
4. Durable external contracts make interchangeable skins possible without sacrificing shared state, trust, or policy enforcement.
5. Consumers have situated knowledge of their own needs, and software should let them apply that knowledge through replaceable interfaces rather than forcing them into a producer-defined experience.

OCS is not just "software with APIs." It is software architected so that client replaceability is a first-class product property rather than an accidental side effect.

## 1. Purpose And Scope

Open Consumer Software is first and foremost a design standard for consumer-facing software in the LLM era.

It also functions as:

- a product architecture model
- a design philosophy
- a conceptual framework
- a basis for future technical and product standards

OCS is not a formal protocol specification. It defines how software should be built when personalized interfaces are finally practical.

`SKILL.md` is the agent-first operational translation of this standard. This README defines the doctrine. The skill applies it in agent workflows.

## 2. The Problem

Most software today is consumer-facing but producer-controlled at the interaction layer. Even when products expose APIs or integrations, users are still expected to use the official application for core workflows. As a result:

- the interface becomes a point of lock-in
- accessibility and workflow needs are constrained by vendor priorities
- product innovation is bottlenecked by first-party UI teams
- third-party builders operate on incomplete or unstable contracts
- user choice exists in theory more often than in practice

This model made sense when building and maintaining software clients was expensive. That condition is changing. Software design should change with it.

## 3. Consumer Sovereignty And Situated Knowledge

OCS starts from the premise that consumers often understand their own circumstances better than producers can. A producer can provide durable capabilities, trustworthy contracts, and safe policy boundaries, but it cannot anticipate every workflow, accessibility need, operating context, team habit, device constraint, or local problem a consumer faces.

A single first-party interface must generalize across many users. That generality is useful, but it is also a limit. When the interface is mandatory, consumers are forced to adapt their work to the producer's chosen environment. When the rails are exposed without client lock-in, consumers can build, choose, or modify skins that fit the circumstances they actually live in.

OCS therefore treats consumer sovereignty as a product architecture concern. The producer enables the capability layer; the consumer retains meaningful agency over how those capabilities are experienced and applied.

## 4. Why Now

Several forces make OCS practical now in a way that it was not previously:

- APIs, SDKs, CLIs, and event-driven architectures are more mature than in earlier software eras
- typed schemas and machine-readable contracts make systems easier to compose reliably
- cloud identity, policy, and audit systems are good enough to support many clients on shared rails
- coding agents drastically reduce the cost of building task-specific interfaces
- users can now participate more directly in shaping their software environment

Coding agents are not the whole story, but they are a major accelerator. They reduce the practical cost of skin creation from a specialist project to a routine workflow. That changes what software producers can reasonably be expected to support.

This shift is already visible among high-agency users. Developers and other power users increasingly avoid the default interfaces of task systems, cloud platforms, internal tools, and SaaS products, instead composing personal workstations from APIs, CLIs, scripts, agents, and small custom clients. These workstations are not novelty projects. They become everyday operating environments shaped around the individual's actual way of working.

OCS names this shift and argues that software should be designed for it intentionally, rather than forcing it to emerge through workarounds.

## 5. Canonical Definition

Open Consumer Software is a design standard in which software is built as durable rails for independent skins, so consumers can choose, build, replace, and personalize how they use a product without losing access to the underlying service, identity, data, or policy model.

The shortest way to say it is this:

Short form:

> Open Consumer Software is software built as stable rails for interchangeable skins.

Expanded form:

> Open Consumer Software applies to products whose core value is exposed through durable external contracts, allowing multiple clients to operate over the same capabilities, state, permissions, and policy boundaries.

OCS does not require a producer to ship multiple first-party skins. It requires the producer to make independent skin-building technically and legally possible.

## 6. Terminology

### OCS

The software paradigm defined here.

### Producer

The entity that operates the underlying service, capability layer, and trust boundary.

### Consumer

The person, team, or organization using the software and potentially choosing, modifying, or building its interface layer.

### Rails

The durable capability layer exposed by the producer. Rails include APIs, SDKs, CLIs, schemas, auth, permissions, state models, webhooks, event streams, audit surfaces, compatibility policies, and other contract-bearing surfaces.

### Skin

A client interface that operates against the rails. A skin may be graphical, conversational, voice-based, terminal-based, automated, embedded, or agent-generated. A first-party client is a skin. A third-party client is a skin. A personal client is a skin.

### Contract

The externally consumable definition of how capabilities, objects, identities, policies, and outcomes are represented and accessed.

### Essential Workflow

The core actions a user must be able to perform in order to use the product for its primary purpose. Essential workflows include the main operations that define the product's utility, not every convenience feature of the first-party interface.

### Interchangeability

The property that multiple skins can access the same underlying product without forcing users to abandon their state, permissions, history, or core capabilities.

### Consumer Openness

The ability of consumers to choose, build, replace, and combine skins on top of a producer's rails.

The word "open" in OCS refers primarily to consumer openness at the interaction layer. It does not, by itself, require open source licensing, open governance, or fully public infrastructure. It means the consumer is not confined to a single vendor-controlled interface.

## 7. The Core Model

OCS separates a software product into two layers.

### 7.1 Rails

The rails define what the product can do.

They typically include:

- capability endpoints
- typed objects and schemas
- command surfaces
- authentication and authorization semantics
- event and webhook systems
- policy and compliance controls
- auditability and observability surfaces
- compatibility guarantees

The rails are the durable substrate of the product.

### 7.2 Skins

The skins define how the product is experienced.

They may include:

- web apps
- native apps
- terminal clients
- chat-based agents
- voice interfaces
- automations
- browser extensions
- internal team tools
- specialized accessibility clients

The essential characteristic of a skin is not its form factor but its replaceability.

### 7.3 Outcomes

An outcome is the result of executing a capability through any skin. In OCS, outcomes must resolve against the same underlying rails so they can remain understandable, auditable, and consistent regardless of client.

### 7.4 Trust Boundary

The trust boundary is controlled by the producer, not by any single skin. A skin can shape the experience of the product, but it must not redefine the core semantics of permissions, policy, or state integrity.

## 8. Normative Requirements

The minimum requirements for a product to qualify as OCS are below. The terms MUST, SHOULD, and MAY are used in their normative sense.

### 8.1 Required Properties

A product claiming to be OCS MUST satisfy all of the following:

1. Contract-first design.
   The product MUST expose durable external contracts for its primary capabilities rather than relying on unofficial or incomplete access paths.
2. Independent skin viability.
   The product MUST make it technically possible for third parties and consumers to build viable skins for important user workflows.
3. Shared state model.
   All compliant skins MUST operate against the same underlying accounts, identities, objects, and system state.
4. Permission consistency.
   Authorization and policy semantics MUST be enforced at the rails layer rather than delegated to individual skins.
5. Outcome consistency.
   Equivalent actions taken from different skins MUST produce compatible system outcomes.
6. No required first-party gateway.
   The official client MUST NOT be the only path for essential user operations unless those operations are explicitly outside the product's public capability scope.
7. Stable compatibility policy.
   The producer MUST publish versioning, deprecation, and compatibility expectations for contract-bearing surfaces.
8. Legal and policy permission.
   The producer MUST provide terms and policies that allow third-party and consumer-built skins to exist without relying on informal tolerance, private exceptions, or discriminatory restrictions.

### 8.2 Strong Recommendations

A product aligned with OCS SHOULD also provide:

- machine-readable schemas
- typed SDKs
- CLI parity for important workflows
- test or sandbox environments
- event streams or webhooks
- audit and observability mechanisms
- reference clients or starter skins
- policy documentation for third-party and agent-built skins

### 8.3 Optional Extensions

An OCS system MAY additionally support:

- skin marketplaces
- declarative client templates
- agent-native interface generation
- composable multi-provider skins
- portable user interface state

## 9. Qualification Test

A product is OCS only if the answer to the following questions is yes:

- Can an external builder create a capable client without reverse engineering?
- Is independent skin-building allowed by the product's technical and legal terms?
- Can a consumer switch skins without losing account continuity, data continuity, or core capabilities?
- Are permissions and policies enforced by the rails rather than trusted to the skin?
- Are the most important workflows available through durable public contracts?
- Can multiple skins coexist over the same product state?
- Does the official application act as a reference client rather than a mandatory gateway?

If any of these fail materially, the product may be extensible or API-enabled, but it is not yet OCS.

### 9.1 OCS-Native Design Checklist

The OCS-Native design checklist applies to new products, systems, and major features that should align with OCS.

- Build the product around durable external contracts, not a single UI.
- Make independent skin-building technically possible without reverse engineering.
- Make independent skin-building legally and by policy possible, not just informally tolerated.
- Keep accounts, identity, objects, and state shared across skins.
- Enforce permissions, policy, and integrity at the rails layer.
- Ensure equivalent actions across skins produce compatible outcomes.
- Avoid reserving essential workflows for the first-party client alone.
- Publish compatibility, versioning, and deprecation expectations.
- Treat the official client as a reference implementation, not the only legitimate interface.
- Design for consumer modification, replacement, and personalization from the start.

### 9.2 Not OCS If

An OCS claim should be rejected if any of the following are true:

- the official application is still the only meaningful way to use the product
- alternative skins depend on private or unstable access
- third-party or consumer-built skins are blocked by terms or policy
- permissions or policy are enforced inconsistently across skins
- users lose continuity of identity, data, or core capability when switching skins
- the interface layer is open in theory but closed in practice

## 10. What OCS Is Not

OCS is not equivalent to any of the following:

### 10.1 Open Source Software

Open source concerns software licensing and code availability. OCS concerns interaction-layer openness and client replaceability. A system can be OCS without being open source. A system can be open source without being OCS.

### 10.2 API-First Software

API-first software emphasizes external programmability. OCS goes further by requiring that important product workflows remain viable across interchangeable clients sharing the same state and trust model.

### 10.3 Headless Software

Headless systems separate backend and presentation layers, but they do not necessarily provide consumer replaceability, stable multi-client interoperability, or a shared trust model for broad client ecosystems.

Headless software separates capability from presentation. OCS makes that separation available to consumers, communities, third parties, and agents as a legitimate mode of use. A headless system with restrictive enterprise contracts, selective access, or legal limits on independent clients may be architecturally decoupled, but it is not OCS if consumers cannot reasonably choose, build, or adopt alternative skins for essential workflows.

### 10.4 Plugin Platforms

Plugin systems extend a host application. OCS allows the host application itself to be replaceable.

### 10.5 White-Labeled SaaS

White-label products allow branding variation. OCS allows interaction variation with durable contract-level compatibility.

### 10.6 Protocol Networks

Protocols often standardize interoperability across many providers. OCS can exist on top of a single provider if that provider exposes stable rails and supports interchangeable skins. OCS is therefore compatible with protocol-based systems but not dependent on them.

## 11. Trust, Safety, And Governance

OCS must define how consumer freedom coexists with safe, reliable operation. Without this, OCS collapses into unsafe client fragmentation. OCS is not an argument for chaos. It is an argument for accountable openness.

### 11.1 Producer Responsibilities

The producer MUST remain responsible for:

- identity integrity
- permission enforcement
- policy enforcement
- auditability of important actions
- abuse detection and response
- data integrity
- compatibility management

### 11.2 Skin Responsibilities

Skins SHOULD be expected to:

- accurately represent actions and permissions
- avoid deceptive or manipulative interaction patterns
- disclose their identity and level of trust
- respect producer-enforced policy boundaries
- preserve reliable user intent during execution

### 11.3 Governance Questions

A future formal OCS standard should define positions on:

- skin certification
- trust labels and reputation systems
- revocation and abuse handling
- disclosure requirements for agent-built skins
- accessibility and consumer protection requirements
- liability boundaries between producers and skin builders

## 12. Why OCS Matters

OCS matters because it reframes software around the interests of the consumer without discarding the responsibilities of the producer.

### 12.1 For Consumers

Consumers gain:

- more control over workflow and interface design
- better accessibility and personalization
- less dependence on a single official application
- more ability to apply their own circumstantial knowledge to software use
- more room for specialized and context-specific experiences
- a more durable relationship to the underlying product capabilities
- a legitimate path to create their own skins without needing to own the entire stack
- closer proximity between real user needs and interface experimentation

### 12.2 For Producers

Producers gain:

- a clearer separation between capability design and interface design
- stronger incentives to invest in durable, trustworthy rails
- more room for experimentation without redefining the core product each time
- a broader surface for community-driven experimentation, revealing new workflows and capabilities the producer can later formalize in the rails
- a healthier long-term relationship with consumers based on capability trust rather than interface lock-in

## 13. Maturity Model

Not every product moves toward OCS in the same way or at the same pace. The maturity model below classifies progress.

The key distinction at the top end is this:

- OCS-Native means the product is designed correctly for OCS.
- OCS-Complete means the surrounding ecosystem, governance, and consumer choice are mature in practice.

### Level 0: Closed Application

The official interface is effectively the only meaningful way to use the product.

### Level 1: API-Enabled

The product exposes APIs or integrations, but core workflows still depend heavily on the official client.

### Level 2: OCS-Adjacent

External builders can create useful clients, but compatibility, permissions, or workflow completeness remain partial.

### Level 3: OCS-Compatible

Most important workflows are available through durable contracts, and multiple skins can operate over shared accounts and state with consistent outcomes.

### Level 4: OCS-Native

The product is intentionally designed around durable rails and independent skins. The official client is a reference implementation, while the broader skin ecosystem can be built by consumers, third parties, or the producer. At this level, the architecture and product philosophy are OCS by design, even if the surrounding skin ecosystem is still early.

### Level 5: OCS-Complete

The product supports a robust ecosystem of interchangeable skins, strong policy enforcement, formal compatibility guarantees, and durable consumer choice at scale. At this level, OCS is not just a product design principle but a mature operating reality.

## 14. Examples, Non-Examples, And Borderline Cases

OCS is most useful when it can classify cases cleanly.

### 14.1 Real-World Mappings

These are not perfect examples of OCS. They are grounding references that help locate the idea relative to systems people already understand.

#### Email Clients

Email demonstrates an older form of interface plurality. Many clients can operate over the same underlying account and message state. This shows that shared rails and many skins are possible, but email is not OCS in the full sense because OCS is not just a protocol pattern. It is also a product design standard for modern software services.

#### Headless Commerce And Headless CMS

These systems show that backend and presentation can be separated cleanly. They are useful precedents, but they are not automatically OCS because many of them are still merchant-facing or developer-facing architectures rather than consumer-facing ecosystems of interchangeable skins.

#### API-First SaaS Products

Many modern SaaS products expose APIs, SDKs, and automations. They become OCS only when those external surfaces are sufficient for consumers and communities to build viable skins for important workflows without relying on the official client as a permanent gateway.

#### Plugin-Based Platforms

Extensible platforms demonstrate that products can support third-party innovation. They are not OCS when the host interface remains mandatory and third parties can only decorate or extend the official client rather than replace it.

### 14.2 OCS-Native Example

A product exposes full capability contracts, shared account state, consistent permissions, eventing, versioning, and a first-party client that is fully replaceable by third-party or consumer-built skins, even if the broader ecosystem around those skins is still emerging.

### 14.3 OCS-Compatible But Incomplete

A product has strong APIs and SDKs, and several external clients exist, but some critical workflows still require the official app.

### 14.4 Not OCS: Extensible Host Application

A product supports plugins, but all meaningful workflows must still pass through the host application's interface.

### 14.5 Not OCS: Headless Backend Only

A system exposes backend services but provides no durable consumer-facing model for interchangeable skins over shared user state and trust boundaries.

### 14.6 Borderline Cases

A product allows automation and custom dashboards but does not yet expose enough contract surface for full client replaceability. This is adjacent to OCS, not OCS itself.

A product exposes a public API, but its terms prohibit alternative clients or reserve key workflows for the first-party app. This is not OCS, because the legal or technical conditions for independent skins are missing.

A product allows third-party clients, but permissions, policy, or state integrity are enforced inconsistently across skins. This is not OCS, because interchangeable usage is not actually reliable.

A product supports many skins, but each skin depends on private undocumented access or periodic break-fix reverse engineering. This is not OCS, because the rails are not durable.

## 15. Strategic Implications

Taking OCS seriously as a design paradigm creates several shifts:

- software can be designed around durable capability rails instead of a single mandatory UI
- first-party applications can be treated as reference clients rather than permanent gateways
- consumer circumstantial knowledge can shape the interface layer directly
- accessibility, workflow fit, and personalization can be designed in from the start
- interface innovation can happen without forcing every user into the same experience
- agent-generated clients can become a legitimate part of software usage rather than a workaround

OCS also creates business model pressure. Products that depend on interface lock-in, attention capture, upsell placement, or first-party workflow control may resist interchangeable skins. OCS-aligned producers need models that monetize durable capability access, trust, reliability, policy enforcement, compatibility, and ecosystem participation rather than exclusive control of the interface.

Interfaces still matter. They just stop being singular.

## 16. Design Implications For Product Teams

Building toward OCS changes what teams should optimize for.

Teams must think in terms of:

- durable semantics over temporary UI flows
- permission and policy enforcement at the rails layer
- versioning and compatibility as product features
- auditability across many clients
- testability for third-party and agent-built skins
- consumer adaptation as a legitimate product outcome
- clear separation between capability design and interface design

In an OCS world, the question is no longer:

> How do we get every user into our interface?

It becomes:

> How do we make our capabilities safely usable through independent skins?

## 17. Why This Should Become A Standard

OCS should become a design standard because it treats consumer flexibility and personalization as first-class requirements rather than afterthoughts.

### 17.1 Consumer Flexibility

Users should not be permanently confined to one vendor-controlled interface when the underlying product can be made available through durable rails.

OCS does not require every producer to build many interfaces themselves. It requires producers to stop designing products as though only their own interface is legitimate.

### 17.2 Accessibility And Personalization

Different users need different interfaces. Accessibility, language, workflow, cognitive style, device constraints, and personal preference all shape how software should be experienced. OCS treats that variation as legitimate.

### 17.3 Consumer Sovereignty

Consumers should not have to adapt indefinitely to a producer-defined environment when the underlying capabilities can be safely exposed through durable rails. OCS treats consumers as situated problem-solvers with legitimate knowledge of their own needs, not merely as users of a generalized interface.

### 17.4 Responsible Design In The LLM Era

Coding LLMs and tooling make it realistic to create high-quality custom clients quickly. Once that becomes feasible, software producers have a stronger responsibility to expose durable contracts rather than assume one default UI should govern every user forever.

### 17.5 Durable Consumer Rights

Consumers benefit when access to software capabilities is more durable than any one interface. OCS preserves continuity across changing tools, devices, and interaction paradigms.

### 17.6 Better Software Architecture

Designing for interchangeable skins forces clearer contracts, stronger policy enforcement, and better separation between capability and presentation. These are healthy constraints for modern software systems.

### 17.7 Not Chaos, But Accountable Openness

OCS does not mean every client can behave arbitrarily. The rails still define permissions, policy, auditability, and trust boundaries. The point is not to remove responsibility from producers. It is to stop interface control from becoming the default mechanism of product control.

## 18. Path Forward

If OCS is to become a serious design movement rather than a slogan, the next stages should include:

1. A stable terminology document.
2. A shared set of qualification criteria.
3. Reference architectures for OCS-Native systems.
4. Example contracts and implementation patterns.
5. Governance guidance for trust, safety, and certification.
6. Public case studies showing what responsible OCS design looks like in practice.

OCS becomes more durable as an industry concept as these next stages are formalized over time.

## 19. Thesis

The dominant software model of the last era was one product, one interface, one controlled workflow.

The emerging model is different:

- one capability layer
- many interfaces
- durable contracts
- consumer choice
- agent-assisted personalization

That is Open Consumer Software: designing software this way on purpose.

## Repository Governance

The repository includes lightweight public project files:

- `CONTRIBUTING.md` for contribution expectations
- `GOVERNANCE.md` for current decision-making and project status
- `SECURITY.md` for reporting safety, packaging, or guidance issues
- `CHANGELOG.md` for release history
- `CODE_OF_CONDUCT.md` for participation expectations

## License

The package is licensed for reuse, redistribution, and adaptation under CC BY 4.0. See `LICENSE`.
