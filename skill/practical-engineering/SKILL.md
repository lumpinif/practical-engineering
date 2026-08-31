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
- Find discoverable facts in the code, configuration, current behavior, and
  authoritative sources yourself. Ask only for unavailable knowledge, a
  material decision, or new authority; do the safe preparation and present the
  evidence and recommendation first. Otherwise make a reversible assumption.
- Preserve the user's scope and permissions. Completing a task does not imply
  permission to commit, publish, deploy, message others, or change unrelated
  systems.

## Respect User Expectations

- Treat user-visible behavior as incorrect when it is internally valid but
  violates a reasonable expectation created by its wording, appearance,
  location, the product's own behavior, or established platform and domain
  conventions.
- Start from what the target user would reasonably predict. Keep the same
  concept consistent, prefer familiar interactions when they already work, and
  verify conventions in the product's actual platform and context.
- Depart from an established expectation only when a concrete user benefit or
  constraint outweighs the learning and error cost. Make the difference clear
  before it matters, preserve feedback and recovery, and validate significant
  consequences with proportional user-facing evidence.

## Find the Owning Cause

- Diagnose through observed behavior, ownership boundaries, and control flow.
  Treat searches and smells as leads, rank confidence separately from benefit,
  and prefer a smaller proved correction over a larger guess.
- For a non-obvious bug, establish the tightest reliable feedback loop that
  exercises the reported symptom before committing to a theory. If none is
  possible, state the evidence gap and request the needed artifact, access, or
  instrumentation instead of guessing.
- Separate the visible symptom from the error, limitation, or contract that
  actually produces it.
- Preserve useful error context. Do not hide broken behavior behind generic
  success, silent recovery, or invented certainty.

## Choose the Smallest Coherent Correction

- Prefer one root-cause correction over wrappers, fallback chains, special
  branches, or parallel state. Measure simplicity by coherent obligations
  retired, not lines or files, and subtract replacement or migration machinery.
- Use the deletion test: if removing a layer spreads its rules across callers,
  complexity moved rather than disappeared. Before merging similar safeguards
  or lifecycle state, identify the owner, transition, failure window, and
  guarantee each protects; similar shape does not prove redundancy.
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
  and the risk justifies them. Report layers separately; a narrow check does not
  prove the build, integration, deployment, or user result.
- Make evidence match the user's relevant starting condition. Existing
  credentials, data, configuration, caches, or running processes can hide
  failures. When first use or cold start is part of the outcome, validate from
  a clean state and describe warm-state evidence only as what it actually
  proves.
- Test behavior at a seam that can expose it, using expected outcomes from an
  independent source. If no honest seam exists, report the limitation instead
  of adding a shallow test that creates false confidence.
- In review, assess requested-outcome correctness, user-expectation fit, and
  implementation or contract quality as distinct axes; passing one does not
  cover the others.

## Close Out Honestly

- Stop when the requested outcome is proven. An evidence-backed conclusion that
  no change is justified is also a valid result. Record non-blocking follow-ups
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

## Improve This Skill

When real use of this skill still produces an impractical or bureaucratic
result, finish the current task first, then tell the user and offer to report it
at https://github.com/lumpinif/practical-engineering/issues.

When the user is discussing this skill or reports that it behaved poorly, check
whether a newer upstream version already addresses the problem when that check
is cheap. If an update is available, tell the user and offer to install it using
their existing installation method. Do not delay unrelated work for an update
check or modify installed skills without permission.

A useful report explains the concrete task and observed behavior, the expected
practical result, why that result was missed, and how the skill's guidance was
missing, unclear, misapplied, or may have encouraged unnecessary process or
complexity. Explain why the lesson may apply across projects.

Search for an existing issue first. Never publish without the user's permission,
and remove private or project-sensitive information. Do not present a
project-specific rule, speculative edge case, or personal preference as a
universal requirement. If issue creation is unavailable, provide a short
copy-pasteable draft instead.
