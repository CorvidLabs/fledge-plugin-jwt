---
spec: jwt.spec.md
---

## User Stories

- As a developer, I want to inspect JWT metadata locally without sending the token to a remote service.

## Acceptance Criteria

### REQ-jwt-001

Decode SHALL require exactly the standard three-segment JWT shape before processing content.

Acceptance Criteria
- The deterministic valid fixture reaches decoding.
- Missing or malformed segment shapes exit non-zero.

### REQ-jwt-002

The plugin SHALL Base64URL-decode and pretty-print the header and payload without claiming to verify the signature.

Acceptance Criteria
- The deterministic fixture prints the expected JSON subject.
- Help and output describe inspection rather than signature verification.

### REQ-jwt-003

Malformed input, missing tokens, and missing inspector assets SHALL fail explicitly rather than produce a false result.

Acceptance Criteria
- The invalid-input lane step requires a non-zero result.
- ShellCheck and Bash syntax validation cover explicit failure paths.

### REQ-jwt-004

The UI command SHALL resolve and open only the inspector bundled with the installed plugin.

Acceptance Criteria
- Static validation confirms the inspector path is resolved relative to the plugin.
- A missing bundled inspector returns an explicit non-zero error.

## Constraints

- Decoding is inspection only and does not authenticate the token or validate claims.

## Out of Scope

- Signature verification, claim-policy enforcement, token creation, and remote token submission.
