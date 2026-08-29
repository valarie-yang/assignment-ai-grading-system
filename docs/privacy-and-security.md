# Privacy and security boundary

## Safe to publish

- Product requirements and workflow diagrams.
- Domain schemas without real identities.
- Synthetic student, rubric, and submission fixtures.
- Screenshots or recordings with synthetic content.
- Evaluation methodology and negative cases.
- Local verification commands and non-sensitive output.

## Never publish

- API keys, access tokens, cookies, or credentials.
- Real student names, IDs, submissions, grades, or feedback.
- Private employer source code, internal URLs, configuration, or database exports.
- Production object-storage links or connection strings.
- Logs containing prompt content or personal data.

## Production-minded controls

A real deployment would need authenticated sessions, least-privilege roles, input and file validation, encrypted transport and storage, secrets management, retention/deletion rules, audit events, rate limits, monitoring, incident response, and a documented data-processing basis.

This repository is a portfolio artifact. The controls above are design requirements and release gates, not a claim that this public package is a production service.
