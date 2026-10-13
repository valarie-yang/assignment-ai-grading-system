# AI Assignment Grading Assistant

A teacher-in-the-loop prototype for turning assignment requirements into a reviewable rubric, then drafting criterion-linked AI scoring suggestions for teacher review.

![AI assignment grading workflow](https://raw.githubusercontent.com/valarie-yang/valarie-website/main/assets/ai-assignment-grading-flow-mobile.svg)

## Product hypothesis

Teachers may benefit from a consistent way to move from assignment requirements to explicit scoring criteria and evidence-linked preliminary feedback. This is a product hypothesis—not a finding from user interviews, classroom research, or measured time savings.

## Workflow

1. Import or enter the final assignment requirements.
2. Generate a draft rubric from those requirements.
3. A teacher reviews and locks the rubric.
4. Submit student work for AI preliminary scoring against the locked criteria.
5. Review the criterion-linked score suggestions and evidence; edit or override as needed.
6. A teacher confirms the final grade.

Rubric approval and locking is a prerequisite for AI preliminary scoring. It is intended to keep the scoring basis explicit; it does not eliminate bias or guarantee accurate grading.

## What the current prototype supports

- A browser-based workbench for assignment/rubric and submission review.
- Rubric drafting from assignment requirements, followed by a teacher approval gate.
- Criterion-organized AI preliminary scoring with teacher review and final confirmation.
- Local data handling in the browser-based implementation; AI scoring requires a separately configured local bridge.

The public page shows the workbench interface. It is not a visitor-operated cloud grading service. When AI scoring is enabled, submission text, assignment name, and rubric are sent through the local bridge to the configured model provider. Use only authorized or synthetic work and review the provider's data terms. The public repository is a curated portfolio package; it does not mirror the private/local product source.

## Product decisions

- **Rubric first:** make the assessment basis explicit before AI scoring.
- **Evidence over a bare score:** attach suggestions to criteria and response evidence so the teacher can inspect them.
- **Human authority:** AI produces preliminary suggestions; the teacher edits and confirms the final grade.
- **Bounded deployment:** distinguish a publicly viewable page from the local model/API bridge needed for scoring.

## Validation still needed

Accuracy, reliability, teacher review time, rubric edits, override rates, and classroom adoption have not been validated. Next tests should use authorized or synthetic submissions, teacher-defined answer keys, repeated model runs, and review-time observations. Proposed measures are not results.

## Early API cost observation

Author-reported mean from a small-scale test setup: approximately **CNY 0.2 per assignment** for DeepSeek API calls. The sample size and call scope are not standardized; this is not a quote, benchmark, quality claim, or guarantee. Cost varies with the model, assignment length, prompt, and retries.

## Public-data boundary

This repository contains public-safe product, workflow, evaluation, and synthetic-demo materials—not student records, credentials, internal deployment details, or the complete private source. Do not publish real student submissions, API keys, or confidential course content.

## About this portfolio case

I framed the product hypothesis, designed the teacher-controlled workflow, and built the prototype through AI-assisted coding. This demonstrates product framing and prototype execution; it does not claim a validated classroom outcome or production-scale service.
