# Evaluation plan

## Current evidence

Local verification recorded:

- smoke scenarios: 5/5;
- core assessment/import/report flows: 3/3;
- JavaScript syntax checks;
- secret-scan checks;
- local bridge health check.

The counts describe the tested local scenarios only. They are not production quality claims and should be rerun when the implementation changes.

## Golden-set design

Create synthetic cases spanning:

- high, medium, and low rubric performance;
- incomplete answers;
- answers with irrelevant but fluent text;
- evidence that conflicts with the model's initial interpretation;
- malformed provider output;
- repeated runs against the same input;
- privacy-sensitive strings that must not appear in logs or output.

For every case, retain the rubric version, expected criterion evidence, acceptable score range, and an adjudicated teacher result.

## Product and model-facing metrics

- rubric criterion agreement rate;
- teacher override rate;
- unsupported feedback rate;
- evidence-grounding rate;
- score variance across repeated runs;
- grading latency;
- cost per submission;
- workflow completion rate;
- upload and grading failure rate;
- teacher time saved per assignment.

No user or production metric is claimed in this repository until it is measured and reproducible.

## Release decision

A production evaluation should report results by rubric version, model version, prompt version, cohort, and failure class. A single aggregate score is insufficient for a high-impact assessment workflow.
