Русский | [**English**](README.md)

# ExCashAI — VS Code Extension

> **Сайт:** [excash.org](https://excash.org) · **Исходный код** (приватный) · **Релизы и билды:** [rodor03/externcashai-vscode-releases](https://github.com/rodor03/externcashai-vscode-releases)

VS Code расширение для подключения ExCash AI сервера как нативного провайдера GitHub Copilot Chat с inline-автодополнением кода.

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

## Установка

1. Скачайте `.vsix` файл из [Releases](https://github.com/rodor03/externcashai-vscode-releases/releases)
2. В VS Code: `Extensions` → `...` → `Install from VSIX...`
3. Перезапустите VS Code

## Настройка

1. Откройте Command Palette (`Ctrl+Shift+P`)
2. Выполните `ExCashAI: Set API Key`
3. Введите ваш `sk-...` ключ

Готово! Модели появятся в Copilot Chat, а tab-автокомплит заработает автоматически.

## Команды

| Команда | Описание |
|---------|----------|
| `ExCashAI: Set API Key` | Установить/обновить API-ключ |
| `ExCashAI: Quick Actions` | Меню быстрых действий (клик по статусбару) |
| `ExCashAI: Toggle Inline Completion` | Включить/выключить tab-автокомплит |
| `ExCashAI: Select Inline Completion Model` | Выбрать модель для автокомплита |
| `ExCashAI: Select Chat Model` | Выбрать модель для Copilot Chat |
| `ExCashAI: Check for Updates` | Проверить наличие обновлений |
| `ExCashAI: Hide Builtin Copilot Models` | Скрыть встроенные модели Copilot |
| `ExCashAI: Show Builtin Copilot Models` | Восстановить скрытые встроенные модели |

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

- `✓ ExCashAI (N)` — подключено, N моделей доступно
- `⊘ ExCashAI` — API-ключ не установлен
- `⚠ ExCashAI` — ошибка подключения

Нажмите на статусбар для быстрого доступа к действиям.

## Боковая панель

Расширение добавляет боковую панель с:

- **Статус подключения** и управление API-ключом
- **Список моделей** с переключателями включения/отключения
- **Статистика использования** — расход токенов по моделям, количество запросов

## Требования

- VS Code **1.104.0** или новее
- Установленное расширение GitHub Copilot
- API-ключ ExCashAI

## Лицензия

Proprietary. All rights reserved.
