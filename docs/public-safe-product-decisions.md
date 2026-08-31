# Public-safe product decisions

This document distills product decisions from the reviewed private product baseline into a public portfolio artifact. It intentionally excludes the private implementation, real student submissions, school data, credentials, provider secrets, internal URLs, and copyrighted source materials.

## Product scope

The product supports two user-facing roles:

- Student: identity verification, submission, status visibility, and published result viewing.
- Teacher-admin: course scope, assessment configuration, rubric management, review, release, correction, and export.

AI and background workers are processing actors, not end-user roles. The teacher remains the final decision-maker.

## Core workflow

```
Draft
  → Submitted
  → Parsed / Partially parsed / Manual handling
  → Similarity risk check
  → AI preliminary assessment
  → Teacher review
  → Confirmed
  → Released
  → Corrected (versioned)
```

Draft content is not scored or similarity-checked. Only the current valid submitted version enters downstream processing. Historical versions are retained for traceability and are never silently overwritten.

## Product invariants

1. Server time is the authority for opening, deadline, auto-submit, and lock behavior.
2. Assessment, grading, release, and correction are scoped to one course and one assessment project.
3. Similarity is risk evidence, not an automatic misconduct conclusion or automatic score deduction.
4. An AI score is a draft assessment, not a final grade.
5. A teacher override, release, reopen, or post-release correction requires a reason and an audit record.
6. Release must not expose a partial or unreviewed batch as a completed result.
7. Asynchronous parsing, similarity, grading, and export jobs are idempotent and recoverable.
8. Formal AI grading requires a captured model/provider version and parameter snapshot; a floating alias is not sufficient evidence.
9. Large files are safely parsed and reduced into structured evidence before model processing; raw archives are not sent directly to the model.
10. Budget, rate-limit, provider failure, and malformed output states fail closed or route to human review rather than silently generating a default score.

## Review and release gates

The product makes the following visible to teachers:

- rubric criteria and weights;
- evidence locations supporting each draft score;
- parsing or extraction exceptions;
- confidence and review-needed state;
- similarity risk state without exposing unnecessary identities;
- teacher edits and final score;
- release readiness and unresolved blockers;
- version history after a correction.

A release can be blocked by a missing final score, unresolved critical parsing evidence, or a policy-defined unresolved risk. A teacher can make an explicit, reasoned decision when the policy allows an override.

## Public evidence and limits

The public repository contains curated product documents, state logic, synthetic examples, and an offline/local review story. It does not claim production scale, external student outcomes, autonomous grading, or school-system deployment.

The private source baseline was used to sharpen the public product case; the private codebase and source data remain private.
