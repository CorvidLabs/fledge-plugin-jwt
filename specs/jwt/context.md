---
spec: jwt.spec.md
---

## Context

JWT helps developers inspect token structure locally from either the terminal or a bundled static page.

## Related Modules

- Fledge plugin dispatcher.
- Bundled static inspector under `docs/`.

## Design Decisions

- Keep decoding local and dependency-light.
- State the non-verifying scope explicitly so decoded content is not mistaken for trusted content.
