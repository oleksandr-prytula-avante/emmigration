# Immigration Research Script

Готовый каркас для исследования всех 193 стран-членов ООН через OpenAI API с web search и сохранением результата в JSON.

## Что внутри

- `countries.un-members-193.json` - список 193 стран-членов ООН.
- `research_prompt.md` - расширенный промпт с подстановками `{{COUNTRY}}` и `{{TODAY}}`.
- `immigration_research.mjs` - скрипт, который вызывает OpenAI API, получает структурированный JSON и сохраняет прогресс.
- `package.json` - минимальные зависимости.

## Запуск

```bash
npm install
export OPENAI_API_KEY="your_api_key"
npm run research
```

Проверка на одной стране:

```bash
npm run research:test-one
```

Полезные параметры:

```bash
node immigration_research.mjs --country Portugal
node immigration_research.mjs --limit 10
node immigration_research.mjs --start Germany
node immigration_research.mjs --out data/research.json
node immigration_research.mjs --model gpt-5.6
```

Скрипт сохраняет результат после каждой страны, поэтому его можно безопасно перезапускать.

## Dashboard

Одностраничный dashboard лежит в `dashboard/index.html`.

Если открыт локальный preview, перейдите на:

```text
http://localhost:4174/
```

Нажмите `Загрузить JSON` и выберите файл результата, например:

```text
data/immigration-research.json
```

Dashboard поддерживает поиск, фильтр по валидности, максимальному доходу, налогу и сроку до гражданства.
# emmigration
