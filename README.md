# Tiro

Bring your [Tiro](https://tiro.ooo) meeting notes into Cursor and Grok Bot.

Tiro is the meeting notetaker for teams that work in more than one language. It records a conversation, writes a transcript in real time, and turns it into a structured note plus a wiki your company can search later. This plugin connects the agent to the Tiro MCP server so it can answer questions from your own meetings.

## What you can ask

- "Summarize this week's meetings and list open action items."
- "Search our wiki for the product strategy."
- "What did we decide about pricing in the last two weeks?"
- "Pull yesterday's standup notes into this repo as markdown."

## What's included

| Component | Description |
|---|---|
| MCP server | Tiro's hosted MCP server `https://mcp.tiro.ooo/mcp`, connected through [`mcp-remote`](https://www.npmjs.com/package/mcp-remote). Search notes, open transcripts, read summaries, list folders and workspaces, look up share links, and search the company wiki. Rename notes, edit folder names and details, and move or reorder folders. |
| Skill: `catch-up` | Digest of recent meetings: decisions, action items, open questions. |
| Skill: `pull` | Save a Tiro note or transcript into the current folder as markdown. |

## Setup

1. Open [Tiro in Cursor Directory](https://cursor.directory/plugins/tiro). Under **MCP Servers**, choose **Add to Cursor** and approve adding the **Tiro** server in Cursor. Node.js 18+ is required.
2. Enable **Tiro** in Cursor. The first time a Tiro tool runs, a browser window opens. Sign in with the same account you use in the Tiro app.
3. Choose your permissions, check **Long-lived access**, then click **Allow selected access**. The checkbox is required before the button becomes available.
4. Return to Cursor and confirm that the Tiro tools are available. No API key or admin setup is required.

The connection uses a separate OAuth registration for the Tiro MCP resource so it does not reuse an older registration with outdated permissions. If an existing connection fails, disable the old `server` or `tiro` entry before adding **Tiro** again. Keep Node.js available to Cursor; this plugin runs the tested `mcp-remote@0.15.2` bridge.

The Directory button adds the MCP connection. The `catch-up` and `pull` skills are included with the full plugin in this repository.

Any Tiro plan can connect. Don't have an account yet? Sign up at [tiro.ooo](https://tiro.ooo).

## Permissions and privacy

- The agent can only see the notes and wiki pages the signed-in user can already access in the Tiro app.
- Rename and folder tools follow the signed-in user's edit permissions in Tiro. There is no delete tool.
- Sign-in uses OAuth 2.1 with PKCE. Tokens are stored locally by `mcp-remote` (in `~/.mcp-auth`), never in this repository.
- Original recordings stay on the user's device.
- [Privacy policy](https://tiro.ooo/en/privacy-policy) · [Terms of service](https://tiro.ooo/en/terms-of-service)

## Docs and support

- Documentation: [docs.tiro.ooo](https://docs.tiro.ooo/en/guide/notes/api-mcp-cli)
- Support: [support@tiro.ooo](mailto:support@tiro.ooo)

## License

[MIT](LICENSE). The Tiro name and logo are trademarks of ThePlato Inc. and are not licensed under MIT.
