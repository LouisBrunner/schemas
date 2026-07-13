# schemas

JSON Schemas for config file formats that don't have one published anywhere.

Each schema lives at `schemas/<vendor>/<filename>.schema.json` and is published as-is via GitHub Pages at:

```text
https://schemas.lbrunner.net/<vendor>/<filename>.schema.json
```

Point your file at it the usual way:

```jsonc
{
  "$schema": "https://schemas.lbrunner.net/docker/config.schema.json",
}
```

```yaml
# yaml-language-server: $schema=https://schemas.lbrunner.net/home-assistant/addon-config.schema.json
```

```toml
#:schema https://schemas.lbrunner.net/rustup/settings.schema.json
```

## What's in here

- `clippy/`: Rust Clippy's `clippy.toml`
- `home-assistant/`: add-on `config.yaml`, `repository.yaml`, add-on translation strings, blueprint YAML, core `configuration.yaml`, and integration `translations/<lang>.json`/`strings.json`
- `checkov/`: Checkov's `.checkov.yaml`
- `docker/`: the Docker CLI's `~/.docker/config.json`
- `firefox/`: Firefox enterprise `policies.json`
- `karabiner/`: Karabiner-Elements' `karabiner.json`
- `mcp/`: the de facto `mcpServers` MCP client config shape (Claude Desktop, Claude Code, Cursor, Windsurf)
- `ollama/`: Ollama's `config.json` and `server.json`
- `rustup/`: rustup's `settings.toml`
- `textlint/`: textlint's `.textlintrc`

## Caveats

Most of these are reverse-engineered from official docs or, where available, the tool's own source (see the `description` in each schema for where it came from).
None of them come from an authoritative published schema, because one doesn't exist, so treat them as best-effort rather than exhaustive.
A few of these formats keep growing new options with every release (Clippy, Checkov), and at least one (rustup's `settings.toml`) is explicitly not meant to be a stable public interface,
so don't be surprised if a field is missing or a schema lags behind upstream.

Issues and PRs to fill gaps are welcome.
