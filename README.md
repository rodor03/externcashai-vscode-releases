# ExternCashAI — VS Code Extension

VS Code расширение для использования ExternCash AI через нативный интерфейс GitHub Copilot.

## Возможности

- **Copilot Chat** — все модели сервера доступны в выпадающем списке Copilot Chat
- **Inline Completion** — tab-автокомплит (ghost text) при наборе кода
- **Tool Calling** — поддержка вызова инструментов (function calling)
- **Thinking/Reasoning** — поддержка reasoning-моделей
- **Vision** — поддержка мультимодальных моделей (изображения)

## Требования

- **VS Code Insiders** — расширение использует proposed API (`chatProvider`), который доступен только в [Insiders](https://code.visualstudio.com/insiders/) версии
- Запуск с флагом `--enable-proposed-api`:
  ```bash
  code-insiders --enable-proposed-api externcash.externcashai
  ```

> **Примечание:** в обычной (stable) версии VS Code расширение не активируется. Используйте VS Code Insiders.

## Установка

1. Скачайте последний `.vsix` файл из [Releases](https://github.com/rodor03/externcashai-vscode-releases/releases)
2. В VS Code Insiders: `Extensions` → `...` → `Install from VSIX...`
3. Перезагрузите VS Code Insiders

Или через терминал:
```bash
code-insiders --install-extension externcashai-0.1.0.vsix
```

## Настройка

1. Откройте Command Palette (`Ctrl+Shift+P`)
2. Выполните `ExternCashAI: Set API Key`
3. Введите ваш API-ключ

Модели появятся в Copilot Chat, а tab-автокомплит заработает автоматически.

## Команды

| Команда | Описание |
|---------|----------|
| `ExternCashAI: Set API Key` | Установить/обновить API-ключ |
| `ExternCashAI: Quick Actions` | Меню быстрых действий (клик по статусбару) |
| `ExternCashAI: Toggle Inline Completion` | Включить/выключить tab-автокомплит |
| `ExternCashAI: Select Inline Completion Model` | Выбрать модель для автокомплита |

## Лицензия

Proprietary. All rights reserved.
