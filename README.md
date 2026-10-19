# site-cicd

[![Deploy static site](https://github.com/gilian21e/site-cicd/actions/workflows/deploy.yml/badge.svg)](https://github.com/gilian21e/site-cicd/actions/workflows/deploy.yml)

Лендинг джазовой кофейни **InJazz** с автоматическим развёртыванием через GitHub Actions.

- Сайт на GitHub Pages: https://gilian21e.github.io/site-cicd/
- Тот же сайт на Vercel (нативная интеграция с GitHub): https://site-cicd-kappa.vercel.app/

## Как устроен CI/CD

При каждом `push` в ветку `main` запускается workflow [`deploy.yml`](.github/workflows/deploy.yml):

1. **Проверка HTML и CSS** (`lint`): HTMLHint проверяет разметку, Stylelint — стили.
2. **Публикация на GitHub Pages** (`deploy`): запускается только после успешной проверки.

Для pull request выполняется только проверка, поэтому ошибка в разметке не попадёт на сайт.

Проверить локально: `npm ci && npm run lint`.
