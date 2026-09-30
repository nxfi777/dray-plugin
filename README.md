# Dray

One memory for all your AI assistants and coding agents.

Tell Claude something on Monday, and ChatGPT can look it up on Tuesday. Dray
keeps what you have told each assistant and gives it back in your own words,
with the date you said it.

You need a Dray account: <https://withdray.com>.

## What this plugin contains

- **A connection to Dray's MCP server** at `https://mcp.withdray.com/mcp`
  (Streamable HTTP). You sign in to your Dray account with OAuth the first time
  a tool is used, and approve read access, write access or both.
- **Two skills**, which are plain instructions and run nothing:
  - `dray`: use your memory for one question while you have it paused.
  - `status`: check how much Dray has captured and explain what is missing.

The plugin has no hooks, scripts or executables. Nothing runs or installs on
your computer, and it reads none of your files.

## What it sends, and where

Everything goes to `mcp.withdray.com`, and only when the assistant calls one of
these tools:

| Tool | What it sends to Dray | What comes back |
| --- | --- | --- |
| `search_memory` | The search query the assistant wrote | Facts Dray holds about you and excerpts of your past conversations |
| `recall_conversations` | A conversation id and a range | More of that conversation |
| `get_attribute_history` | The name of one fact | How that fact changed over time |
| `get_conversation_file` | A file name or conversation id | A file you attached or generated before |
| `list_projects`, `get_project`, `get_project_file` | A project name or id | Your project folders and their files |
| `record_memory` | Facts you asked the assistant to save | Confirmation, and the names Dray already uses |
| `link_create`, `link_invite` | A request to link this chat, and what the link is for | A code to type in the other chat |
| `link_join` | The code from the other chat | Who is on the link |
| `link_leave`, `link_close` | Which chat to take off the link, or which link to end | Confirmation |
| `link_post` | The message the assistant wrote for the linked chat | Confirmation |
| `link_read` | A position in the link | New messages from the linked chats |

The plugin sends only what the assistant puts in a tool call: a query, an id,
facts you asked it to save, or a message you asked it to pass on. Your
conversation is never sent, and the plugin cannot read the assistant's own
memory or chat history.

Your Dray account lists every lookup and what it returned, so you can see what
was asked of your memory and when.

## Where the memory comes from

This plugin reads and writes your Dray memory. Your conversations get into
Dray another way: through Dray's browser extension, or the uploader for coding
agents such as Claude Code, Codex and Cursor. You install and switch on both
yourself. See <https://withdray.com/connect>.

## Control

Pause memory, hide a chat or delete anything from your account at
<https://withdray.com>. Closing a link deletes its messages.

## Help, privacy and security

- Help: <https://withdray.com/help> or support@withdray.com
- Privacy policy: <https://withdray.com/privacy>
- Terms: <https://withdray.com/terms>
- To report a security problem, write to support@withdray.com with "Security" in
  the subject.

## Licence

MIT. See [LICENSE](LICENSE).
