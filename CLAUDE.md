# VRNas — лендинг по макету Figma

Вёрстка лендинга VR-сервиса VRNas один в один с макетом, по секциям.

- **Макет:** https://www.figma.com/design/3Ux8qit10eHYzaWG6gS5lb/VRNas--Copy---Copy-?node-id=0-1
- `fileKey: 3Ux8qit10eHYzaWG6gS5lb`, страница **Homepage** — `7:21` (1440×9899)

## Главное правило

**Перед задачей прочитай нужный документ из `documentation/`. После задачи зафиксируй, что изменилось:** обнови существующий документ или создай новый, по одному на решение, в формате «что сделали / почему / ошибки».

| Документ | Когда читать |
|---|---|
| `documentation/section-workflow.md` | перед каждой новой секцией |
| `documentation/figma-assets.md` | скачиваешь иконки, картинки или SVG из Figma |
| `documentation/decor-layer.md` | волны, сетки, свечения, фоновый декор |
| `documentation/layout.md` | раскладка, контейнер, отступы |
| `documentation/responsive.md` | адаптив, брейкпоинты, мобилка |
| `documentation/stack.md` | токены цветов и шрифтов, стек, именование классов |
| `documentation/deploy.md` | деплой на GitHub Pages, пути к ассетам |

Новый документ добавляй в эту таблицу. Когда секция готова, пользователь запускает `/update-docs` (`.claude/skills/update-docs/`).

## Стек и структура

Чистый HTML + CSS, классы по БЭМ, цвета только через токены в `:root`.

```
index.html          — вся страница, секции идут по порядку
css/style.css       — токены, стили по секциям, в конце @media
assets/icons/       — SVG-иконки
assets/images/      — фото (PNG) и декор (SVG)
documentation/      — по одному документу на решение
```

Figma MCP подключён в `.mcp.json`. Если инструментов Figma нет, запусти `/mcp` → figma → Authenticate.

Запуск: превью `site` из `.claude/launch.json` (`python3 -m http.server 5173`).

Прод: https://tretyakweb.github.io/vrnas-landing/ — GitHub Pages, деплоится сам при пуше в `main`.

## Прогресс

| # | Секция | Node ID | Статус |
|---|---|---|---|
| 1 | Header + Hero + Why Choose us (карточка) | `54:1422`, `9:4`, `56:2117` и др. | ✅ готово |
| 2 | About Us | `21:12732` | ⏳ следующая |
| 3 | Our Service | `84:3874` | — |
| 4 | Why Choose Us (с картинками) | `34:95` | — |
| 5 | How to Get Started | `57:2640` | — |
| 6 | Testimonial | `56:1971` | — |
| 7 | Our Pricing | `62:2143` | — |
| 8 | Our Trusted Partners | `56:1972` | — |
| 9 | Our Articles | `50:2055` | — |
| 10 | Subscribe | `89:4329` | — |
| 11 | Footer | `54:1447` | — |

**Открытые TODO:** бургер-меню для мобилки (см. `documentation/responsive.md`).
