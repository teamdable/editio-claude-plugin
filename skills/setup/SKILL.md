---
name: setup
description: Connect the editio plugin in Claude to the user's CMS account and chosen media, or reconnect it with different permissions.
---

editio uses one remote MCP server, `https://cms.editio.kr/api/v2/mcp`, with CMS account OAuth. No separate CMS server installation is needed.

In Claude on the web, desktop, mobile or Cowork, ask the user to connect editio from the plugin's Connectors tab or from Settings > Connectors. In Claude Code, ask the user to run `/mcp`, select `editio` and choose to authenticate; the browser opens the CMS page. Do not assume a shell or local script is available in Claude chat.

On the CMS page the user signs in with their own CMS account using email/password or Google, chooses an eligible media from their active memberships, and checks the permissions they need. Read-only use needs only article search and reading; reporter work adds saving, editing and submitting; desk review adds rejecting and approving, which also requires a desk or administrator role in CMS. Never ask for passwords, tokens, cookies or one-time codes in chat. Never substitute database access or promote a user's role. Platform administrator status alone does not grant plugin access.

Each connection is bound to one media and the permissions approved at connection time. To switch media or add a permission, the user disconnects editio in Claude (in Claude Code, `/mcp` then clear authentication) and connects again. The user can also end a connection in CMS under 연결된 앱. Do not repeat a successful connection only to refresh this conversation's tool list.

After connecting, call `get_article_metadata_context` without an article to verify access and report the actual result. This onboarding does not authorize creating a test article, changing settings or submitting a manuscript. If a media is missing, explain that an active CMS membership and an approved, unsuspended, unexpired media are required, and do not offer to bypass that requirement.
