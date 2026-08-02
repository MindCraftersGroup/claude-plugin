# InsertChat: AI Chatbot & Knowledge Base Builder

The official Claude plugin for [InsertChat](https://insertchat.com). It connects Claude to InsertChat's hosted MCP server so you can inspect assistants, check setup, add a confirmed website source, monitor source training, and open assistant settings.

## Install

After approval in the Claude community marketplace:

```text
/plugin marketplace add anthropics/claude-plugins-community
/plugin install insertchat@claude-community
```

Until then, install directly from this repository:

```text
/plugin marketplace add InsertChat/claude-plugin
/plugin install insertchat@insertchat-plugins
```

Start a new Claude Code session, open `/mcp`, and sign in to your InsertChat account when prompted.

## What Claude can do

- List assistants in the connected InsertChat app.
- Check assistant setup and integration status.
- Add a website source after you confirm the exact assistant and URL.
- Monitor website-source training status.
- Return a safe deep link to assistant settings for actions outside the focused MCP surface.

The plugin does not expose delete, credential, billing, message-sending, or publishing tools.

## Example prompts

```text
List my InsertChat assistants.
Check the setup status of my assistant.
Add https://example.com/docs as a source after confirming the assistant and URL with me.
Show the latest source training status.
Open this assistant's settings.
```

## Requirements

- An [InsertChat](https://app.insertchat.com) account with access to an app and assistant.
- Claude Code with plugin support.
- Browser access to complete InsertChat OAuth sign-in.

## Security and privacy

Authentication uses OAuth with PKCE. Access is scoped to the InsertChat app selected during authorization. See the [privacy policy](https://insertchat.com/privacy), [terms](https://insertchat.com/terms), and [security overview](https://insertchat.com/security).

## Support

Use [InsertChat support](https://insertchat.com/contact) for installation or account help.

## License

[MIT](LICENSE)
