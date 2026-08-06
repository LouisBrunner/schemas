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

- `atproto/`: an OAuth client's `client-metadata.json`
- `clippy/`: Rust Clippy's `clippy.toml`
- `colima/`: Colima's per-profile `colima.yaml`
- `home-assistant/`: add-on `config.yaml`, `repository.yaml`, add-on translation strings, blueprint YAML, core `configuration.yaml`, and integration `translations/<lang>.json`/`strings.json`
- `checkov/`: Checkov's `.checkov.yaml`
- `docker/`: the Docker CLI's `~/.docker/config.json`
- `firefox/`: Firefox enterprise `policies.json`
- `genea/`: the `genea` v3 family-tree JSON format (source of truth for a GEDCOM export tool)
- `hadolint/`: hadolint's `.hadolint.yaml`
- `karabiner/`: Karabiner-Elements' `karabiner.json`
- `mcp/`: the de facto `mcpServers` MCP client config shape (Claude Desktop, Claude Code, Cursor, Windsurf)
- `mockery/`: mockery's `.mockery.yml`
- `ollama/`: Ollama's `config.json` and `server.json`
- `rustup/`: rustup's `settings.toml`
- `textlint/`: textlint's `.textlintrc`

## Caveats

Most of these are reverse-engineered from official docs or, where available, the tool's own source (see the `description` in each schema for where it came from).
None of them come from an authoritative published schema, because one doesn't exist, so treat them as best-effort rather than exhaustive.

Issues and PRs to fill gaps are welcome.
