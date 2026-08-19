# Installing the SocialRobot MCP server in Cline

The SocialRobot MCP server is remote. There is no Docker image, local process, or API key to configure.

## Steps

1. Open the Cline MCP servers panel in settings.
2. Add a new server of type HTTP (remote).
3. Server URL: `https://socialrobot.io/api/mcp`
4. Save. Cline will prompt for OAuth authorization; sign in with your SocialRobot account and approve the scopes you want.
5. Make sure the social accounts you want to publish to are already linked at https://socialrobot.io before testing.

## Verify

Ask Cline: "List my connected social accounts". It should call `list_connected_accounts` and return your accounts.

## Notes

- The server exposes 17 tools across publishing, media, analytics, audience, and platform extras.
- Publishing and media are separate OAuth scopes; analytics-only access is possible.
- MCP is included on every SocialRobot plan, including the free tier.
