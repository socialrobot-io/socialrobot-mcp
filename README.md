# SocialRobot MCP Server

Schedule and analyze social media posts from Claude, ChatGPT, Cursor, Gemini, or any MCP client. Remote server, OAuth sign-in, included on every plan.

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

## Tools (17)

`list_connected_accounts`, `create_post`, `list_posts`, `delete_post`, `reschedule_post`, `get_media_upload_url`, `get_account_analytics`, `get_post_analytics`, `get_posts_with_analytics`, `get_follower_demographics`, `linkedin_search_geo_locations`, `linkedin_search_people_mentions`, `linkedin_search_organizations`, `instagram_best_post_times`, `tiktok_get_creator_info`, `pinterest_list_boards`, `pinterest_create_board`

## Quickstart

### Claude, ChatGPT, Cursor, or any remote MCP client

1. Link your social accounts in SocialRobot first (the server publishes through accounts you already connected).
2. Add `https://socialrobot.io/api/mcp` to your MCP client.
3. Approve the OAuth scopes. Publishing and media are separate scopes, so analytics-only access is possible.
4. Ask for what you want: "Schedule a LinkedIn post about our launch for Tuesday 9am EST."

### Gemini CLI

Once the gallery indexes this repo, `gemini extensions install github.com/socialrobot-io/socialrobot-mcp`. The repo ships a `gemini-extension.json` with the remote server URL.

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
