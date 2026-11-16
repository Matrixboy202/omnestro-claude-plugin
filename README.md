# OMNESTRO for Claude Code

OMNESTRO conducts your own Claude Code and Codex on one software-engineering mission: one builder, a builder with an independent reviewer, or two competing candidates with cross review. Every mission runs in an isolated copy of your project with tests, review and recorded evidence. Nothing reaches your project until you approve the plan and press Apply inside the OMNESTRO desktop app.

This is the edition of the plugin listed in Anthropic's directory. It holds instructions only: one skill, the listing and an icon, all Markdown, JSON and PNG. It contains no program. The OMNESTRO tools come from the OMNESTRO desktop app on your computer.

## Requirements

- The OMNESTRO desktop app. Windows is in early access by invitation until the Microsoft Store release, and Linux has a public beta. See https://omnestro.matrixboy.net/download/.
- An OMNESTRO account. The OMNESTRO app shows the current trial and subscription terms.
- Claude Code signed in with your own Claude subscription. Codex with your ChatGPT plan is optional and enables two-agent missions.

## Setup

1. Install this plugin from the directory.
2. Open OMNESTRO > **Account and subscription** (الحساب والاشتراك) and create an account or sign in.
3. Open **Connect Codex and Claude** (الربط والإضافات) > the **Claude Code** card and press **Install / update the plugin** (تثبيت / تحديث الإضافة). The app sees this plugin and adds only the OMNESTRO tools: a local MCP server named `omnestro` in your Claude Code user settings.
4. On the same card, choose your project and press **Connect / change project** (ربط / تغيير المشروع). A connection lasts up to 7 days and you can revoke it at any time.
5. Start a new Claude Code session and run `/omnestro:conduct-mission`, or ask Claude to run a task through OMNESTRO.

## Example prompts

- "Run this through OMNESTRO: add input validation to the signup form, with Codex reviewing Claude's change."
- "Use OMNESTRO to fix the failing checkout tests and show me the recorded evidence before I apply anything."
- "Ask OMNESTRO for two competing implementations of the CSV export and a cross review of both."

## What the plugin runs, reads and sends

- The plugin itself runs nothing, reads no files and sends nothing.
- The OMNESTRO app registers the `omnestro` MCP server when you press the install button. That server is the dependency-free launcher published on this repository's `main` branch. It reads one file, `~/.omnestro/extensions/claude.json`, which the app writes when you connect a project, and talks only to the OMNESTRO engine on `127.0.0.1`.
- The OMNESTRO app contacts the OMNESTRO account service for sign-in and subscriptions. It runs your own Claude Code and Codex command-line tools, which talk to their providers as they normally do.

## Troubleshooting

- **The skill says the OMNESTRO tools are missing**: press **Install / update the plugin** on the Claude Code card in OMNESTRO, then start a new Claude Code session.
- **NOT_PAIRED** or **EXPIRED**: connect the project again from the Claude Code card.
- **ACCOUNT_REQUIRED**: sign in, or subscribe, under Account and subscription.
- **ENGINE_UNAVAILABLE**: open the OMNESTRO app and wait until it shows that the engine is ready.

## Links

- Website: https://omnestro.matrixboy.net
- Support: https://omnestro.matrixboy.net/support/
- Privacy policy: https://omnestro.matrixboy.net/privacy/
- Terms: https://omnestro.matrixboy.net/terms/
- Source: https://github.com/Matrixboy202/omnestro-claude-plugin
