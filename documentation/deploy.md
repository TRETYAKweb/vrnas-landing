# Деплой на GitHub Pages

**Сайт:** https://tretyakweb.github.io/vrnas-landing/
**Репозиторий:** https://github.com/TRETYAKweb/vrnas-landing (публичный)

## Что сделали

- Включили GitHub Pages через API: источник — ветка `main`, папка `/` (корень).
  ```bash
  gh api -X POST repos/TRETYAKweb/vrnas-landing/pages -f 'source[branch]=main' -f 'source[path]=/'
  ```
- Деплой автоматический: каждый `git push` в `main` пересобирает сайт за ~1 минуту.
- Статус последней сборки: `gh api repos/TRETYAKweb/vrnas-landing/pages/builds/latest --jq .status`.

## Почему так

- Сборки нет, сайт — статика в корне, поэтому хватает «Deploy from a branch» без GitHub Actions.
- Сайт живёт в подпапке `/vrnas-landing/`, поэтому все пути к ассетам и CSS — **только относительные** (`assets/...`, `css/...`). Путь с ведущим `/` уйдёт в корень `tretyakweb.github.io` и даст 404.

## Ошибки и подводные камни

- `.env` с Figma-токеном в `.gitignore`. Перед включением Pages проверили, что он ни разу не попадал в историю (`git log --all -- .env`): репозиторий публичный, всё в нём видно всем.
- `.md` из репо (`CLAUDE.md`, `documentation/`) Pages тоже публикует через Jekyll. Секретов там нет, так что это не проблема, но не клади туда ничего приватного.
