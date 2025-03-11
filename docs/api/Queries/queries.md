# Queries History

## Endpoint: GET /v1/queries/

[APIpie.ai](https://apipie.ai) provides this endpoint to fetch the history of queries sorted by Timestamp in Descending order.

For more information on usage tracking and analytics, visit the [APIpie documentation](https://apipie.ai/docs).

## Request

### Query Parameters

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| limit | integer | No | 50 | Limit number of returned queries per page |
| offset | integer | No | 0 | Offset used for pagination |

### Example Requests

- Get default queries (50 most recent): `https://api.apipie.ai/v1/queries/`
- Get 10 most recent queries: `https://api.apipie.ai/v1/queries/?limit=10`
- Get the second page of 20 queries: `https://api.apipie.ai/v1/queries/?limit=20&offset=20`

## Response

### 200 OK

| Property | Type | Description |
|----------|------|-------------|
| items | array | Array of query objects |
| limit | number | Limit parameter used in the request |
| offset | number | Offset parameter used in the request |

#### Query Object Properties

| Property | Type | Description |
|----------|------|-------------|
| id | number | Internal ID of the query |
| username | string | Name of the user that made the request |
| timestamp | string | Date and Time when the request was done in ISO format |
| app | string | Name of the API key |
| provider | string | AI Service Provider used |
| route | string | Unique identifier of the AI model used within the Provider |
| unit | string | Unit used for in cost calculations |
| prompt_tokens | number | Number of Tokens in the prompt |
| prompt_char | number | Number of Characters in the prompt |
| response_tokens | number | Number of Tokens in the response |
| response_char | number | Number of Characters in the response |
| cost | string | Cost of the query, decimal with up to 12 decimal places |
| latency_ms | number | Query latency in milliseconds |

### Example Response

```json
{
  "items": [
    {
      "id": 12345,
      "username": "user@example.com",
      "timestamp": "2023-09-15T14:32:17Z",
      "app": "My Application",
      "provider": "openai",
      "route": "gpt-3.5-turbo",
      "unit": "token",
      "prompt_tokens": 42,
      "prompt_char": 256,
      "response_tokens": 128,
      "response_char": 768,
      "cost": "0.000123456789",
      "latency_ms": 1250
    },
    {
      "id": 12344,
      "username": "user@example.com",
      "timestamp": "2023-09-15T14:30:05Z",
      "app": "My Application",
      "provider": "anthropic",
      "route": "claude-2",
      "unit": "token",
      "prompt_tokens": 35,
      "prompt_char": 210,
      "response_tokens": 95,
      "response_char": 570,
      "cost": "0.000234567890",
      "latency_ms": 1500
    }
  ],
  "limit": 50,
  "offset": 0
}
```

For more details on usage tracking and cost management, see the [APIpie Usage documentation](https://apipie.ai/docs/Features/Usage).
