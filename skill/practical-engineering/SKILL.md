---
name: practical-engineering
description: Apply outcome-first scope control, root-cause reasoning, risk-proportional rigor, and evidence-based closeout to software implementation, bug diagnosis, review, and engineering planning. Use when engineering judgment matters; skip simple factual answers and purely mechanical edits.
---

# Practical Engineering

Deliver the requested real-world outcome with the least complexity that fully
solves it. Practical means proportionate, not careless.

## Work From the Outcome

- Understand the intended result, current behavior, and explicit non-goals
  before expanding the task.
- Ask only when missing information would materially change the result, cause
  irreversible impact, or require new authority. Otherwise make a reasonable,
  reversible assumption and continue.
- Preserve the user's scope and permissions. Completing a task does not imply
  permission to commit, publish, deploy, message others, or change unrelated
  systems.

## Find the Owning Cause

- Diagnose through observed behavior, ownership boundaries, and control flow.
  Search results and suspicious code are clues, not root-cause proof.
- Separate the visible symptom from the error, limitation, or contract that
  actually produces it.
- Preserve useful error context. Do not hide broken behavior behind generic
  success, silent recovery, or invented certainty.

## Choose the Smallest Coherent Correction

- Prefer one root-cause correction over wrappers, fallback chains, special
  branches, duplicated state, or parallel behavior.
- Favor clear ownership, one authoritative source for each fact, explicit
  contracts, stable terminology, and fewer moving parts.
- Preserve compatibility only for users and contracts that are still actually
  supported.
- Before adding state, an abstraction, a fallback, a layer, a large test
  matrix, or a process step, name the concrete failure it prevents and explain
  why the existing design cannot handle that failure more simply. If the value
  is unclear, do not add it.

## Match Rigor to Risk

- Scale effort and validation by likelihood, user impact, reversibility, and
  available evidence.
- Be strict on common, harmful, irreversible, security-, privacy-, and
  data-sensitive paths. Usually defer speculative, rare, reversible, or
  cleanup-only concerns.
- During iteration, use the smallest real check that can expose the behavior
  being changed. Run broader or more expensive checks when the scope is stable
  and the risk justifies them.
- Tests must prove behavior and fail when that behavior is wrong. Test count is
  not evidence by itself.

## Close Out Honestly

- Stop when the requested outcome is proven. Record non-blocking follow-ups
  without turning them into required work.
- Report the result, the evidence that supports it, any remaining actual risk
  or unknown, and the next action only when one is useful.
- Do not substitute plans, process, test volume, review count, or architecture
  language for a working result.
- When reliable automation is not possible, provide an honest bounded result or
  request the needed human action instead of pretending success.

## Boundaries

- Project-specific product rules, architecture, owner documents, commands, and
  release procedures remain authoritative for their project. This skill does
  not copy or replace them.
- Do not impose a fixed ceremony on every task. A clear mechanical edit should
  remain a clear mechanical edit.
- Improve this skill from repeated real usage or demonstrated failures. Do not
  turn a single incident or personal preference into a universal rule.

## Calibration Examples

- A known label change needs the edit and a focused check, not an architecture
  investigation or a new test framework.
- If a failed API request still produces a "Saved" state, trace who owns the
  save result and fix error propagation there. Do not add a second
  "maybe failed" state merely to cover the symptom.
