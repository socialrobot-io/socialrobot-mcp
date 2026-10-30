# SocialRobot

SocialRobot is a social media scheduling app (https://socialrobot.io). This extension
connects Gemini CLI to the hosted SocialRobot MCP server at
`https://socialrobot.io/api/mcp`. Remote server, OAuth sign-in, included on every plan,
including Free.

## What it can do

- List connected social accounts across Instagram, LinkedIn, X, TikTok, Facebook,
  Threads, Pinterest, Bluesky, Mastodon, and Google Business Profile.
- List the user's brands (projects), read what SocialRobot learned about each one
  (offer, audience, writing voice) and the hashtags it uses, and check what the plan
  has left this month.
- Create, schedule, list, update, reschedule, and delete posts.
- Upload media, either through a presigned URL or the byte upload fallback.
- Read account and post analytics, a performance report of what worked, follower
  demographics, and Instagram best-time windows.
- Platform extras: LinkedIn people, organization, and location search for mentions;
  Pinterest boards and top pins; TikTok creator info.

A bundled skill (`socialrobot-post-scheduling`) covers the post-scheduling workflow,
per-platform adaptation, and best-time hints.

## How to behave

- Confirm intent before creating, updating, rescheduling, or deleting. Deletion is
  permanent, so name the post explicitly.
- SocialRobot schedules and publishes posts only. It cannot send direct messages,
  email, or calendar invites, and it does not write copy. Do not call tools for those
  requests.
- Check which platforms are connected before scheduling. Instagram requires an image or
  video, so text-only feed posts are impossible.
- When scheduling, confirm the platform, account, and time with an explicit timezone.
- If a tool call returns an authentication challenge, tell the user to run
  `/mcp auth socialrobot` and finish the OAuth flow in the browser.
- Summarize results in plain language. Do not dump raw JSON, internal identifiers,
  storage keys, or provider error bodies.

## Auth

OAuth 2.0 with PKCE and automatic discovery, so no configuration is needed in the
extension manifest. Sessions can be revoked at any time from the SocialRobot dashboard.

## Links

- App: https://socialrobot.io
- MCP page: https://socialrobot.io/mcp
- Privacy: https://socialrobot.io/privacy-policy
- Support: hey@socialrobot.io
