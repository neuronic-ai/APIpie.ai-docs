# Embeddings LLM

## Endpoint: POST /v1/embeddings

[APIpie.ai](https://apipie.ai) allows you to generate embeddings for the given input text using the specified model.

The `model` field in the request body specifies the model to use. Check the [/models route](https://apipie.ai/docs/api/models) for complete list of embedding models. You can specify the encoding format (`float` or `np`) and the dimensions (up to 1536) of the output embedding vector.

For more information, visit the [APIpie API documentation](https://apipie.ai/docs).

## Request

### Body Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| model | string | Yes | Model to use for generating embeddings |
| input | string | Yes | Input text to generate embeddings for |
| encoding_format | string | No | Format of the output encoding (float, np). Only supported by OpenAI |
| dimensions | integer | No | Number of dimensions for the embedding vector (max 1536). Only supported by OpenAI |

### Example Request

```json
{
  "model": "text-embedding-3-small",
  "input": "why is the sky blue?",
  "encoding_format": "float",
  "dimensions": 1024
}
```

## Response

### 200 OK

| Property | Type | Description |
|----------|------|-------------|
| object | string | Type of the returned object, usually "list" |
| data | array | Array containing the embedding data |
| provider | string | Provider of the AI service |
| model | string | Model used for generating embeddings |
| usage | object | Usage statistics for the request |

For more details on embedding models and their capabilities, see the [APIpie documentation](https://apipie.ai/docs).

### Example Response

```json
{
  "object": "list",
  "data": [
    {
      "object": "embedding",
      "index": 0,
      "embedding": [
        0.015207428,
        -0.0031979256,
        -0.042056903,
        0.03562467,
        0.022221763,
        -0.0012624348,
        0.013301042,
        ...
      ]
    }
  ],
  "provider": "openai",
  "model": "text-embedding-3-small",
  "usage": {
    "prompt_tokens": 6,
    "total_tokens": 6,
    "prompt_characters": 20,
    "cost": "0.0000001260",
    "latency_ms": 349
  }
}
