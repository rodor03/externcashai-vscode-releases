[**Русский**](README.ru.md) | English

# ExCashAI — VS Code / Cursor Extension

> **Website:** [excash.org](https://excash.org) · **Source code** (private) · **Releases & builds:** [rodor03/externcashai-vscode-releases](https://github.com/rodor03/externcashai-vscode-releases)

Connects the ExCash AI server as a GitHub Copilot Chat provider in **VS Code**, or as Cursor BYOK (Bring Your Own Key) with inline completions in **Cursor**.

## Features

- **Copilot Chat Integration** (VS Code) — all server models available in the Copilot Chat model dropdown
- **Cursor BYOK** (Cursor) — Apply API key + Sync models into Cursor Agent settings
- **Inline Code Completion** — tab-autocomplete with ghost text suggestions while typing
- **Tool Calling** — full support for function/tool invocation
- **Thinking/Reasoning** — support for reasoning-enabled models (extended thinking)
- **Vision** — support for multimodal models (image input)
- **Token Tracking** — real-time token consumption statistics in the sidebar
- **Model Management** — enable/disable specific models, per-model thinking settings
- **Auto-Update** — automatic update checking via GitHub Releases
- **Model Hiding** (VS Code) — hide built-in Copilot models from the dropdown

## Installation

1. Download the `.vsix` file from [Releases](https://github.com/rodor03/externcashai-vscode-releases/releases)
2. In VS Code or Cursor: `Extensions` → `...` → `Install from VSIX...`
3. Restart the editor

## Setup (VS Code)

1. Open Command Palette (`Ctrl+Shift+P`)
2. Run `ExCashAI: Set API Key`
3. Enter your `sk-...` key

Models appear in Copilot Chat; tab-autocomplete starts automatically. Requires the GitHub Copilot extension.

## Setup (Cursor BYOK)

1. Install the same `.vsix` in Cursor and set the API key (sidebar or `ExCashAI: Set API Key`)
2. In the ExCashAI sidebar: **Apply to Cursor** (writes key + model merge into Cursor `state.vscdb`)
3. Fully quit and restart Cursor (Reload Window is not enough)
4. Use `ex-…` models for ExternCash. **Use Cursor models** soft-disables OpenAI BYOK so Composer/Pro work again (key/URL stay; Apply re-enables). **Hide/Show Cursor models** toggles native picker entries (best-effort).
5. Smoke-test Agent with an `ex-…` model

Then use **Sync models** after changing enable/disable or reasoning settings in the sidebar.

### Model ids and `/v1`

- Models are written as `ex-<realId>` and, for thinking models, `ex-<realId>(effort)` (ASCII effort allowlist).
- `openAIBaseUrl` must include the `/v1` path (the extension rewrites misconfigured URLs without `/v1`).
- A successful Apply fingerprint does **not** prove Agent already works — restart + smoke is required.

### Clipboard fallback

If the `cursor` CLI is missing, Apply copies the API key to the clipboard so you can paste it in **Cursor Settings → Models** manually (enterprise / locked environments).

### Threat / uninstall notes

- Do not log or share the raw API key; Copy/Apply use the key only in the Extension Host.
- Uninstall may leave `ex-*` entries in Cursor’s settings blob; cleaning them is a separate companion/backend `ex-` strip DoD (not part of this extension alone).

## Commands

| Command | Description | Host |
|---------|-------------|------|
| `ExCashAI: Set API Key` | Set or update API key | both |
| `ExCashAI: Quick Actions` | Quick actions menu (status bar click) | both |
| `ExCashAI: Toggle Inline Completion` | Enable/disable tab-autocomplete | both |
| `ExCashAI: Select Inline Completion Model` | Choose model for autocomplete | both |
| `ExCashAI: Apply to Cursor` | Write key + models to Cursor | Cursor |
| `ExCashAI: Sync models to Cursor` | Sync model list after Apply | Cursor |
| `ExCashAI: Select Chat Model` | Choose model for Copilot Chat | VS Code |
| `ExCashAI: Check for Updates` | Manually check for extension updates | both |
| `ExCashAI: Hide Builtin Copilot Models` | Hide built-in Copilot models | VS Code |
| `ExCashAI: Show Builtin Copilot Models` | Restore hidden built-in models | VS Code |

## Chat Participant (VS Code)

Type `@externcashai` in Copilot Chat to access built-in commands:

| Command | Description |
|---------|-------------|
| `@externcashai stats` | Show context and token usage statistics |
| `@externcashai models` | List available models |

## Settings

| Setting | Default | Description |
|---------|---------|-------------|
| `externcashai.inlineCompletion.enabled` | `true` | Enable tab-autocomplete |
| `externcashai.inlineCompletion.model` | `claude-haiku-4-5` | Model for autocomplete (default: Claude Haiku 4.5) |
| `externcashai.inlineCompletion.debounceDelay` | `600` | Delay before request (ms, 100–2000) |
| `externcashai.inlineCompletion.maxContextLines` | `50` | Context lines before cursor (10–200) |
| `externcashai.inlineCompletion.temperature` | `0.2` | Sampling temperature (0–2) |
| `externcashai.inlineCompletion.maxTokens` | `200` | Max tokens to generate (50–1000) |
| `externcashai.autoUpdate.enabled` | `true` | Auto-check for updates |

## Status Bar

- `✓ ExCashAI (N)` — connected, N models available
- `⊘ ExCashAI` — API key not set
- `⚠ ExCashAI` — connection error

Click the status bar item for quick access to actions.

## Sidebar Panel

The extension adds a sidebar panel with:

- **Connection status** and API key management
- **Available models** list with enable/disable toggles
- **Cursor section** (Cursor only) — Apply / Copy key / Sync
- **Usage statistics** — tokens consumed per model, request count

## Requirements

- VS Code **1.104.0** or later, or a compatible Cursor build
- GitHub Copilot extension (VS Code path only)
- ExCashAI API key
- For Cursor Apply/Sync: `sqlite3` and the `cursor` CLI when available

## License

Proprietary. All rights reserved.
