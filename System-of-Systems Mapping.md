# System-of-Systems Mapping (Planes Model)

Status: Descriptive
Authority: None (non-normative)
Mutability: Controlled (may evolve without changing contracts)

This document describes how the Contract Stack relates to the wider system-of-systems.
It does not declare new permissions, constraints, or precedence rules.

All enforcement authority remains in the Contract Stack artifacts (RCN, derived nodes, regression gates, and change control).


## Plane 1 — Source of Truth

What lives here:
- Canonical contract artifacts (RCN, derived node specs, checklists)
- Registries and indexes (e.g., Contract Stack Index)
- Schemas / formats that define valid structure
- Versioned documents intended to be referenced, not reinterpreted

Rule:
- Truth is not generated. It is stored.
- Downstream systems may reference this plane but must not rewrite it.


## Plane 2 — Governance & Enforcement

What lives here:
- Regression gates (adversarial packs + expected response rules)
- Integration scans
- Freeze / bake / version protocols
- Diffing and change-control mechanisms
- Auditability and mechanical visibility of violations

Rule:
- No change becomes “true” without passing governance.
- Compliance is measured mechanically, not assumed via discipline.


## Plane 3 — Admissibility Contracts

What lives here:
- Non-agentic / non-teleological boundaries
- Human authority boundary
- Admissible outputs constraints
- Optimism immunity constraints
- Termination / stop rules

Rule:
- These constraints define what is allowed to exist downstream.
- If a downstream behavior conflicts with this plane, the downstream behavior is invalid.


## Plane 4 — Derivation Constraints

What lives here:
- Derived nodes that transform intent into constrained artifacts (e.g., D1 Intent Translation)
- Rules that specify what derived outputs may contain
- Constraints that prevent hidden teleology, advice, or authority leakage during derivation

Rule:
- Derived nodes may translate and structure information only within admissible bounds.
- Derived nodes do not “improve” intent, select outcomes, or generate purpose.
- Any downstream node depending on non-compliant derived output is invalid.


## Plane 5 — Explicit Non-Scope

What lives here:
- A clear list of what the system does not do
- Prohibitions against interfaces, agent behavior, workflow execution, or decision-making inside the Contract Stack
- Statements that prevent the repo from becoming an implementation surface

Rule:
- The Contract Stack produces constraints, not solutions.
- Anything that implements user-facing behavior belongs outside this repository.


## Relationship Summary

- Plane 1 stores canonical artifacts.
- Plane 2 enforces compliance and controls change.
- Plane 3 defines admissibility and boundaries.
- Plane 4 defines constrained derivation steps (nodes).
- Plane 5 prevents scope creep and implementation drift.

The Contract Stack repository is a governance-first substrate:
it bounds what downstream systems are allowed to do and makes violations inspectable.


## Practical Usage

Use this document to answer:
- “Where does this artifact belong?”
- “Is this change governance or implementation?”
- “Does this belong in the Contract Stack repo or outside it?”

Do not use this document to:
- Introduce new constraints
- Reinterpret RCN or derived node specs
- Override regression gates or change control
