# fledge-plugin-jwt

A [fledge](https://github.com/CorvidLabs/fledge) plugin for decoding and inspecting JSON Web Tokens — at the terminal or in a browser.

## Features

- **CLI decode** — split a JWT, base64url-decode each part, pretty-print header + payload as JSON.
- **Web inspector** — a single-file glassmorphic UI (`docs/index.html`) for paste-and-inspect with colorized claims and timestamp humanization.
- **No runtime install** — pure bash + `jq` + `base64`. No `npm install`, no language runtime beyond what's already on a typical dev box.

## Install

```bash
fledge plugins install CorvidLabs/fledge-plugin-jwt
```

Requires `bash`, `jq`, and `base64` on PATH. The `ui` subcommand opens the bundled HTML with `open` (macOS — on Linux, open the file path it prints in your browser).

## Usage

### Decode a token in the terminal

```bash
fledge jwt decode eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIi...
```

```text
Header:
{
  "alg": "HS256",
  "typ": "JWT"
}

Payload:
{
  "sub": "1234567890",
  "name": "John Doe",
  "iat": 1516239022
}
```

### Open the web inspector

```bash
fledge jwt ui
```

Opens the bundled `docs/index.html` — a self-contained, dependency-free page for pasting tokens and exploring claims.

## How it works

`bin/jwt` is a bash script that handles the base64url ⇄ base64 conversion (`tr '_-' '/+'` + padding), feeds each segment to `base64 -d` / `base64 -D` (both forms tried so it works on Linux and macOS), and pipes the result to `jq` for color JSON. The signature segment is intentionally not verified — this plugin inspects, it doesn't trust.

The web inspector is a static HTML file with no build step or backend.

## Development

```bash
# Run the CLI directly
chmod +x bin/jwt
./bin/jwt decode <token>
./bin/jwt ui

# Install locally for testing
fledge plugins install --path .
```

## License

MIT
