# Product brief

## Users

- Teachers and graders who need a consistent first pass across many submissions.
- Students who need a transparent explanation of rubric-based feedback.
- Course and program administrators who need controlled reports and audit trails.

## Job to be done

Given a course assignment and a validated rubric, help a teacher move from submission intake to a reviewable preliminary assessment without allowing an unverified model output to become the final grade.

## MVP scope

1. Create course, assignment, roster, and rubric.
2. Validate criterion weights and score ranges.
3. Import synthetic roster and submission fixtures.
4. Save a draft and submit a versioned attempt.
5. Request a structured AI preliminary assessment.
6. Validate the returned object.
7. Let a teacher review, edit, or override.
8. Export a final report only after review.

## Product decisions

- Rubrics are first-class product objects, not prompt text hidden from the user.
- AI output is a draft assessment, not an authoritative grade.
- Human review is part of the happy path, not an exception path.
- A failed or malformed AI response must not write a final grade.
- Production release requires evidence for privacy, identity, storage, retention, model version, and observability.

## Non-goals

This public case does not claim to provide a learning-management-system replacement, plagiarism detection, institutional policy decisions, automatic final grading, or a production-grade model evaluation service.
