# HookChat

A static, browser-based Discord-style client for webhook sending and bot-powered channel browsing.

## Deploy on GitHub Pages

1. Open the repository settings.
2. Select **Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**.
4. Select `main` and `/ (root)`, then save.
5. Open the published Pages URL after deployment completes.

No build step, package manager, backend, or database is required.

## Modes

### Webhook

Paste a Discord incoming webhook URL and connect. HookChat can send messages through that webhook. Discord webhooks do not provide server discovery, channel browsing, message history, or live message events.

Treat webhook URLs as secrets. Anyone with the URL can use the webhook.

### Bot

Paste a bot token to connect directly to Discord's HTTP API and Gateway. The bot can list guilds it belongs to, list accessible text channels, read recent messages, receive new messages while connected, and send messages.

The bot needs the **View Channels**, **Read Message History**, and **Send Messages** permissions in the relevant channels. The Message Content privileged Gateway intent must be enabled in the Discord Developer Portal if the app needs message text.

**Security:** This is a static client. A bot token entered here is used by JavaScript in the browser and is not protected by a backend. It is kept in memory only and is not written to local storage, but it is still accessible to the browser session, developer tools, and browser extensions. Use a test bot with limited permissions. Do not use this mode on shared devices or an untrusted copy of the site. For stronger token protection, a server-side application is required.

## Limitations

- HookChat is not an official Discord client.
- It does not authenticate as your personal Discord user.
- Webhook messages appear under the webhook's configured identity.
- Bot messages appear under the bot's identity.
- Discord API permissions and rate limits apply.
- This first version supports text channels and plain-text messages. It does not implement voice, attachments, threads, reactions, or rich embed rendering.

## License

MIT
