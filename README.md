# Project Overview

This repository is a releases and issue management system for the cr8lab project. It manages releases, changelogs, and release notes for the following projects:

- **outlook-mcp**: Outlook MCP integration package

This repository does not contain source code.

## Outlook MCP

MCP server that exposes Microsoft Outlook to AI Agents via COM objects on Windows.
No OAuth, no Graph API, no IT admin provisioning required.

Key features:

- Runs entirely locally on Windows via direct COM access
- Launches Outlook headless if not already running
- 10 tools: check, search, read, flag, move, delete email and more
- Built-in configurator for Claude Desktop, Claude Code, GitHub Copilot, and more
- Compiles to a standalone Windows executable via Nuitka (no Python on target machine)
