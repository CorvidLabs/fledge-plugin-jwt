# fledge-plugin-jwt

A fledge plugin

## Install

```bash
fledge plugins install 0xLeif/fledge-plugin-jwt
```

## Usage

```bash
fledge jwt
fledge jwt --help
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
