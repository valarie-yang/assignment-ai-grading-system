# Threat model for the public-safe case

The case is designed around risks that matter in AI-assisted assessment workflows:

| Threat | Product control | Public evidence boundary |
|---|---|---|
| Unpublished grade is exposed | Teacher review and explicit release gate | Describe the rule; use synthetic records only |
| AI invents unsupported feedback | Evidence requirement, schema validation, teacher override | Show contract and failure behavior; do not claim measured accuracy |
| Prompt injection in a submission | Treat submission as untrusted content; isolate instructions; block unsafe output | Explain the boundary without publishing private prompts |
| Malicious file upload | Type/size checks, archive safety, no execution of student code | Publish generic controls, not private deployment details |
| Provider receives excessive data | Minimize payload, redact identifiers, provider policy review | Publish the policy abstraction, not endpoints or credentials |
| Audit trail is altered | Versioned assessment, review, correction, and release events | Use synthetic event examples |

The AI is an assistant for preliminary assessment and explanation. It does not own final grading, publishing, source-of-truth data mutation, or access to private credentials.
