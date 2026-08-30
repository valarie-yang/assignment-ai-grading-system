# Public release checklist

This checklist applies to the curated public portfolio package. It is not a production deployment checklist.

## Before every public commit

- [ ] No real student, teacher, institution, submission, grade, or directory data.
- [ ] No API keys, credentials, tokens, cookies, private URLs, or environment files.
- [ ] No private implementation, local runtime, database, backup, log, or generated export.
- [ ] No textbook, exam, licensed, or third-party asset without explicit publication rights.
- [ ] README labels each artifact as `implemented`, `locally verified`, `proposed`, or `production gated`.
- [ ] Synthetic fixtures are clearly marked and contain no reversible identifiers.
- [ ] Links resolve to public-safe files only.
- [ ] A clean-snapshot review has been completed.

## Claims gate

Do not claim production scale, model accuracy, external user outcomes, formal school deployment, or regulated compliance unless there is a separately reviewable source of evidence and authorization.

## Evidence package

The preferred public evidence chain is:

`product problem → workflow/state model → AI boundary → synthetic example → evaluation plan → human review/release gate`

Private engineering depth may be discussed in an interview, but is not implied by this public repository.
