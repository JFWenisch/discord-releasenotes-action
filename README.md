# discord-releasenotes-action
Action to send existing GitHub release info to a Discord channel via webhook

## 🎯 Purpose

This action is designed to **bridge private GitHub repositories with public Discord communities**. While to-date existing action only work with public repositories and make use of the `on: release` trigger, this versatile action uses the provided token to fetch the latest release metadata—including tag, name, body, and formats it into a clean, multi-line Discord embed. 

(Yes, this action also works with public repositores)

## 🔧 Features

- ✅ Supports **private repositories** using GitHub token authentication
- 📦 Posts **release name, tag, and body** in a Discord embed
- 🖼️ Customizable bot name, avatar, and embed color
- 🧵 Preserves Markdown formatting and line breaks



### Example Usage
```yaml
- name: Notify Discord
  uses: jfwenisch/discord-releasenotes-action@v1
  with:
    webhook: ${{ secrets.DISCORD_WEBHOOK }}
    github_token: ${{ secrets.GITHUBTOKEN }}

```

### 📥 Inputs

| Name           | Description                                                                 | Required | Default               |
|----------------|-----------------------------------------------------------------------------|----------|------------------------|
| `webhook`      | Discord webhook URL to send the release embed                               | ✅ Yes   | —                      |
| `github_token` | GitHub token to fetch release metadata (supports private repos)             | ✅ Yes   | —                      |
| `username`     | Display name of the bot posting to Discord                                  | ❌ No    | `GitHub`           |
| `avatar_url`   | URL of the avatar image shown in Discord                                    | ❌ No    | GitHub's default logo  |
