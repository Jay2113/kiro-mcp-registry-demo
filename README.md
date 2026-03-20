# MCP Registry Test

Test registry file for [Kiro Enterprise MCP Governance](https://kiro.dev/docs/enterprise/governance/mcp/).

## What this is

A sample MCP registry JSON that allow-lists three MCP servers: Filesystem, Fetch, and Memory. Use it to test the enterprise MCP governance feature in Kiro.

## Setup

1. Copy the raw URL of `registry.json`:

   ```
   https://raw.githubusercontent.com/YOUR_ORG/mcp-registry-test/main/registry.json
   ```

2. Open the Kiro console → **Settings** → **Shared settings**.

3. Toggle **Model Context Protocol (MCP)** to **On**.

4. Set **MCP Registry URL** to the raw URL above.

5. Restart your Kiro client (IDE or CLI).

## What to expect

- Only the three servers in `registry.json` are available to users on this profile.
- Users cannot add servers outside the allow-list.
- Users can still add their own environment variables and HTTP headers on top of registry definitions.
- Kiro fetches the registry at startup and every 24 hours. Removing a server from the file terminates it on the next sync.

## Allowed servers

| Server | Package | Transport |
|--------|---------|-----------|
| Filesystem | `@modelcontextprotocol/server-filesystem` | stdio |
| Fetch | `@modelcontextprotocol/server-fetch` | stdio |
| Memory | `@modelcontextprotocol/server-memory` | stdio |

## Customizing

Edit `registry.json` to add or remove servers. See the [registry file format docs](https://kiro.dev/docs/enterprise/governance/mcp/#mcp-registry-file-format) for the full schema.
