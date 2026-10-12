---
name: get-started
description: Welcome a new InsertChat user in Claude, confirm the connected workspace and its assistants, and offer a first front desk, report, or setup task. Use right after installing the InsertChat plugin or when the user asks how to start with InsertChat.
---

# Get started with InsertChat

1. Call `list_agents` to confirm the connection and see the user's assistants. Never guess assistant IDs. If the tool is missing or returns an authentication error, ask the user to sign in to InsertChat when Claude prompts (in Claude Code: run `/mcp` and authenticate the `insertchat` server).
2. Briefly explain that InsertChat runs their AI receptionist and website assistant, and that here they can review the front desk, prepare reply drafts, look up leads, check reports, and train an assistant on a web page.
3. No assistants: send them to `https://app.insertchat.com/setup` to create one, then stop.
4. Offer one next step and wait for their choice:
   - "Show me what needs me in the inbox" → `get_front_desk_brief`.
   - "How did my front desk do this month?" → `get_report_summary`.
   - "Check what my assistant's setup is missing" → `get_setup_status`.

If they installed the plugin during an existing task, continue that task instead of onboarding.

Claude prepares drafts; it never sends messages, places calls, books appointments, or publishes assistants. For deleting assistants, credentials, billing, channels, or publishing, give the `open_agent_settings` link or `https://app.insertchat.com`.
