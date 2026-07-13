---
module: jwt
version: 2
status: active
files:
  - bin/jwt

db_tables: []
depends_on: []
---

# Jwt

## Purpose

Decode the header and payload of a structurally valid JSON Web Token for inspection, and open the bundled local web inspector when requested.

## Public API

| Surface | Behavior |
|---------|----------|
| decode | Validate JWT segment shape, Base64URL-decode header and payload, and pretty-print their JSON. |
| ui | Open the bundled static inspector page. |
| help | Print command usage and examples. |

## Invariants

1. Decode accepts exactly three non-empty Base64URL-shaped segments.
2. Only the header and payload are decoded; the signature is not verified.
3. Base64URL characters are normalized and padding is restored before decoding.
4. Missing tokens and malformed structure exit non-zero with diagnostics on standard error.
5. The UI command opens only the bundled inspector path resolved relative to the plugin.
6. Unknown subcommands exit with usage status 64.

## Behavioral Examples

```
Given a three-segment JWT whose header and payload contain JSON
When the developer runs the decode command
Then the plugin prints the decoded header and payload without claiming signature verification
```

## Error Cases

| Error | When | Behavior |
|-------|------|----------|
| Missing token | Decode has no token argument | Report the required argument and exit non-zero. |
| Invalid JWT shape | Token is not three Base64URL segments | Report invalid format and exit non-zero. |
| Invalid JSON | A decoded segment is not JSON | Report which segment could not be parsed. |
| Inspector missing | Bundled docs page cannot be found | Report the resolved missing path and exit non-zero. |

## Dependencies

- Bash
- `base64`, `tr`, and `jq`
- Platform `open` command for the UI surface

## Change Log

| Version | Date | Changes |
|---------|------|---------|
| 1 | 2026-07-12 | Document existing JWT decoding and local inspector behavior for SpecSync 5 adoption. |
| 2026-07-13 | CHG-0001-adopt-specsync-5-0-1-and-trust-1-0-0-governance-for-the-jwt-fledge-plugin: Adopt SpecSync 5.0.1 and Trust 1.0.0 governance for the JWT Fledge plugin |
