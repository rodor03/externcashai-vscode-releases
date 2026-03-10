# ExternCashAI — VS Code Extension

VS Code расширение для использования ExternCash AI через нативный интерфейс GitHub Copilot.

## Возможности

- **Copilot Chat** — все модели сервера доступны в выпадающем списке Copilot Chat
- **Inline Completion** — tab-автокомплит (ghost text) при наборе кода
- **Tool Calling** — поддержка вызова инструментов (function calling)
- **Thinking/Reasoning** — поддержка reasoning-моделей
- **Vision** — поддержка мультимодальных моделей (изображения)

## Установка

### Автоматическая (одной командой)

Скачивает и устанавливает последнюю версию расширения.

**Linux / macOS:**
```bash
curl -sL "$(curl -s https://api.github.com/repos/rodor03/externcashai-vscode-releases/releases/latest | grep browser_download_url | cut -d '"' -f 4)" -o /tmp/externcashai.vsix && code --install-extension /tmp/externcashai.vsix && rm /tmp/externcashai.vsix
```

**Windows (PowerShell):**
```powershell
$u=(Invoke-RestMethod https://api.github.com/repos/rodor03/externcashai-vscode-releases/releases/latest).assets[0].browser_download_url; Invoke-WebRequest $u -OutFile "$env:TEMP\externcashai.vsix"; code --install-extension "$env:TEMP\externcashai.vsix"; Remove-Item "$env:TEMP\externcashai.vsix"
```

<details>
<summary><b>VS Code Insiders</b></summary>

**Linux / macOS:**
```bash
curl -sL "$(curl -s https://api.github.com/repos/rodor03/externcashai-vscode-releases/releases/latest | grep browser_download_url | cut -d '"' -f 4)" -o /tmp/externcashai.vsix && code-insiders --install-extension /tmp/externcashai.vsix && rm /tmp/externcashai.vsix
```

**Windows (PowerShell):**
```powershell
$u=(Invoke-RestMethod https://api.github.com/repos/rodor03/externcashai-vscode-releases/releases/latest).assets[0].browser_download_url; Invoke-WebRequest $u -OutFile "$env:TEMP\externcashai.vsix"; code-insiders --install-extension "$env:TEMP\externcashai.vsix"; Remove-Item "$env:TEMP\externcashai.vsix"
```

</details>

### Ручная установка

1. Скачайте последний `.vsix` файл из [Releases](https://github.com/rodor03/externcashai-vscode-releases/releases)
2. В VS Code: `Extensions` → `...` → `Install from VSIX...`
3. Перезагрузите VS Code

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
