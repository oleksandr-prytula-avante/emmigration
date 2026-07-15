# Immigration Research Script

A ready-to-use research scaffold for checking all 193 UN member states through the OpenAI API with web search and saving structured results to JSON.

## Contents

- `countries.un-members-193.json` - list of 193 UN member states.
- `research_prompt.md` - detailed research prompt with `{{COUNTRY}}` and `{{TODAY}}` placeholders.
- `immigration_research.mjs` - script that calls the OpenAI API, requests structured JSON, and saves progress.
- `package.json` - minimal project dependencies.
- `dashboard/` - local one-page dashboard for reviewing the collected JSON.

## Run

```bash
npm install
export OPENAI_API_KEY="your_api_key"
npm run research
```

Run a single-country test:

```bash
npm run research:test-one
```

Useful options:

```bash
node immigration_research.mjs --country Portugal
node immigration_research.mjs --limit 10
node immigration_research.mjs --start Germany
node immigration_research.mjs --out data/research.json
node immigration_research.mjs --model gpt-5.6
```

The script saves results after each country, so it is safe to stop and restart.

## Dashboard

The one-page dashboard is located at `dashboard/index.html`.

If the local preview server is running, open:

```text
http://localhost:4174/
```

Click `Load JSON` and select the result file, for example:

```text
data/immigration-research.json
```

The dashboard supports search, default eligible filtering, fully matched filtering, income/tax/citizenship-year filters, and sorting by citizenship/passport timeline, country, and taxation.
