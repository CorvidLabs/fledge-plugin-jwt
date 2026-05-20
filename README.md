# fledge-plugin-jwt

A [fledge](https://github.com/CorvidLabs/fledge) plugin for JWT decoding and inspection.

## Features

- **CLI Decoding**: Quickly decode JWTs from your terminal.
- **Web Inspector**: Beautiful, premium web UI for detailed inspection.
- **Zero Dependencies**: Powered by standard tools like `jq` and `base64`.

## Installation

```bash
fledge plugins install CorvidLabs/fledge-plugin-jwt
```

## Usage

### Decode a token
```bash
fledge jwt decode <your-token>
```

### Open the Web Inspector
```bash
fledge jwt ui
```

## How it works

This plugin runs via the [fledge-v1 plugin protocol](https://corvidlabs.github.io/fledge/). The `binary` field in `plugin.toml` points to the executable in `bin/` — replace the starter bash stub with any language (Python, Node, Go, Rust, etc.). The only contract is that the binary is executable and supports `--help`.


## Development

```bash
# Test the command directly
chmod +x bin/*
./bin/jwt --help

# Install locally for testing
fledge plugins install --path .
```

## License

MIT
