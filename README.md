# Discord Meme Bot 🤖

A Discord bot with slash commands for meme generation and more.

## Prerequisites

- Python 3.13+
- [uv](https://docs.astral.sh/uv/) - Fast Python package manager
- Discord Bot Token
- n8n Webhook URL and API Key

## Setup

### Local Development
```bash
git clone https://github.com/EstebanVincent/DiscordBot.git
cd DiscordBot
cp .env.example .env  # Edit with your values
uv sync
uv run python src/main.py
```

### Docker
```bash
# Build and run locally
docker build -t discord-bot .
docker run -d --name discord-bot -e DISCORD_TOKEN=... -e WEBHOOK_URL=... -e API_KEY=... discord-bot

# Or use pre-built image
docker run -d --name discord-bot -e DISCORD_TOKEN=... -e WEBHOOK_URL=... -e API_KEY=... \
  ghcr.io/estebanvincent/discordbot/discord-bot:latest
```

## Commands

- `/meme prompt:<text>` - Generate a meme from your text prompt

## Discord Setup

1. Create bot at [Discord Developer Portal](https://discord.com/developers/applications)
2. Copy bot token to environment variables  
3. Invite bot with permissions: Send Messages, Use Slash Commands, Embed Links


## Development

```bash
# Code quality
uv run ruff check src
uv run ruff format src
```

Project uses GitHub Actions for CI/CD with semantic versioning and automated Docker builds.
