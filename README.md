# Shadow Codex Plugin

This repository is the minimal public Codex plugin wrapper for Shadow.

It contains:

- a Codex marketplace file at `.agents/plugins/marketplace.json`
- the `shadow` plugin manifest and icon assets
- an `.mcp.json` file that points Codex to `https://mcp.shadow.co`

It does not contain the Shadow MCP server implementation or deployment code.

## Install in Codex

Add this marketplace to `~/.codex/config.toml`:

```toml
[marketplaces.shadow-marketplace]
source_type = "git"
source = "https://github.com/dr-ethosxyz/shadow-codex-plugin.git"
ref = "main"

[plugins."shadow@shadow-marketplace"]
enabled = true
```

Then restart Codex and connect Shadow on first use.

## Manual fallback

If you only need raw MCP connectivity, you can still use:

```toml
[mcp_servers.shadow]
url = "https://mcp.shadow.co"
```

But the marketplace/plugin install path is the recommended setup because it carries Shadow branding and the full Codex plugin metadata.
