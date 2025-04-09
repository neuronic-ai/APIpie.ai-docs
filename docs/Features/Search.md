---
id: search
title: Inline Search
slug: /search
sidebar_position: 15
---

<div align="center">
  <img src="https://apipie.ai/docs/img/Features/pooling-banner.png" alt="Search Feature Banner" width="100%" />
</div>

Enable any model to answer with real-time, verifiable information using **Inline Search** — our built-in web search and grounding system that works seamlessly with OpenAI-compatible APIs. With a single request, you can inject live context from the internet into your prompt, no browser tools, agents, or plugins required.

## What is Inline Search?

Inline Search enhances any model by integrating real-time search results and scraped content directly into the prompt — without requiring the model to have built-in browsing capabilities.

When enabled, the system:

1. Performs X number of live searches using top-ranked search engines
2. Fetches and ranks up to 100 results per search
3. Scrapes the top results, cleans the text, removes noise
4. Appends that content to your prompt before model invocation

This allows even legacy models to answer with fresh knowledge, and it works **automatically with any model or app built on the OpenAI chat format.**

---

## Why Use Inline Search?

- **Fresh data in any model** – including GPT-3.5, Claude, LLaMA, Mixtral, and more
- **No special setup** – works out of the box in standard OpenAI API format
- **Customize search volume and scope**
- **Simple to configure via request body**

> ⚠️ *Note*: Because this uses live search + scraping, expect an added delay of 1–6 seconds total, depending on complexity of the web pages we are pulling data from. We have to render the javascript before we can pull the data.

---

## Quick Start (OpenAI Format Example)

Use `web_search_options` in your request to instantly enable Inline Search.

'''bash
curl -X POST 'https://apipie.ai/v1/chat/completions' \
-H 'Authorization: Bearer <API_KEY>' \
-H 'Content-Type: application/json' \
-d '{
  "user": "qa_test",
  "stream": true,
  "model": "openai/gpt-4o",
  "web_search_options": {
    "search_context_size": "medium"
  },
  "max_tokens": 500,
  "messages": [
    {
      "role": "user",
      "content": "Who was the best and worst president of the united states, quantifiable and verifiable?"
    }
  ]
}'
'''

### Options for `web_search_options.search_context_size`

| Value  | Description                                 |
|--------|---------------------------------------------|
| `low`  | Small content injection (~1–2 links)        |
| `medium` | Moderate (~3–4 results, ~3–5K characters) |
| `high` | Full web grounding (~5–6 results, ~10K+)    |

---

## Alternate Inline Search via Payload (Advanced)

You can also enable search with deeper control using the `online` flag and extended parameters:

| Field           | Description                                                |
|-----------------|------------------------------------------------------------|
| `online`        | Enable inline search grounding (`true` or `false`)         |
| `searches`      | Number of search queries to perform (default: 1)           |
| `pull`          | Max results to pull from each search (default: 20)         |
| `use`           | How many of those results to append to the prompt (default: 3) |
| `scrape_length` | Max number of characters to include from each scrape       |
| `search_lang`   | Language code for results (e.g. `"en"`)                    |
| `search_geo`    | Geolocation code (e.g. `"US"`)                             |

'''json
{
  "user": "user123",
  "model": "claude-3-5-sonnet",
  "online": true,
  "searches": 2,
  "pull": 10,
  "use": 4,
  "scrape_length": 12000,
  "search_lang": "en",
  "search_geo": "US",
  "messages": [
    { "role": "user", "content": "Summarize the most recent news about generative AI in healthcare." }
  ]
}
'''

---

## Using Inline CLI (Prompt Commands)

You can also enable search directly in the prompt with these Inline CLI commands:

| Command         | Behavior                             |
|----------------|--------------------------------------|
| `:search`       | Fast search (1 query, 3 results)     |
| `:searchmore`   | More results (1 query, 5 results)    |
| `:deepsearch`   | Broad + deep search (3 queries)      |
| `:setsearchlang:en` | Set language to English          |
| `:setsearchgeo:US`  | Set geo location to United States|

Example prompt:

'''json
{ "content": "Summarize today’s major AI headlines :deepsearch :setsearchlang:en :setsearchgeo:US" }
'''

---

## Direct Use of the Search & Scrape APIs

For users needing lower-level control or standalone search capabilities, we also offer public API endpoints.

### POST `/v1/search`

'''json
{
  "query": "latest AI developments",
  "search_provider": "google",
  "search": "google",
  "geo": "us",
  "lang": "en",
  "results": 10,
  "safeSearch": -1,
  "user": "user123"
}
'''

Returns a list of ranked search results with URLs, titles, and descriptions.

---

### POST `/v1/scrape`

'''json
{
  "url": "https://example.com/article",
  "format": "parsed"
}
'''

Returns parsed content:

- `title`
- `textContent`
- `excerpt`
- `hrefs[]`

---

## Developer Tips

- Works with **all models**, including offline-only models like GPT-3.5 or Mistral
- Use `web_search_options` for OpenAI-style apps
- Use `online`, `pull`, `use`, `scrape_length` for full control
- Combine with `memory`, `integrity`, and `shaping` for robust agents
- Monitor latency: search grounding can add 1–6s per request

---

## Example: High-Precision Search

'''bash
curl -X POST 'https://apipie.ai/v1/chat/completions' \
-H 'Authorization: Bearer <API_KEY>' \
-H 'Content-Type: application/json' \
--data-raw '{
  "user": "research_bot",
  "model": "mixtral",
  "online": true,
  "searches": 3,
  "pull": 15,
  "use": 5,
  "scrape_length": 15000,
  "search_lang": "en",
  "search_geo": "US",
  "messages": [
    { "role": "user", "content": "What are the leading companies developing open-source LLMs in 2025?" }
  ]
}'
'''

---

## Conclusion

Inline Search brings live, trusted information to **any model or application** using the standard OpenAI request format or advanced options. Whether you're building agents, research assistants, or chatbots — this feature ensures your responses are grounded in the real world.

Try it out with `web_search_options`, `online: true`, or `:deepsearch` in your next request.

---

## Related Links

- [Chat Completions API](https://apipie.ai/docs/api/chatcompletions)
- [Search API](https://apipie.ai/docs/api/search)
- [Scrape API](https://apipie.ai/docs/api/scrape)
- [Vectors API](https://apipie.ai/docs/api/vectors)
