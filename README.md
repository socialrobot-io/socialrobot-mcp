# SocialRobot MCP Server

[![smithery badge](https://smithery.ai/badge/ntorres-dev/socialrobot-io)](https://smithery.ai/servers/ntorres-dev/socialrobot-io)
[![Listed on MCP Servers](https://mcpservers.org/badge.svg)](https://mcpservers.org/servers/socialrobot-io/socialrobot-mcp)

Schedule and analyze social media posts from Claude, ChatGPT, Cursor, Gemini, Grok Build, or any MCP client. Remote server, OAuth sign-in, included on every plan.

- **Server URL:** https://socialrobot.io/api/mcp
- **Docs:** https://socialrobot.io/mcp
- **Pricing:** included on every SocialRobot plan, including Free (free plan: 15 scheduled posts per month; paid plans: unlimited)

## What it does

Connect the server once, complete OAuth, and the assistant can:

- List connected accounts
- Create, schedule, list, reschedule, and delete posts
- Upload media through presigned URLs
- Pull account and post analytics plus follower demographics
- Use platform extras: Instagram best-time windows, TikTok creator info, Pinterest board management, LinkedIn people and organization search

## Tools (20)

`list_connected_accounts`, `create_post`, `list_posts`, `update_post`, `delete_post`, `reschedule_post`, `get_media_upload_url`, `upload_media`, `get_account_analytics`, `get_post_analytics`, `get_posts_with_analytics`, `get_follower_demographics`, `linkedin_search_geo_locations`, `linkedin_search_people_mentions`, `linkedin_search_organizations`, `instagram_best_post_times`, `tiktok_get_creator_info`, `get_pinterest_top_pins`, `pinterest_list_boards`, `pinterest_create_board`

## Quickstart

### Claude, ChatGPT, Cursor, or any remote MCP client

1. Link your social accounts in SocialRobot first (the server publishes through accounts you already connected).
2. Add `https://socialrobot.io/api/mcp` to your MCP client.
3. Approve the OAuth scopes. Publishing and media are separate scopes, so analytics-only access is possible.
4. Ask for what you want: "Schedule a LinkedIn post about our launch for Tuesday 9am EST."

### Claude Code plugin

This repo doubles as a Claude Code plugin: `.claude-plugin/plugin.json` (manifest), `.mcp.json` (the remote OAuth server), and `skills/socialrobot-post-scheduling/` (post-scheduling workflow with per-platform adaptation and best-time hints). `claude plugin validate .` passes clean, `--strict` included.

While the community listing is under review, load it from a local clone:

```bash
git clone https://github.com/socialrobot-io/socialrobot-mcp.git
claude --plugin-dir ./socialrobot-mcp
```

### Gemini CLI

```bash
gemini extensions install https://github.com/socialrobot-io/socialrobot-mcp
```

Ships `gemini-extension.json` (remote OAuth server, no local process), `GEMINI.md` context, and the bundled `socialrobot-post-scheduling` skill. The first call that needs access triggers an OAuth challenge: run `/mcp auth socialrobot` and approve in the browser. Indexed by the Gemini CLI extension gallery through the `gemini-cli-extension` topic; if it is not listed yet, install directly from the repo URL above.

### Grok Build

Submitted to the [xAI plugin marketplace](https://github.com/xai-org/plugin-marketplace/pull/372) (pending review). Once listed, install the `socialrobot` plugin from the marketplace to get the MCP server plus a post-scheduling skill, then authorize via browser OAuth on first use.

### Cline

See [llms-install.md](./llms-install.md).

## Auth

OAuth 2.0 with PKCE through the normal login page, or an API key sent as `Authorization: Bearer` for clients that skip browser flows. Sessions can be revoked or rotated from the dashboard at any time. Calls are rate-limited per plan.

## Platforms

Instagram, LinkedIn, X, TikTok, Facebook, Threads, Pinterest, Bluesky, Mastodon.

## Links

- Product: https://socialrobot.io
- MCP page: https://socialrobot.io/mcp
- Best MCP servers for social media in 2026: https://socialrobot.io/blog/best-mcp-servers-for-social-media
- Privacy: https://socialrobot.io/privacy-policy
- Terms: https://socialrobot.io/terms-and-conditions
