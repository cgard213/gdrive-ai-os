# Connections

The tools your AI can reach, and what each one is for. The `onboard` skill fills this in from a real read of your tools. Tag each tool with the path it serves so the AI knows when to use it.

| Tool | Path | What it holds | The AI uses it for |
|---|---|---|---|
| Google Drive | all | Files, docs, anything on file | Finding and reading anything |
| Gmail | _____ | Email | Catching up on a thread, drafting replies |
| Google Calendar | _____ | Appointments, schedule | The day, the week, what is booked |
| _____ | _____ | _____ | _____ |
| _____ | _____ | _____ | _____ |

## How connecting works, by platform

How you add a tool depends on the assistant. See `_shared/platforms.md`.

- **Claude:** Settings, Connectors, or the + menu in the composer. For a tool with no built-in connector, use an MCP server (for example through mcp.zapier.com) and add it as a custom connector.
- **ChatGPT:** Settings, Connectors. Link a Drive folder to a Project for live context.
- **Gemini:** native to Workspace. An admin turns on the apps you want.

## Notes

- A tool the AI cannot reach is a blind spot. The weekly audit checks for tools you use but have not connected.
- Some connectors read but do not write. Note which ones, so the AI does not assume it can save where it cannot.
