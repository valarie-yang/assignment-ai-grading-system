# Architecture and state model

## Domain model

    Course
      └── Assignment
            └── Rubric
    Student
      └── Submission
            └── AIAssessment
                  └── TeacherReview
                        └── FinalGrade

Important relationships:

- A submission belongs to one assignment and student.
- An AI assessment references the submission, rubric version, prompt version, and model version when available.
- A teacher review references the AI assessment but is independently editable.
- A final grade is released only from the reviewed assessment state.

## Submission lifecycle

    DRAFT → SUBMITTED → AI_ASSESSED → TEACHER_REVIEW → REVISED → RELEASED

Failure and control paths:

- SUBMITTED → VALIDATION_FAILED
- AI_ASSESSED → AI_FAILED
- TEACHER_REVIEW → NEEDS_REVISION
- any non-released state → WITHDRAWN, subject to retention rules

## Service boundaries

- Intake boundary: authenticated submission and file validation.
- Domain boundary: assignments, rubrics, submissions, assessments, reviews, and reports.
- AI boundary: provider adapter, structured response validation, timeout and failure handling.
- Release boundary: teacher authorization and audit event before final publication.
- Storage boundary: protected object storage for files and a database for metadata and workflow state.

## Production release gates

Before a production claim would be appropriate, the implementation would need verified identity/session controls, role authorization, encrypted database and object storage, retention and deletion policy, immutable model-version capture, prompt/configuration versioning, observability, and an operational recovery plan.
