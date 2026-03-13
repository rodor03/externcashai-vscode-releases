[**Русский**](README.ru.md) | English

# ExternCashAI — VS Code Extension

VS Code extension that connects ExternCash AI server as a native GitHub Copilot Chat provider with inline code completions.

## Features

- **Copilot Chat Integration** — all server models available in the Copilot Chat model dropdown
- **Inline Code Completion** — tab-autocomplete with ghost text suggestions while typing
- **Tool Calling** — full support for function/tool invocation
- **Thinking/Reasoning** — support for reasoning-enabled models (extended thinking)
- **Vision** — support for multimodal models (image input)
- **Token Tracking** — real-time token consumption statistics in the sidebar
- **Model Management** — enable/disable specific models, per-model thinking settings
- **Auto-Update** — automatic update checking via GitHub Releases
- **Model Hiding** — hide VS Code's built-in Copilot models from the dropdown

## Supported Models

| Provider | Models |
|----------|--------|
| Anthropic | Claude Opus 4.6, Claude Sonnet 4.6, Claude Haiku 4.5 |
| Google | Gemini 3.1 Pro, Gemini 2.5 Pro, Gemini 3 Pro/Flash |
| OpenAI | GPT-5 Mini, GPT-5.4, GPT-5.3 Codex |
| xAI | Grok Code Fast 1 |

## Installation

1. Download the `.vsix` file from [Releases](https://github.com/rodor03/externcashai-vscode-releases/releases)
2. In VS Code: `Extensions` → `...` → `Install from VSIX...`
3. Restart VS Code

## Setup

1. Open Command Palette (`Ctrl+Shift+P`)
2. Run `ExternCashAI: Set API Key`
3. Enter your `sk-...` key

That's it! Models will appear in Copilot Chat, and tab-autocomplete will start working automatically.

## Commands

| Command | Description |
|---------|-------------|
| `ExternCashAI: Set API Key` | Set or update API key |
| `ExternCashAI: Quick Actions` | Quick actions menu (status bar click) |
| `ExternCashAI: Toggle Inline Completion` | Enable/disable tab-autocomplete |
| `ExternCashAI: Select Inline Completion Model` | Choose model for autocomplete |
| `ExternCashAI: Select Chat Model` | Choose model for Copilot Chat |
| `ExternCashAI: Check for Updates` | Manually check for extension updates |
| `ExternCashAI: Hide Builtin Copilot Models` | Hide built-in Copilot models from dropdown |
| `ExternCashAI: Show Builtin Copilot Models` | Restore hidden built-in models |

## Chat Participant

Type `@externcashai` in Copilot Chat to access built-in commands:

| Command | Description |
|---------|-------------|
| `@externcashai stats` | Show context and token usage statistics |
| `@externcashai models` | List available models |

## Settings

| Setting | Default | Description |
|---------|---------|-------------|
| `externcashai.inlineCompletion.enabled` | `true` | Enable tab-autocomplete |
| `externcashai.inlineCompletion.model` | `""` | Model for autocomplete (default: Claude Haiku 4.5) |
| `externcashai.inlineCompletion.debounceDelay` | `400` | Delay before request (ms, 100–2000) |
| `externcashai.inlineCompletion.maxContextLines` | `50` | Context lines before cursor (10–200) |
| `externcashai.inlineCompletion.temperature` | `0.2` | Sampling temperature (0–2) |
| `externcashai.inlineCompletion.maxTokens` | `200` | Max tokens to generate (50–1000) |
| `externcashai.autoUpdate.enabled` | `true` | Auto-check for updates |

## Status Bar

- `✓ ExternCashAI (N)` — connected, N models available
- `⊘ ExternCashAI` — API key not set
- `⚠ ExternCashAI` — connection error

Click the status bar item for quick access to actions.

## Sidebar Panel

The extension adds a sidebar panel with:

- **Connection status** and API key management
- **Available models** list with enable/disable toggles
- **Usage statistics** — tokens consumed per model, request count

## Requirements

- VS Code **1.104.0** or later
- GitHub Copilot extension installed
- ExternCashAI API key

## License

Proprietary. All rights reserved.
