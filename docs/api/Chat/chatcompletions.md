# Chat Completions

## Endpoint: POST /v1/chat/completions

[APIpie.ai](https://apipie.ai) provides this endpoint to query LLMs using text and, for vision-capable models, image data. This endpoint supports multiple models (up to 5, comma-separated) in the model field. Specify the appropriate request format depending on whether the model is text-based or vision-capable.

An array of responses will be returned for multi-model queries.

Please refer to the [APIpie API documentation](https://apipie.ai/docs) for more details on ChatCompletionRequest for text-based models and VisionChatCompletionRequest for vision-capable models.

## Request

### Body Parameters for ChatCompletionRequest

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| messages | array | Yes | Array of message objects with role and content |
| model | string | Yes | Language Model to use, comma separated, up to 5 models |
| provider | string | No | AI Service Provider to use |
| memory | boolean | No | Enable Integrated Model Memory to maintain conversation context |
| mem_session | string | No | Unique identifier for maintaining separate memory chains |
| mem_expire | integer | No | Time in minutes after which stored memories will expire |
| mem_clear | integer | No | Set to 1 to instantly delete all stored memories for the specified mem_session |
| mem_msgs | integer | No | Maximum number of messages to append from memory (default: 8) |
| mem_length | integer | No | Percentage (1-100) of model's max response tokens to use for memory |
| rag_tune | string | No | Name of the rag tune or vector collection to be used for RAG tuning |
| routing | string | No | Define how to route your call (price, multi-tiered performance, average_latency) |
| temperature | number | No | Influences the randomness in token selection (0-2) |
| top_p | number | No | Controls the cumulative probability distribution cutoff (0-1) |
| top_k | integer | No | Limits the selection pool to the top k most probable tokens |
| frequency_penalty | number | No | Adjusts token selection based on previous occurrences (-2 to 2) |
| presence_penalty | number | No | Decreases likelihood of tokens appearing again (-2 to 2) |
| repetition_penalty | number | No | Discourages repeating words or phrases (1-2) |
| n | integer | No | Number of responses to generate (1-5) |
| beam_size | integer | No | Number of sequences to keep at each generation step (1-5) |
| max_tokens | integer | No | Max tokens used to generate a response |
| stream | boolean | No | Return response in event-stream |
| tools | array | No | Optional tools/functions for the model to use |
| tool_choice | string | No | Specifies how tools are chosen ("none", "auto", "required") |
| tools_model | string | No | Model to use for processing tools (default: gpt-4o-mini) |
| integrity | integer | No | Integrity setting (12 or 13) for best of 2 or 3 answers |
| integrity_model | string | No | Model to use for integrity checks (default: gpt-4o) |
| force_provider | boolean | No | Force request to be routed to the specified provider |

### Example Messages Format

```json
[
  {"role": "system", "content": "Respond in Swedish."},
  {"role": "assistant", "content": "additional data to help the system answer the users prompt"},
  {"role": "user", "content": "Why the sky is blue?"}
]
```

### Example Chat Request

```json
{
  "messages": [
    {"role": "user", "content": "Why the sky is blue?"}
  ],
  "model": "gpt-3.5-turbo",
  "memory": 1,
  "mem_session": "test3746"
}
```

### Body Parameters for VisionChatCompletionRequest

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| model | string | Yes | Vision Model to use |
| messages | array | Yes | Array of message objects with role and content |
| max_tokens | integer | No | Max tokens used to generate a response |

### Example Vision Request

```json
{
  "messages": [
    {
      "role": "user",
      "content": [
        {"type": "text", "text": "describe this person"},
        {
          "type": "image_url",
          "image_url": {
            "url": "https://apipie.ai/temp/dlcpieh28hy8vnf.jpg",
            "detail": "high"
          }
        }
      ]
    }
  ],
  "model": "gpt-4-vision-preview"
}
```

### Example Tools Request

```json
{
  "model": "claude-3.5-sonnet",
  "messages": [
    {"role": "user", "content": "What is the current weather in Dallas, TX?"}
  ],
  "tools": [
    {
      "type": "function",
      "function": {
        "name": "get_current_weather",
        "description": "Get the current weather in a given location",
        "parameters": {
          "type": "object",
          "properties": {
            "location": {
              "type": "string",
              "description": "The city and state, e.g., San Francisco, CA"
            },
            "unit": {
              "type": "string",
              "enum": ["celsius", "fahrenheit"]
            }
          },
          "required": ["location"]
        }
      }
    }
  ],
  "tool_choice": "auto"
}
```

## Response

### 200 OK

| Property | Type | Description |
|----------|------|-------------|
| id | string | Unique identifier for the completion |
| object | string | Type of the returned object, usually "chat.completion" |
| created | integer | UTC timestamp of when the completion was created |
| provider | string | Provider of the AI service |
| model | string | AI model used for generating the completion |
| choices | array | Array of possible completion options generated by the model |
| usage | object | Usage statistics for the request |
| system_fingerprint | string | Unique fingerprint of the system configuration used |

For more information on response formats and error handling, visit the [APIpie API documentation](https://apipie.ai/docs).

### Example Response

```json
{
  "id": "chatcmpl-123abc",
  "object": "chat.completion",
  "created": 1677858242,
  "provider": "openai",
  "model": "gpt-3.5-turbo",
  "choices": [
    {
      "index": 0,
      "message": {
        "role": "assistant",
        "content": "The sky appears blue because of a phenomenon called Rayleigh scattering..."
      },
      "logprobs": null,
      "finish_reason": "stop"
    }
  ],
  "usage": {
    "prompt_tokens": 13,
    "completion_tokens": 42,
    "total_tokens": 55,
    "prompt_characters": 78,
    "response_characters": 256,
    "cost": 0.00012,
    "latency_ms": 1250
  },
  "system_fingerprint": "fp_12345"
}
