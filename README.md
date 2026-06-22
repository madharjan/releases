# Project Overview

This repository is a releases and issue management system for the cr8lab projects. It manages releases and changelogs for the following projects:

- outlook-mcp

This repository does not contain source code. It only consists of documentation (setup & user guides) and changelogs.

## Outlook MCP

MCP server that exposes Microsoft Outlook to AI Agents via COM objects on Windows.
No OAuth, no Graph API, no IT admin provisioning required.

Key features:

- Runs entirely locally on Windows via direct COM access
- Launches Outlook headless if not already running
- 36 tools for email, tasks, calendar, and folder management (v1.0.2+)
- Built-in configurator for Claude Desktop, Claude Code, GitHub Copilot, and more
- Compiles to a standalone Windows executable via Nuitka (no Python on target machine)
- 11 calendar tools including event management, recurring events, and meeting invites
- Free/busy availability checking and scheduling conflict detection
- Meeting invite responses (accept, decline, tentatively accept)
- 4 folder management tools for creating, renaming, moving, and deleting folders

### Changelog

Refer to [Changelog](./outlook-mcp/changelogs.md) for changelogs for each release.

### Setup Guide

Refer to [Setup Guide](./outlook-mcp/setup-guide.md) for setup instructions on how to install Outlook MCP.

### User Guide

Refer to [User Guide](./outlook-mcp/user-guide.md) to understand how to use Outlook MCP.
