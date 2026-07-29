# Contributing to XCGP

## How to contribute

1. Open an issue to discuss proposed changes
2. Fork the repo and create a feature branch
3. Submit a pull request

## What we're looking for

- **Feedback from Gold/Green implementers** — does the tumbler format work for you?
- **Feedback from new implementers** — is the spec clear enough to implement?
- **Test cases** — conformance tests for each endpoint
- **Reference implementations** — minimal servers in different languages

## Design constraints

- **Backward compatible** — new versions MUST NOT break existing implementations
- **Minimal** — if a feature can be omitted, omit it
- **Implementation-agnostic** — MUST NOT mandate specific data structures or protocols
- **Secure by default** — content verification MUST be required, not optional

## Versioning

We use semantic versioning. The spec version (`protocol_version` field) tracks
breaking changes. New optional fields in responses do NOT require a version bump.
