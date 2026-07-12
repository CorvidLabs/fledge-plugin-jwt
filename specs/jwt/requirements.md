---
spec: jwt.spec.md
---

## User Stories

- As a developer, I want to inspect JWT metadata locally without sending the token to a remote service.

## Acceptance Criteria

### REQ-jwt-001

Decode SHALL require exactly the standard three-segment JWT shape before processing content.

### REQ-jwt-002

The plugin SHALL Base64URL-decode and pretty-print the header and payload without claiming to verify the signature.

### REQ-jwt-003

Malformed input, missing tokens, and missing inspector assets SHALL fail explicitly rather than produce a false result.

### REQ-jwt-004

The UI command SHALL resolve and open only the inspector bundled with the installed plugin.

## Constraints

- Decoding is inspection only and does not authenticate the token or validate claims.

## Out of Scope

- Signature verification, claim-policy enforcement, token creation, and remote token submission.
