---
spec: jwt.spec.md
---

## Test Plan

### Integration Tests

- ShellCheck and parse the dispatcher with Bash.
- Verify help exits successfully.
- Decode a deterministic JWT fixture and assert header/payload content.
- Verify malformed and missing tokens exit non-zero.
