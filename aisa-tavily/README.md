# AIsa Tavily Search

Search the web and extract public page content through AIsa's Tavily-backed API relay.

## What it does

- Web search for research and source discovery
- News-focused search with recent-day filtering
- Public URL content extraction for downstream analysis

## When to use

- Research a topic on the open web
- Find sources before summarizing or comparing claims
- Look up recent news
- Extract readable content from a public URL

## Requirements

- `node`
- `AISA_API_KEY`
- Internet access with outbound requests to `https://aisa.one` and `https://api.aisa.one`

## Setup

Set your API key before running commands:

```bash
export AISA_API_KEY="your-key-here"
```

Get `AISA_API_KEY` from https://marketplace.aisa.one

## Usage

### Search

```bash
node scripts/search.mjs "query"
node scripts/search.mjs "query" -n 10
node scripts/search.mjs "query" --deep
node scripts/search.mjs "query" --topic news
```

### Options

- `-n <count>`: Number of results (default: 5, max: 20)
- `--deep`: Use advanced search for deeper research (slower, more comprehensive)
- `--topic <topic>`: Search topic - `general` (default) or `news`
- `--days <n>`: For news topic, limit to last n days

### Extract content from URL

```bash
node scripts/extract.mjs "https://example.com/article"
```

## Auth, relay, upload, and side effects

- Uses `AISA_API_KEY` for authenticated requests
- Sends search queries and public target URLs to AIsa's remote relay
- Connects to `https://aisa.one` / `https://api.aisa.one`
- Does not use OAuth
- Does not upload media or files
- This skill is for remote web search and public URL extraction, not local browser automation

## Notes

- Powered by AIsa's unified API gateway (`https://aisa.one` / `https://api.aisa.one`)
- Use `--deep` for complex research questions
- Use `--topic news` for current events
