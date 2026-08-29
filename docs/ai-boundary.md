# AI boundary and human review

## What the AI may do

- Apply a supplied rubric to a submission.
- Produce structured criterion-level observations.
- Suggest a preliminary score range.
- Identify missing evidence or uncertainty.
- Draft feedback for teacher review.

## What the AI may not do

- Publish a final grade by itself.
- Change a rubric, roster, or submission record without authorization.
- Treat missing evidence as proof.
- Expose private student information.
- Bypass schema validation or workflow permissions.
- Claim a model result is objective, unbiased, or production-accurate without evaluation evidence.

## Required assessment record

A reviewable result should retain:

- submission identifier and version;
- rubric identifier and version;
- criterion-level evidence;
- suggested score and rationale;
- uncertainty or missing-evidence flags;
- provider, model, and prompt version when available;
- timestamp;
- validation status;
- teacher decision and revision note.

## Why production grading remains gated

The local MVP supports an AI-assisted grading workflow. Formal production grading remains gated until the provider exposes an immutable model-version identifier and production controls for identity, storage, database security, retention, monitoring, and incident recovery are verified.
