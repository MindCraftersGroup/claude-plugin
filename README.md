# InsertChat - AI Receptionist

The official Claude plugin for [InsertChat](https://insertchat.com), the AI receptionist, AI phone agent, and AI chatbot for growing businesses. InsertChat answers phone calls, website chats, WhatsApp, email, and SMS with your business knowledge, captures leads, and hands conversations to your team in one shared inbox.

This plugin connects Claude to InsertChat's hosted MCP server and adds four guided skills, so you can run your front desk from Claude in chat, Cowork, and Claude Code.

## What Claude can do

- **See what needs you:** a front desk brief across your assistants with urgent, unassigned, waiting, and needs-you conversations.
- **Review calls and chats:** search and read AI receptionist calls and AI chatbot conversations, then get summaries, callback briefs, and reply drafts that you send yourself.
- **Look up leads:** find contacts, read their submitted inquiries, and open related conversations (owners and admins).
- **Track results:** monthly conversation, resolution, contact, satisfaction, and credit reports (requires analytics access).
- **Train your assistant:** check knowledge sources and training status, spot the questions customers ask, and add one web page (FAQ, services, opening hours) as knowledge after you confirm the assistant and URL.

Adding a URL imports one page, uses one credit and one source slot, and does not crawl the website. Setup and training checks do not verify every channel or prove a phone line or website widget is live.

## Skills

| Skill | Use it for |
| --- | --- |
| `get-started` | Confirm the connection and pick a first task |
| `ai-front-desk` | Front desk briefing, inbox triage, lead follow-up, monthly performance |
| `ai-receptionist` | AI receptionist call reviews and callback briefs |
| `ai-website-assistant` | Website chat knowledge gaps, training checks, adding a page |

## Install

From Claude: open **Customize > Plugins**, search for InsertChat, and add it once it is listed in Anthropic's directory.

In Claude Code, from this repository:

```text
/plugin marketplace add MindCraftersGroup/claude-plugin
/plugin install insertchat@insertchat-plugins
```

Then run `/mcp`, select `insertchat`, and sign in to your InsertChat account.

### Other clients

The same repository works as a Cursor plugin (`.cursor-plugin/plugin.json` + `mcp.json`) and a Gemini CLI extension (`gemini-extension.json`):

```text
gemini extensions install https://github.com/MindCraftersGroup/claude-plugin
```

Any MCP client can connect directly to `https://api.insertchat.com/v2/mcp` (Streamable HTTP, OAuth). The server is published in the official MCP Registry as `com.insertchat/insertchat`.

## Example prompts

```text
Show the calls and chats my AI receptionist needs me to handle.
Summarize my latest unassigned website chat and draft a reply.
Find my newest lead and tell me what they asked for.
How did my AI receptionist and chatbot perform this month?
Is my assistant fully set up, and has it finished training?
Train my AI chatbot on my website's FAQ page: https://example.com/faq.
```

## Requirements

- An [InsertChat](https://app.insertchat.com) account with access to a workspace and at least one assistant.
- Contacts require an owner or admin role; reports also require analytics access.
- Browser access to complete InsertChat OAuth sign-in.

## What the plugin connects to and sends

The plugin contains no executable code. It declares one remote MCP server, `https://api.insertchat.com/v2/mcp`, operated by MindCrafters LLC. Claude sends tool requests (assistant IDs, search queries, filters, and URLs you ask to import) to that server and receives data from your InsertChat workspace. Nothing is sent anywhere else.

Sign-in uses OAuth 2.0 with PKCE and is scoped to the workspace you choose during authorization. The plugin requests these scopes: `insertchat:apps:read`, `insertchat:agents:read`, `insertchat:sources:read`, `insertchat:sources:write`, `insertchat:inbox:read`, `insertchat:contacts:read`, and `insertchat:reports:read`. Clients that ignore the requested scope list receive the server default, which adds `insertchat:workspace:open` (workspace links and InsertChat display preferences).

The only write tool is `add_source_url`: it imports one web page as knowledge and uses one credit and one source slot. Every other tool is read-only. The plugin cannot delete data, send customer messages, place calls, book appointments, change phone routing, manage credentials or billing, or publish assistants. Reply drafts stay in Claude until you send them yourself in InsertChat.

## Privacy and security

See the [privacy policy](https://insertchat.com/privacy), [terms](https://insertchat.com/terms), and [security overview](https://insertchat.com/security). You can disconnect at any time by removing the plugin or clearing its authentication in Claude.

## Support

Contact [InsertChat support](https://insertchat.com/contact) or support@insertchat.com.

## License

[MIT](LICENSE)
