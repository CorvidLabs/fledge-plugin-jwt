---
change: CHG-0001-adopt-specsync-5-0-1-and-trust-1-0-0-governance-for-the-jwt-fledge-plugin
artifact: testing
---

# Testing

Local acceptance requires the six-step Fledge lane, strict SpecSync checks at committed threshold 0, all four integrations, a healthy Trust doctor, and a clean diff.

Hosted acceptance requires the new `trust` job and existing ShellCheck/help smoke jobs to pass while Pages remains independent.
