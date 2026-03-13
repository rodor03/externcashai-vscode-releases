Русский | [**English**](README.md)

# ExternCashAI — VS Code Extension

VS Code расширение для подключения ExternCash AI сервера как нативного провайдера GitHub Copilot Chat с inline-автодополнением кода.

## Возможности

- **Copilot Chat** — все модели сервера доступны в выпадающем списке Copilot Chat
- **Inline Completion** — tab-автокомплит (ghost text) при наборе кода
- **Tool Calling** — поддержка вызова инструментов (function calling)
- **Thinking/Reasoning** — поддержка reasoning-моделей (расширенное мышление)
- **Vision** — поддержка мультимодальных моделей (изображения)
- **Отслеживание токенов** — статистика расхода токенов в реальном времени в боковой панели
- **Управление моделями** — включение/отключение моделей, настройки thinking для каждой модели
- **Автообновление** — автоматическая проверка обновлений через GitHub Releases
- **Скрытие моделей** — скрытие встроенных моделей Copilot из выпадающего списка

## Поддерживаемые модели

| Провайдер | Модели |
|-----------|--------|
| Anthropic | Claude Opus 4.6, Claude Sonnet 4.6, Claude Haiku 4.5 |
| Google | Gemini 3.1 Pro, Gemini 2.5 Pro, Gemini 3 Pro/Flash |
| OpenAI | GPT-5 Mini, GPT-5.4, GPT-5.3 Codex |
| xAI | Grok Code Fast 1 |

## Установка

1. Скачайте `.vsix` файл из [Releases](https://github.com/rodor03/externcashai-vscode-releases/releases)
2. В VS Code: `Extensions` → `...` → `Install from VSIX...`
3. Перезапустите VS Code

## Настройка

1. Откройте Command Palette (`Ctrl+Shift+P`)
2. Выполните `ExternCashAI: Set API Key`
3. Введите ваш `sk-...` ключ

Готово! Модели появятся в Copilot Chat, а tab-автокомплит заработает автоматически.

## Команды

| Команда | Описание |
|---------|----------|
| `ExternCashAI: Set API Key` | Установить/обновить API-ключ |
| `ExternCashAI: Quick Actions` | Меню быстрых действий (клик по статусбару) |
| `ExternCashAI: Toggle Inline Completion` | Включить/выключить tab-автокомплит |
| `ExternCashAI: Select Inline Completion Model` | Выбрать модель для автокомплита |
| `ExternCashAI: Select Chat Model` | Выбрать модель для Copilot Chat |
| `ExternCashAI: Check for Updates` | Проверить наличие обновлений |
| `ExternCashAI: Hide Builtin Copilot Models` | Скрыть встроенные модели Copilot |
| `ExternCashAI: Show Builtin Copilot Models` | Восстановить скрытые встроенные модели |

## Chat Participant

Введите `@externcashai` в Copilot Chat для доступа к встроенным командам:

| Команда | Описание |
|---------|----------|
| `@externcashai stats` | Статистика использования контекста и токенов |
| `@externcashai models` | Список доступных моделей |

## Настройки

| Настройка | По умолчанию | Описание |
|-----------|-------------|----------|
| `externcashai.inlineCompletion.enabled` | `true` | Включить tab-автокомплит |
| `externcashai.inlineCompletion.model` | `""` | Модель для автокомплита (по умолчанию: Claude Haiku 4.5) |
| `externcashai.inlineCompletion.debounceDelay` | `400` | Задержка перед запросом (мс, 100–2000) |
| `externcashai.inlineCompletion.maxContextLines` | `50` | Строк контекста перед курсором (10–200) |
| `externcashai.inlineCompletion.temperature` | `0.2` | Температура сэмплирования (0–2) |
| `externcashai.inlineCompletion.maxTokens` | `200` | Макс. токенов для генерации (50–1000) |
| `externcashai.autoUpdate.enabled` | `true` | Автоматическая проверка обновлений |

## Статусбар

- `✓ ExternCashAI (N)` — подключено, N моделей доступно
- `⊘ ExternCashAI` — API-ключ не установлен
- `⚠ ExternCashAI` — ошибка подключения

Нажмите на статусбар для быстрого доступа к действиям.

## Боковая панель

Расширение добавляет боковую панель с:

- **Статус подключения** и управление API-ключом
- **Список моделей** с переключателями включения/отключения
- **Статистика использования** — расход токенов по моделям, количество запросов

## Требования

- VS Code **1.104.0** или новее
- Установленное расширение GitHub Copilot
- API-ключ ExternCashAI

## Лицензия

Proprietary. All rights reserved.
