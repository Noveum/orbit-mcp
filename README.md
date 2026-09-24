# Orbit MCP

<p align="center"><img src="assets/logo.png" width="96" alt="Orbit logo"></p>

Connect Gemini CLI and Cursor to [Orbit](https://orbit.noveum.ai), a free, open-source task manager for people and agents. Manage issues, projects, sprints, docs and files in the workspace you authorize.

**Remote MCP endpoint:** `https://orbit.noveum.ai/mcp`

## Install in Gemini CLI

```sh
gemini extensions install https://github.com/Noveum/orbit-mcp
```

Review the installation prompt, restart Gemini CLI, and authenticate the Orbit server when prompted. You can start authentication with `/mcp auth orbit`. Sign into Orbit, select a workspace and complete its consent and passkey verification. The connection uses Streamable HTTP and OAuth. No API key is required.

Confirm the extension is installed with `gemini extensions list`. Use `/mcp` inside Gemini CLI to inspect connection status and available tools. Tool availability depends on the permissions you grant.

## Cursor

The repository includes a Cursor plugin manifest and a one-plugin marketplace manifest. Marketplace publication requires Cursor review and is not claimed here. You can already add the remote server in Cursor MCP settings with this configuration:

```json
{
  "mcpServers": {
    "orbit": { "url": "https://orbit.noveum.ai/mcp" }
  }
}
```

Complete the browser OAuth flow when prompted. Do not add a local command or API key.

## Other MCP clients

Use a client that supports remote Streamable HTTP with OAuth discovery. Set its server URL to `https://orbit.noveum.ai/mcp`, then complete the browser authorization flow. See [Orbit MCP setup](https://github.com/Noveum/orbit/blob/main/docs/mcp.md) for client-specific instructions.

## What this repository contains

This repository contains client connection metadata and the Orbit logo. It does not start a local server or include the application. Full application source and self-hosting instructions live in [Noveum/orbit](https://github.com/Noveum/orbit).

## Validation

Installing the public repository with Gemini CLI 0.26.0 succeeded in an isolated profile. Cursor metadata passes the official plugin-template validator; Cursor IDE installation has not yet been exercised. That verifies package loading, not a complete authenticated Gemini session. Authentication still requires the user's interactive Orbit consent.

## Support

Report connection problems in [Orbit issues](https://github.com/Noveum/orbit/issues). Include the client version and error message, but never include access tokens, authorization codes, cookies or private workspace content.

Apache-2.0 licensed. Built by [Noveum](https://noveum.ai).
