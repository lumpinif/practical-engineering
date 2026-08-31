# Practical Engineering

Practical Engineering is a small Codex skill for making sound engineering
decisions without turning normal work into process theater.

It keeps attention on the requested user outcome, the real owner and control
flow behind a problem, the smallest coherent correction, risk-proportional
validation, and an honest stopping point.

## What It Is For

The skill helps with implementation, bug diagnosis, engineering review,
planning, and closeout when judgment matters. It is designed to prevent common
failure modes such as scope creep, symptom patches, duplicated state, invented
fallbacks, excessive validation, and endless cleanup after the result is
already proven.

## What It Does Not Replace

Project-specific product rules, architecture documents, owner contracts,
commands, and release procedures stay in their projects. This repository is not
a universal style guide, a testing handbook, or a library of incident-specific
rules. It does not grant permission to commit, publish, deploy, or modify
systems outside a user's request.

## Repository Layout

```text
skill/practical-engineering/
├── SKILL.md
└── agents/
    └── openai.yaml
```

The distributable skill stays self-contained and intentionally small. Project
maintenance information and version history remain outside the skill bundle.

## Maintenance

Change the skill when real usage shows that an engineering decision is
consistently wrong or unclear. Prefer a narrow correction over adding a rule for
every possible edge case.

- Keep `SKILL.md` focused on guidance that changes decisions.
- Keep project-specific facts in the project that owns them.
- Require a concrete failure before adding abstractions, states, fallbacks,
  layers, large test matrices, or process.
- Validate the skill structure with Codex's `skill-creator` validator.
- Record meaningful behavior changes in `CHANGELOG.md`; use Git history for
  implementation detail.

The project starts at `0.x` while the skill is calibrated through real use. A
release should represent a meaningful change in behavior, not routine wording
cleanup.

## Status

`0.1.0` is the initial public version. It intentionally has no scripts,
references, assets, installation automation, or project-specific rules.
