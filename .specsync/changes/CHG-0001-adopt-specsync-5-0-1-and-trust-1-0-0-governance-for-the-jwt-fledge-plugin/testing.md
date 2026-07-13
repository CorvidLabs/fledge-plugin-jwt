---
change: CHG-0001-adopt-specsync-5-0-1-and-trust-1-0-0-governance-for-the-jwt-fledge-plugin
artifact: testing
---

# Testing

Local acceptance requires the six-step Fledge lane, strict SpecSync checks at committed threshold 0, all four integrations, a healthy Trust doctor, and a clean diff.

## Requirement Evidence

- `REQ-jwt-001`: the deterministic decode task covers valid shape; the invalid task covers malformed shape.
- `REQ-jwt-002`: the decode task asserts the expected pretty-printed subject and the help task preserves inspection wording.
- `REQ-jwt-003`: the invalid task requires non-zero behavior; ShellCheck and Bash syntax checks cover error branches.
- `REQ-jwt-004`: ShellCheck and Bash syntax checks validate the relative inspector path and explicit missing-file failure.

Hosted acceptance requires the new `trust` job and existing ShellCheck/help smoke jobs to pass while Pages remains independent.
