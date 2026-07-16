Русский | [**English**](README.md)

# ExCashAI — расширение VS Code / Cursor

> **Сайт:** [excash.org](https://excash.org) · **Исходный код** (приватный) · **Релизы и билды:** [rodor03/externcashai-vscode-releases](https://github.com/rodor03/externcashai-vscode-releases)

Подключает сервер ExCash AI как провайдер GitHub Copilot Chat в **VS Code** или как Cursor BYOK (Bring Your Own Key) с inline-автодополнением в **Cursor**.

## Возможности

- **Copilot Chat** (VS Code) — модели сервера в выпадающем списке Copilot Chat
- **Cursor BYOK** (Cursor) — Apply ключа и Sync моделей в настройки Cursor Agent
- **Inline Completion** — tab-автокомплит (ghost text)
- **Tool Calling** — вызов инструментов (function calling)
- **Thinking/Reasoning** — reasoning-модели
- **Vision** — мультимодальные модели (изображения)
- **Отслеживание токенов** — статистика в боковой панели
- **Управление моделями** — вкл/выкл, настройки thinking
- **Автообновление** — проверка через GitHub Releases
- **Скрытие моделей** (VS Code) — скрытие встроенных моделей Copilot

## Установка

1. Скачайте `.vsix` из [Releases](https://github.com/rodor03/externcashai-vscode-releases/releases)
2. В VS Code или Cursor: `Extensions` → `...` → `Install from VSIX...`
3. Перезапустите редактор

## Настройка (VS Code)

1. Command Palette (`Ctrl+Shift+P`)
2. `ExCashAI: Установить API-ключ`
3. Введите `sk-...`

Модели появятся в Copilot Chat; tab-автокомплит заработает автоматически. Нужно расширение GitHub Copilot.

## Настройка (Cursor BYOK)

1. Установите тот же `.vsix` в Cursor и задайте API-ключ (сайдбар или `ExCashAI: Установить API-ключ`)
2. В сайдбаре ExCashAI: **Применить в Cursor** (ключ + merge моделей в `state.vscdb`)
3. Полностью закройте и перезапустите Cursor (Reload Window недостаточно)
4. Для ExternCash выбирайте `ex-…`. **Модели Cursor** мягко выключает OpenAI BYOK (Composer/Pro снова работают; ключ/URL остаются; Apply включает ExternCash снова). **Скрыть/Показать модели Cursor** — native в picker (best-effort).
5. Проверьте Agent на модели `ex-…`

Далее **Синхронизировать модели** — после смены вкл/выкл или reasoning в сайдбаре.

### Id моделей и `/v1`

- В Cursor пишутся `ex-<realId>` и для thinking — `ex-<realId>(effort)`.
- `openAIBaseUrl` должен содержать путь `/v1` (расширение перезаписывает URL без `/v1`).
- Успешный fingerprint Apply ≠ «Agent уже работает» — нужен рестарт и smoke.

### Fallback буфера обмена

Если нет CLI `cursor`, Apply копирует ключ в буфер — вставьте вручную в **Cursor Settings → Models** (enterprise / locked).

### Угрозы / удаление

- Не логируйте и не шарьте сырой API-ключ; Copy/Apply используют ключ только в Extension Host.
- После uninstall в blob Cursor могут остаться `ex-*`; очистка — отдельный companion/backend DoD (`ex-` strip).

## Команды

| Команда | Описание | Хост |
|---------|----------|------|
| `ExCashAI: Установить API-ключ` | Установить/обновить ключ | оба |
| `ExCashAI: Быстрые действия` | Меню (клик по статусбару) | оба |
| `ExCashAI: Переключить inline…` | Вкл/выкл tab-автокомплит | оба |
| `ExCashAI: Выбрать модель inline…` | Модель автокомплита | оба |
| `ExCashAI: Применить в Cursor` | Запись ключа и моделей | Cursor |
| `ExCashAI: Синхронизировать модели с Cursor` | Sync после Apply | Cursor |
| `ExCashAI: Выбрать модель чата` | Copilot Chat | VS Code |
| `ExCashAI: Проверить обновления` | Обновления | оба |
| `ExCashAI: Скрыть встроенные модели Copilot` | Скрыть встроенные модели | VS Code |
| `ExCashAI: Показать встроенные модели Copilot` | Восстановить встроенные модели | VS Code |

## Chat Participant (VS Code)

В Copilot Chat: `@externcashai`:

| Команда | Описание |
|---------|----------|
| `@externcashai stats` | Статистика контекста и токенов |
| `@externcashai models` | Список моделей |

## Настройки

| Настройка | По умолчанию | Описание |
|-----------|-------------|----------|
| `externcashai.inlineCompletion.enabled` | `true` | Tab-автокомплит |
| `externcashai.inlineCompletion.model` | `claude-haiku-4-5` | Модель (по умолчанию Claude Haiku 4.5) |
| `externcashai.inlineCompletion.debounceDelay` | `600` | Задержка (мс, 100–2000) |
| `externcashai.inlineCompletion.maxContextLines` | `50` | Строк контекста (10–200) |
| `externcashai.inlineCompletion.temperature` | `0.2` | Температура (0–2) |
| `externcashai.inlineCompletion.maxTokens` | `200` | Макс. токенов (50–1000) |
| `externcashai.autoUpdate.enabled` | `true` | Автопроверка обновлений |

## Статусбар

- `✓ ExCashAI (N)` — подключено
- `⊘ ExCashAI` — нет ключа
- `⚠ ExCashAI` — ошибка

## Боковая панель

- Статус и API-ключ
- Список моделей (вкл/выкл)
- Секция **Cursor** (только в Cursor) — Apply / Copy / Sync
- Статистика токенов

## Требования

- VS Code **1.104.0+** или совместимый Cursor
- GitHub Copilot (только путь VS Code)
- API-ключ ExCashAI
- Для Apply/Sync в Cursor: `sqlite3` и CLI `cursor` (если доступен)

## Лицензия

Proprietary. All rights reserved.
