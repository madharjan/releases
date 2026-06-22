# Changelogs

## Outlook MCP v1.0.2

- Added 4 calendar tools: get_event, create_event, search_events, delete_event
- Calendar events include attendees, organizer, recurrence, and reminder details
- search_events supports date range listing and title keyword search (query or start_date required)
- Refactored tool handlers into tools/ module (email, tasks, calendar, folders)

## Outlook MCP v1.0.1

- Update with new email tools and task management (Microsoft To Do) tools
- Added 6 email tools: draft, send, conversation thread, attachments
- Added 5 task tools: create, list, update, complete, delete

## Outlook MCP v1.0.0

Initial release:

- Runs entirely locally on Windows via direct COM access
- Launches Outlook headless if not already running
- 10 tools: check, search, read, flag, move, delete email and more
- Built-in configurator for Claude Desktop, Claude Code, GitHub Copilot, and more
- Standalone Windows executable (no Python on target machine)
- Installer using Inno Setup 6 - <https://jrsoftware.org/>
