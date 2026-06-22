# User Guide

## How Outlook MCP Works

Outlook MCP is a bridge between your AI Agent (like Claude or GitHub Copilot) and your Outlook data -- emails, tasks, calendar events, and folders. Here's how it works in simple terms:

1. You ask your AI Agent a question about your Outlook data (e.g., "Find emails from my boss" or "Schedule a meeting for next Tuesday")
2. Your AI Agent uses Outlook MCP to safely access your Outlook data
3. Outlook MCP connects to your Outlook (the app you already use) on your computer
4. Your Outlook retrieves the data and sends it back
5. Your AI Agent reads and understands the data and answers your question

All of this happens locally on your computer -- your data never goes to external servers. Everything is encrypted and secure.

Key benefits:

- No cloud storage or external accounts needed
- Works with your existing Outlook installation
- All your Outlook data stays private on your computer
- Works while offline or online

## Using Outlook MCP

### With Claude Code

Once your system restarts:

1. Open Claude Code (or VS Code with Claude Code extension)
2. Ask Claude about your Outlook data using natural language:
   - "Check my recent emails"
   - "Show tasks due this week"
   - "What meetings do I have tomorrow?"
3. Claude will use Outlook MCP to access your Outlook data

### With Claude Desktop

1. Open Claude Desktop app
2. Start a new conversation
3. Use Claude to manage your Outlook emails, tasks, calendar, and folders just like above

### With GitHub Copilot or Other AI Agents

Outlook MCP works the same way in any configured agent. Just ask naturally about your emails, tasks, calendar, or folders.

## Available Email Tools

Once configured, Outlook MCP gives your AI agent access to these capabilities:

| Tool                | What It Does                                                        |
| ------------------- | ------------------------------------------------------------------- |
| Check Email         | Retrieve recent emails from your Inbox (last hour, day, week, etc.) |
| Search Email        | Find emails using keywords or sender/recipient filters              |
| Read Email          | Get the full content and attachments of an email                    |
| Draft Email         | Compose and save an email draft without sending                     |
| Send Email          | Send a new email or dispatch a saved draft                          |
| Get Flagged Emails  | List emails flagged for follow-up with optional date range filter   |
| Get Conversation    | Retrieve all emails in a conversation thread                        |
| Download Attachment | Save an email attachment to your computer                           |
| Mark Read/Unread    | Change email read status                                            |
| Set Flag            | Add follow-up flags to important emails                             |
| Move Email          | Move emails to different folders                                    |
| Delete Email        | Soft-delete emails to your Deleted Items folder                     |
| Flush Outbox        | Trigger Send/Receive to dispatch emails stuck in the Outbox         |
| List Mailboxes      | See all MAPI mailboxes you have access to                           |
| List Folders        | See all your email folders and mailboxes                            |
| Get Folder Info     | Check folder details (name, item count, etc.)                       |

## Available Task Tools

Outlook MCP also gives your AI agent access to your Outlook Tasks:

| Tool               | What It Does                                                 |
| ------------------ | ------------------------------------------------------------ |
| Create Task        | Create a new task with title, priority, status, and due date |
| Get Tasks          | List tasks with optional status and due date range filters   |
| Update Task        | Update task subject, priority, status, or due date           |
| Mark Task Complete | Mark a task as completed                                     |
| Delete Task        | Delete a task from your Tasks folder                         |

## Available Calendar Tools

Outlook MCP gives your AI agent comprehensive access to your Outlook Calendar:

| Tool                    | What It Does                                                   |
| ----------------------- | -------------------------------------------------------------- |
| Get Event               | Get full details of a calendar event including attendees       |
| Create Event            | Create a new calendar event with title, time, and location     |
| Search Events           | List or search calendar events by date range and title         |
| Delete Event            | Delete a calendar event                                        |
| Update Event            | Edit event details (subject, time, location, body, reminder)   |
| List Calendars          | See all calendar folders visible in Outlook                    |
| Get Free Busy           | Check time slot availability and detect scheduling conflicts   |
| Create Recurring Event  | Create repeating events with daily, weekly, or custom patterns |
| Update Recurring Series | Edit all occurrences in a recurring event series at once       |
| Send Meeting Invite     | Create an event and send meeting invitations to attendees      |
| Respond to Meeting      | Accept, tentatively accept, or decline meeting requests        |

## Available Folder Management Tools

Outlook MCP helps you organize your folders:

| Tool          | What It Does                                      |
| ------------- | ------------------------------------------------- |
| Create Folder | Create a new subfolder under an existing folder   |
| Rename Folder | Rename a folder in place                          |
| Delete Folder | Soft-delete a folder to your Deleted Items folder |
| Move Folder   | Move a folder under a new parent folder           |

## Understanding Logs (For Troubleshooting)

Outlook MCP keeps detailed logs to help troubleshoot issues. You don't need to worry about these unless something isn't working correctly.

Where to find logs:

- Look in the Outlook MCP installation folder (usually `C:\Users\[YourUsername]\AppData\Local\Programs\OutlookMCP\logs\`)
- The log file is named `outlook_mcp.log`

What logs show:

- When Outlook MCP connects to Outlook
- What email searches or actions you performed
- Any errors or problems that occurred

When to check logs:

- If emails, tasks, or calendar events aren't showing up
- If your AI Agent says it can't access your Outlook data
- If the tool seems slow or unresponsive

### Configuration and Log Levels

Outlook MCP uses a configuration file (`config.yaml`) to control its behavior, including how detailed the logs are. By default, logs show basic information (INFO level). If you're troubleshooting a complex problem, you can enable more detailed logs.

Two log levels:

| Level          | Shows                                                                 | When to use                                       |
| -------------- | --------------------------------------------------------------------- | ------------------------------------------------- |
| INFO (default) | Basic information, tool calls, connections, errors                    | Normal operation and basic troubleshooting        |
| DEBUG          | Detailed information about every step, search details, retry attempts | In-depth diagnostics when something isn't working |

### Enable DEBUG Mode for Detailed Diagnostics

To get more detailed logs for troubleshooting:

1. Open Command Prompt (Win+R, type `cmd`, press Enter)
2. Run the configuration menu:

   ```cmd
   outlook-mcp.exe --config-interactive
   ```

3. A menu appears. Select the option to change "Log Level"
4. Enter: `DEBUG` (in all capitals)
5. Save your changes

Now Outlook MCP will create much more detailed logs showing every step it takes. This helps diagnose complex issues.

To return to normal logging:

Run the same command and set the log level back to `INFO`.

If you see errors in the logs, share them with support or check the troubleshooting section below.

## Troubleshooting Common Issues

### "Outlook is not installed"

Outlook MCP requires Microsoft Outlook to be installed on your computer (Outlook for Microsoft 365 or standalone Outlook). Web-only Outlook doesn't work.

Solution:

- Install Microsoft Outlook on your computer
- Open Outlook at least once so it initializes properly
- Restart Outlook MCP

### "AI Agent can't access my emails"

This usually means Outlook MCP isn't connected properly to Outlook or your agents.

Solutions:

1. Make sure Outlook is running (open the Outlook app)
2. Close and reopen your AI Agent (Claude Desktop, VS Code, etc.)
3. Check the logs for error messages (see "Understanding Logs" section above)
4. Verify the tool is configured: Open Command Prompt and run: `outlook-mcp.exe --agent-status`
5. Look for `[OK]` next to your agent

### "Emails are loading slowly"

Large searches or loading many emails can take a moment. This is normal.

Solutions:

- Search for more specific terms (instead of searching all emails, search a specific folder)
- Use a shorter time period (e.g., "last week" instead of "last year")
- Try searching for fewer emails at once

### "I'm getting errors I don't understand"

Outlook MCP sometimes shows technical error messages. Here are the most common ones:

| Error Message              | What It Means                     | Solution                                   |
| -------------------------- | --------------------------------- | ------------------------------------------ |
| "MAPI session failed"      | Can't connect to Outlook          | Restart Outlook and try again              |
| "RPC_E_SERVER_BUSY"        | Outlook is busy with another task | Wait a moment and try again                |
| "AdvancedSearch timed out" | Search took too long              | Try a simpler search or smaller time range |
| "COM object error"         | Outlook has a temporary problem   | Restart Outlook                            |

### "The installer won't run"

If the installer (`OutlookMCP-Setup.exe`) won't start:

Solutions:

- Disable antivirus temporarily (some antivirus software blocks installers)
- Download the installer again from the [Releases page](https://github.com/madharjan/releases/releases/)

### Still having problems?

- Visit the [GitHub repository](https://github.com/madharjan/releases) to report issues or get help
- Share the log file (see "Understanding Logs" section) to help diagnose the problem
- Make sure you're using the latest version of Outlook MCP

## Automate Your Daily Outlook Tasks

With Outlook MCP, you can ask your AI Agent to help with routine Outlook tasks:

Email examples:

- "Flag all unread emails from my manager"
- "Show me all emails from last week about project X"
- "Move emails from [folder] to [archive]"
- "Find emails with attachments from the last 30 days"

Task examples:

- "Create a task to follow up with Alice by Friday"
- "Show me all high-priority tasks due this week"
- "Mark the budget review task as complete"
- "List all tasks marked as high priority"

Calendar examples:

- "What meetings do I have tomorrow?"
- "Schedule a team sync on Monday at 10am"
- "Find all meetings mentioning project X this month"
- "Check my availability next Tuesday between 2-4pm"
- "Send a meeting invite to the team for a 1-hour standup on Friday at 9am"
- "Respond to pending meeting requests (accept the team sync, decline the vendor call)"
- "Create a recurring weekly meeting every Thursday at 3pm"

Folder organization examples:

- "Create a new folder called 'Project Archive' under my Inbox"
- "Rename my 'Projects' folder to 'Active Projects'"
- "Move my 'Completed' folder under 'Archive'"
- "Delete the temporary 'Test' folder I created"

Just ask your AI Agent naturally, and it will use Outlook MCP to get things done without you manually clicking through Outlook.

## What's New

Check the [Changelog](./changelogs.md) for version history and latest features.

## Learn More

- **Full Details & Support:** [madharjan/releases on GitHub](https://github.com/madharjan/releases)
- **Latest Releases:** [Download or view release notes](https://github.com/madharjan/releases/releases/)
