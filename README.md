# OMNESTRO for Claude Code

OMNESTRO conducts your own Claude Code and Codex on one software-engineering mission: one builder, a builder with an independent reviewer, or two competing candidates with cross review. Every mission runs in an isolated copy of your project with tests, review and recorded evidence. Nothing reaches your project until you approve the plan and press Apply inside the OMNESTRO desktop app.

This plugin connects Claude Code to the OMNESTRO desktop app on your computer. It does not contain the OMNESTRO engine.

## Requirements

- The OMNESTRO desktop app. Windows is in early access by invitation until the Microsoft Store release, and Linux has a public beta. See https://omnestro.matrixboy.net/download/.
- An OMNESTRO account. The first sign-in on a device starts a free trial; after the trial a subscription is required. The app shows the current trial length and prices.
- Claude Code signed in with your own Claude subscription. Codex with your ChatGPT plan is optional and enables two-agent missions.
- Node.js 18 or later on your PATH.

## Setup

1. Install the plugin: `claude plugin marketplace add Matrixboy202/omnestro-claude-plugin`, then `claude plugin install omnestro@omnestro`.
2. Open OMNESTRO > **Account and subscription** (الحساب والاشتراك) and create an account or sign in.
3. Open **Connect Codex and Claude** (الربط والإضافات) > the **Claude Code** card, choose your project and press **Connect / change project** (ربط / تغيير المشروع). A connection lasts up to 7 days and you can revoke it at any time. If you installed this plugin from the directory, you do not need the card's install button.
4. Start a new Claude Code session and run `/omnestro:conduct-mission`, or ask Claude to run a task through OMNESTRO.

## Example prompts

- "Run this through OMNESTRO: add input validation to the signup form, with Codex reviewing Claude's change."
- "Use OMNESTRO to fix the failing checkout tests and show me the recorded evidence before I apply anything."
- "Ask OMNESTRO for two competing implementations of the CSV export and a cross review of both."

## What the plugin runs, reads and sends

- It starts `node launcher.mjs` from the plugin folder as a local stdio MCP server. The launcher has no third-party dependencies.
- It reads one file, `~/.omnestro/extensions/claude.json`, which the OMNESTRO app writes when you connect a project. The file holds the local engine address and a connection token scoped to that one project.
- It sends requests only to the OMNESTRO engine on `127.0.0.1`. The plugin itself makes no internet requests and collects no conversation data.
- The OMNESTRO app contacts the OMNESTRO account service for sign-in and subscriptions. It runs your own Claude Code and Codex command-line tools, which talk to their providers as they normally do.

## Tools

`omnestro_connection_status` reports the setup step you still need, your account state and the free-trial and plan facts. Once connected: read the project, modes, missions, plans, activity and evidence, and request a new mission, a follow-up, the next stage, a resume or a cancellation. Every request that changes anything waits for your approval in the OMNESTRO app. Plan approval, answers to questions and Apply happen only in the app.

## Troubleshooting

- **NOT_PAIRED** or **EXPIRED**: connect the project again from the Claude Code card. Installing or updating the plugin does not renew a connection.
- **ACCOUNT_REQUIRED**: sign in, or subscribe after the trial, under Account and subscription.
- **ENGINE_UNAVAILABLE**: open the OMNESTRO app and wait until it shows that the engine is ready.

## Links

- Website: https://omnestro.matrixboy.net
- Support: https://omnestro.matrixboy.net/support/
- Privacy policy: https://omnestro.matrixboy.net/privacy/
- Terms: https://omnestro.matrixboy.net/terms/
- Source: https://github.com/Matrixboy202/omnestro-claude-plugin
