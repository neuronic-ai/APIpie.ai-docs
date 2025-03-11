# Fetch Models

## Endpoint: GET /v1/models

[APIpie.ai](https://apipie.ai) provides this endpoint to fetch all available AI models or use one or more filters to narrow down the results.

For more information on available models and their capabilities, visit the [APIpie documentation](https://apipie.ai/docs).

## Request

### Query Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| type | string | No | Filter by type of model (llm, vision, embedding, image, voice, moderation, coding, free) |
| subtype | string | No | Filter by subtype of model (chat, fill-mask, question-answering, tts, stt, multimodal) |
| provider | string | No | Filter by provider of the model |
| combination | string | No | Filter by a combination of provider and subtype |
| enabled | integer | No | Only show enabled chat models (1 for enabled, 0 for disabled) |
| voices | parameter | No | Retrieve a complete list of available voices (use /v1/models?voices) |
| restrictions | string | No | Retrieve a complete list of available Country Restrictions (use /v1/models?restrictions) |

### Example Requests

- Get all models: `https://api.apipie.ai/v1/models`
- Filter by type: `https://api.apipie.ai/v1/models?type=llm`
- Filter by provider: `https://api.apipie.ai/v1/models?provider=openrouter`
- Filter by provider and subtype: `https://api.apipie.ai/v1/models?provider=openrouter&subtype=chat`
- Get only enabled chat models: `https://api.apipie.ai/v1/models?enabled=1&subtype=chat`
- Get all available voices: `https://api.apipie.ai/v1/models?voices`
- Get country restrictions: `https://api.apipie.ai/v1/models?restrictions`

## Response

### 200 OK - Models Response

| Property | Type | Description |
|----------|------|-------------|
| object | string | Type of the list |
| data | array | Array of model objects |

#### Model Object Properties

| Property | Type | Description |
|----------|------|-------------|
| enabled | boolean | Whether Model is enabled |
| type | string | Type of the model (llm, vision, embedding, image, voice, moderation, code) |
| subtype | string | Subtype of the model |
| provider | string | Provider of the model |
| model | string | The base model name |
| route | string | Provider specific identifier |
| description | string | Description of the Model |
| max_tokens | integer | Max cumulative tokens supported by the model |
| max_response_tokens | integer | Max tokens that this model can return in the response |
| req_price | string | Price for request - per unit |
| res_price | string | Price for response - per unit |
| price_unit | string | Price unit, the number of price_type per price |
| price_type | string | Type of the price (token, char, request, tokens, image, minute, characters, character, provider) |
| avg_cost | string | Average cost of the model, tracking actual usage (per 1000 characters) |
| latency | string | Average latency by combined prompt/response size |
| available | boolean | Availability status of the model |
| query_count | string | Total count of queries for this model |

### Example Models Response

```json
{
  "object": "list",
  "data": [
    {
      "enabled": 1,
      "type": "llm",
      "subtype": null,
      "provider": "openrouter",
      "model": "nous-capybara-7b",
      "route": "nousresearch/nous-capybara-7b",
      "description": "The Capybara series is a collection of datasets and models...",
      "max_tokens": 4096,
      "max_response_tokens": 4096,
      "req_price": "0.0000001800000000",
      "res_price": "0.0000001800000000",
      "price_type": "token",
      "price_unit": "1.00",
      "avg_cost": "0.0000912966",
      "latency": "1162/2145/6245/8234/18456/8162",
      "available": 1,
      "query_count": "310,000"
    },
    {
      "...": "Additional models not shown..."
    }
  ]
}
```

### 200 OK - Voices Response

When using the `voices` parameter, the response will contain a list of available voice models.

```json
{
  "object": "list",
  "data": [
    {
      "provider": "elevenlabs",
      "model": "eleven_multilingual_v2",
      "voice": "21m00Tcm4TlvDq8ikWAM",
      "name": "Rachel",
      "description": "accent: american, description: calm, age: young, gender: female, use case: narration"
    },
    {
      "...": "Additional models not shown..."
    }
  ]
}
```

### 200 OK - Restrictions Response

When using the `restrictions` parameter, the response will contain a list of country restrictions.

```json
{
  "object": "list",
  "data": [
    {
      "restrict_id": 2,
      "name": "openai",
      "countries": "{\"countries\":[{\"name\":\"Albania\",\"alpha-2\":\"AL\"},{\"name\":\"Algeria\",\"alpha-2\":\"DZ\"},{\"name\":\"Afghanistan\",\"alpha-2\":\"AF\"}]}"
    },
    {
      "restrict_id": 3,
      "name": "anthropic",
      "countries": "{\"countries\":[{\"name\":\"Germany\",\"alpha-2\":\"DE\"},{\"name\":\"France\",\"alpha-2\":\"FR\"},{\"name\":\"Spain\",\"alpha-2\":\"ES\"}]}"
    },
    {
      "...": "Additional restrictions not shown..."
    }
  ]
}
```

For more details on model availability, pricing, and capabilities, see the [APIpie Models documentation](https://apipie.ai/docs/Models/Overview).
