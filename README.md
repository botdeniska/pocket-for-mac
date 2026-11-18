# Pocket for Mac — страница

Страница Pocket for Mac на GitHub Pages — https://botdeniska.github.io/pocket-for-mac/: скачать
помощник для Mac, как начать, политика конфиденциальности. На неё ведёт гайд «Как начать» в
приложении iPhone (`HelperDownload.pageURL`). Сборки нет: Pages публикует папку `docs/` ветки
`main` как есть.

| Файл | Что это |
|---|---|
| `docs/index.html` | главная: помощник, как начать, если Mac не находится |
| `docs/privacy.html` | политика конфиденциальности (ссылка для App Store Connect) |
| Releases → `Pocket-for-Mac-Helper.dmg` | помощник; кнопка «Скачать для Mac» всегда ведёт на последний выпуск |

## Выпуск помощника

1. В репозитории приложения: `scripts/release-helper.sh` → нотаризованный DMG в
   `build/release-helper/PocketMacHelper-<версия>-<сборка>.dmg`.
2. Загрузите его в выпуск GitHub под постоянным именем — ссылка
   `releases/latest/download/Pocket-for-Mac-Helper.dmg` не меняется:

   ```bash
   cp build/release-helper/PocketMacHelper-<версия>-<сборка>.dmg /tmp/Pocket-for-Mac-Helper.dmg
   gh release create v<версия> /tmp/Pocket-for-Mac-Helper.dmg \
     --repo botdeniska/pocket-for-mac --title "Pocket for Mac Helper <версия>"
   ```

Пока выпуска с этим файлом нет, вместо кнопки «Скачать для Mac» страница пишет, что помощник
готовится к выпуску; с выпуском показывает его версию.

## Проверить локально

```bash
python3 -m http.server -d docs 8000   # http://localhost:8000
```
