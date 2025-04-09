---
id: inline-cli
title: Inline CLI
slug: /inline-cli
sidebar_position: 14
---

<div align="center">
  <img src="https://apipie.ai/docs/img/Features/inlinecli-banner.png" alt="Inline CLI Feature Banner" width="100%" />
</div>

Unlock powerful real-time API control with **Inline CLI** – a breakthrough feature built directly into your prompt flow. This innovation enables developers to dynamically apply API configurations within user input, empowering advanced AI behavior with a single line of text.

## What is Inline CLI?

Inline CLI allows users to inject configuration and behavior commands into the **first or last 250 characters of any prompt** using the syntax `:command:value`. These commands are parsed before the prompt is sent to the model and can be used to persist state, override models, shape responses, and control memory, search, and more.

Inline CLI works across any OpenAI-compatible API or agent. It’s powerful, portable, and frictionless for users of all levels.

## Authentication

Use one of the following authentication methods:

- Bearer token in the `Authorization` header  
- API key via `x-api-key` header

Example headers:

'''http
Authorization: Bearer <YOUR_API_KEY>
x-api-key: <YOUR_API_KEY>
'''

## Enabling Inline CLI

Inline CLI is controlled via the `inline_cli` field in the request body. You can set:

- `"all"` — Enable all CLI features
- Comma-delimited features, e.g. `"model,search,memory"`
- `"false"` — Fully disables Inline CLI

Example:

'''json
"inline_cli": "model,shaping,integrity"
'''

## How Inline CLI Works

- Commands prefixed with `:` (colon) are extracted from the prompt
- They can be persistent (`set` commands) or temporary (for a single query)
- Some commands (like `:help`, `:getstate`) bypass model processing
- You can mix commands, like setting state and querying in one prompt

---

## Supported Commands

### 📄 Information Commands

Direct responses (no prompt processing):

| Command       | Description                                    |
|---------------|------------------------------------------------|
| `:getstate`   | Show current saved CLI settings                |
| `:help`       | Show all available Inline CLI commands         |

---

### 🤖 Model Commands

Choose or override AI models:

| Command                        | Description                                               |
|--------------------------------|-----------------------------------------------------------|
| `:setmodel:<provider>/<model>` | Persistently use specified model                         |
| `:unsetmodel`                  | Remove saved model, revert to defaults                   |
| `:answerwith<AI>`              | Use a specific provider/model once (e.g. `:answerwithgpt`) |

Supported AI aliases: `openai`, `gpt`, `claude`, `anthropic`, `grok`, `gemini`, `llama`, `deepseek`, `mistral`, `mixtral`, `smart`, `cheap`

---

### 🛠️ Shaping Commands

Customize model behavior:

| Command        | Description                       |
|----------------|-----------------------------------|
| `:beprecise`   | Lower temperature, more accurate  |
| `:bebalanced`  | Balanced configuration            |
| `:becreative`  | Higher creativity, more diverse   |
| `:becrazy`     | Maximum randomness                |
| `:becoder`     | Optimized for code responses      |
| `:avoidrepeat` | Penalize repeated tokens          |
| `:answerdiverse` | Increase answer diversity       |
| `:stayontopic` | Focus tightly on topic            |

---

### ✅ Integrity Commands

Eliminate hallucinations and ensure accurate responses:

| Command               | Description                       |
|------------------------|-----------------------------------|
| `:setintegrity`        | Enable normal integrity setting   |
| `:setsuperintegrity`   | Enable maximum integrity setting  |
| `:answerintegrity`     | Use integrity override once       |
| `:answersuperintegrity`| Use super integrity override once |
| `:unsetintegrity`      | Remove persistent integrity       |

---

### 🌐 Internet Search Commands

Enrich prompts with real-time web search:

| Command                | Description                                   |
|------------------------|-----------------------------------------------|
| `:search`              | Perform fast search                           |
| `:searchmore`          | Medium-depth search                           |
| `:deepsearch`          | Full-contextual search                        |
| `:setsearchlang:<lang>`| Set search language (e.g. `:setsearchlang:en`)|
| `:setsearchgeo:<geo>`  | Set search region (e.g. `:setsearchgeo:US`)   |

---

### 🧠 Memory Commands

Persistent conversational memory:

| Command               | Description                                      |
|------------------------|--------------------------------------------------|
| `:setmemoryon`         | Turn memory on                                   |
| `:setmemoryoff`        | Turn memory off                                  |
| `:clearmemory`         | Delete all memory for user/session              |
| `:setmemexpire:<min>`  | Set memory expiration in minutes (5-1440)       |

---

## Inline CLI vs State Parameters

| Feature           | CLI `:command`        | JSON Field             | Behavior              |
|-------------------|------------------------|-------------------------|------------------------|
| Persistent Setting| `:setmodel:gpt/4o`     | `model`, `provider`     | Stored in state        |
| One-Time Override | `:answerwithgpt`       | N/A                     | Applies once           |
| View State        | `:getstate`            | N/A                     | No model call made     |
| Persist + View    | `:setmodel:gpt/4o :getstate` | `inline_cli`, `user` | Set & view in one call |

---

## Example Prompt Usage

'''bash
curl -X POST 'https://apipie.ai/v1/chat/completions' \
-H 'Authorization: Bearer <API_KEY>' \
-H 'Content-Type: application/json' \
--data-raw '{
  "user": "12345",
  "inline_cli": "all",
  "messages": [
    { "role": "user", "content": "Tell me a fun fact :becreative :answerwithclaude" }
  ]
}'
'''

---

## API Schema Integration

Use the `ChatCompletionRequest` schema to configure:

- `inline_cli`: `"all"` or comma-delimited feature list  
- `user`: Required for memory, CLI, and tenant-based features  
- `model`, `provider`: Can be overridden by inline CLI  
- `memory`, `mem_session`, `mem_clear`: Memory state and control  
- `rag_tune`, `search_geo`, `search_lang`: RAG and search customization  
- `tools`, `tool_choice`, `tools_model`: Optional function-calling support  
- `temperature`, `top_p`, `top_k`, `penalties`: Prompt shaping controls

Full schema in API docs:  
[Chat Completions API](https://apipie.ai/docs/api/chatcompletions)

---

## Tips for Devs

- You can mix `:set` and `:getstate` to both configure and review settings
- If a user sends only info commands, the model isn’t invoked at all
- All commands are ignored by the model and intercepted by the system

---

## Conclusion

Inline CLI gives developers and users full control over AI behavior inside the natural language prompt. With built-in support across memory, model control, search, integrity, and more, it’s a one-of-a-kind system designed to **maximize customization with zero overhead**.

Start with `:help` in your prompt and build smarter agents with fewer constraints.

---

## Related Links

- [Chat Completions API](https://apipie.ai/docs/api/chatcompletions)
- [Fetch Models API](https://apipie.ai/docs/api/fetchmodels)
- [Ragtune API](https://apipie.ai/docs/api/ragtune)
- [Vectors API](https://apipie.ai/docs/api/vectors)
