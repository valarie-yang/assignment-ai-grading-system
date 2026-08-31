# Public release scan

Scan date: 2026-08-31

Scope: public `main` branch, README, docs and assets.

Checks completed:

- No `.env` file or credential-like filename appears in the current public tree.
- Searches for `BEGIN PRIVATE KEY`, `ghp_`, `sk-`, `api_key`, `localhost`, `127.0.0.1`, internal host patterns and email-address patterns returned no matches.
- Public release, data-classification, privacy, security and threat-model documents exclude student data, real submissions, credentials, internal configuration and private implementation.

Limit: this is a current public snapshot review; it is not a replacement for GitHub Secret Scanning history or a full historical commit audit.
