
<div align="center">
    <img src="https://apipie.ai/docs/img/Features/completions-banner.png" alt="Chat Completions Feature Banner" width="100%" />
</div>

Leverage the flexibility and power of our Chat Completions endpoint to integrate conversational AI into your applications. Whether you're building customer support bots, generating creative content, or crafting interactive experiences, our chat completion API is designed to help you get the most from AI models while providing advanced features like [RAG integration](https://APIpie.ai/docs/Features/Ragtune), [model routing](https://APIpie.ai/docs/Features/Routing), and [response verification](https://APIpie.ai/docs/Features/Integrity).

## Chat Completions Overview

The Chat Completions API allows developers to interact with AI models in a conversational manner by sending a sequence of messages to the model and receiving a response. The structure of these messages is fully compliant with OpenAI's API structure, allowing seamless integration.

### OpenAI Compatible Framework

Our API is fully compatible with the [OpenAI Chat Completions API](https://platform.openai.com/docs/api-reference/chat), making migration seamless. Just change the URL and your API key, and your OpenAI-based application can start using APIpie immediately. Once integrated, you can take advantage of our additional features:

- [Automatic model routing](https://APIpie.ai/docs/Features/Routing) for optimal performance and cost
- [RAG integration](https://APIpie.ai/docs/Features/Ragtune) for enhanced knowledge retrieval
- [Response verification](https://APIpie.ai/docs/Features/Integrity) to reduce hallucinations
- [Usage tracking](https://APIpie.ai/docs/Features/Usage) with detailed metrics
- [Model pooling](https://APIpie.ai/docs/Features/Pools) for high availability

## How Chat Completions Work

A typical API call sends an array of messages to the chosen model, where each message consists of a role (either `system`, `user`, or `assistant`) and content. The model then processes the conversation and returns a response based on the provided context. 

:::note
- We use the chat completions route for all LLM interfaces (instruct, text, etc.). All models are accessible through this unified interface.
- For voice and image generation, see our dedicated [Images API](https://APIpie.ai/docs/Features/Images) & [Voices API](https://APIpie.ai/docs/Features/Voices) documentation.
:::

### Available Model Providers

Our API integrates with multiple leading AI providers, each offering unique capabilities:

- [OpenAI](https://APIpie.ai/docs/Models/OpenAI) - GPT-4, GPT-3.5 series
- [Anthropic](https://APIpie.ai/docs/Models/Claude) - Claude series
- [Meta](https://APIpie.ai/docs/Models/Llama) - Llama series
- [Cohere](https://APIpie.ai/docs/Models/Cohere) - Command series
- [AI21](https://APIpie.ai/docs/Models/ai21) - Jurassic series
- [Amazon](https://APIpie.ai/docs/Models/Amazon) - Bedrock models
- [Google](https://APIpie.ai/docs/Models/Google) - Gemini series

See our [Models Overview](https://APIpie.ai/docs/Features/Models) for a complete list of supported models and providers.

### Example API Call

Below is an example of how to use the Chat Completions API to generate a response:

```bash
curl -L -X POST 'https://apipie.ai/v1/chat/completions' \
-H 'Content-Type: application/json' \
-H 'Accept: application/json' \
-H 'Authorization: Bearer <YOUR_API_KEY>' \
--data-raw '{
  "provider": "openrouter",
  "model": "gpt-4o",
  "max_tokens": 100,
  "messages": [
    {
      "role": "user",
      "content": "Why is the sky blue?"
    }
  ]
}'
```

### Response Example

The expected response structure looks like the following:

```json
{
  "id": "chatcmpl-5fde5f7fffe8d6dc1f18aab4a138d4b7",
  "object": "chat.completion",
  "created": 1729535643,
  "provider": "openrouter",
  "model": "openai/gpt-4o",
  "choices": [
    {
      "index": 0,
      "message": {
        "role": "assistant",
        "content": "The sky appears blue primarily due to a phenomenon called Rayleigh scattering. Here's how it works:\n\n1. **Sunlight Composition**: Sunlight, or white light, is composed of many colors, each with different wavelengths. These colors can be seen in a rainbow or through a prism.\n\n2. **Atmospheric Interaction**: As sunlight reaches the Earth's atmosphere, it collides with molecules of gases and small particles.\n\n3. **Scattering and Wavelengths**: Different colors of light are"
      },
      "logprobs": null,
      "finish_reason": "stop"
    }
  ],
  "usage": {
    "prompt_tokens": 13,
    "completion_tokens": 100,
    "total_tokens": 113,
    "prompt_characters": 20,
    "response_characters": 474,
    "cost": 0.001878,
    "latency_ms": 2727
  },
  "system_fingerprint": "fp_f4d98523ab4ae852"
}
```

This structure provides the generated message, completion details, and detailed usage metrics for each request.

## Detailed Explanation of Parameters

### Required Parameters

- **messages** (array): A sequence of message objects in the conversation. Each message has:
  - **role** (string): The role of the message in the conversation. Possible values: `system`, `user`, `assistant`.
  - **content** (string): The content of the message.

### Message Roles

- **system**: This message type is used to guide the AI's behavior throughout the conversation. It sets the rules or parameters for how the AI should respond. For example, the system message might instruct the AI to speak in a specific language, adopt a particular tone, or adhere to certain boundaries in its replies. It's useful for defining the scope and role of the assistant, ensuring it stays within the desired context.
  
  **Example use case**: Defining the AI's behavior.
  
  ```json
  {
    "role": "system",
    "content": "You are a helpful assistant that speaks only in Swedish."
  }
  ```

- **user**: The user message represents the actual input or query from the person interacting with the AI. It's the prompt or question the user is submitting to the AI, and this message is crucial as it dictates what the AI will respond to. The content here is typically dynamic based on what the user is asking or requesting at any given moment.

  **Example use case**: The user's request to the AI.
  
  ```json
  {
    "role": "user",
    "content": "Why is the sky blue?"
  }
  ```

- **assistant**: This message type is the AI's response or any generated information that contributes to the conversation. It can be used for knowledge retrieval (such as in Retrieval-Augmented Generation, RAG) or historical memory when responding to ongoing conversations. The assistant message can be stored and used in context to improve the model’s ability to respond appropriately over a series of interactions.

  **Example use case**: AI's response or retrieved information.
  
  ```json
  {
    "role": "assistant",
    "content": "The sky is blue because of a phenomenon called Rayleigh scattering..."
  }
  ```

- **model** (string): Specifies the AI model to use. Normally a single base model name, you can provide up to 5 comma-separated models for multi-model queries which leverages our super query capabilities (Note: Some other features may not work with Super Query, such as pools for example)

### Optional Parameters

- **provider** (string): Optionally, specify the AI provider, or omit this field to let the system choose the best-performing one.
  
- **rag_tune** (string): Use this to specify a RAG tune or vector collection for augmenting language model queries with data from a specified vector database.

- **routing** (string): Defines how the call should be routed when multiple providers exist for a model. Options are:
  - `price`: Chooses the cheapest provider.
  - `perf`: Selects based on lowest latency for prompt size.
  - `perf_avg`: Chooses based on average latency.

### Memory Management Parameters

Our [Integrated Model Memory (IMM)](https://APIpie.ai/docs/Features/IMM) system provides advanced conversation context management that works across all supported models:

- **memory** (integer): Enable memory management by setting to 1
- **mem_session** (string): Unique identifier for separate conversation contexts
- **mem_expire** (integer): Set custom expiration time in minutes (max 1440, default 15)
- **mem_clear** (integer): Clear memory for a specific session when set to 1

Example API call with memory management:

```bash
curl -L -X POST 'https://apipie.ai/v1/chat/completions' \
-H 'Content-Type: application/json' \
-H 'Accept: application/json' \
-H 'Authorization: Bearer <YOUR_API_KEY>' \
--data-raw '{
  "memory": 1,
  "mem_session": "user123",
  "mem_expire": 60,
  "messages": [
    {
      "role": "user",
      "content": "Remember this: my favorite color is blue"
    }
  ]
}'
```

This enables persistent conversation context across different models within the same session, allowing you to maintain context even when switching between different AI providers.

### Generation Control Parameters (Grouped)

You can fine-tune the model's output by controlling randomness, creativity, and repetition through the following parameters:

- **temperature** (number): Controls randomness in the output. A lower value makes the model more deterministic, while a higher value increases randomness.
- **top_p** (number): Cumulative probability cutoff for token selection. A lower value keeps the output more deterministic, while a higher value increases creativity.
- **top_k** (integer): Limits the token selection to the top-k most likely tokens. A lower value makes the response more predictable.
- **frequency_penalty** (number): Penalizes tokens based on their frequency in the output, promoting diversity.
- **presence_penalty** (number): Penalizes tokens that have already appeared, encouraging new content.

Here’s a sample API call with these options:

```bash
curl -L -X POST 'https://apipie.ai/v1/chat/completions' \
-H 'Content-Type: application/json' \
-H 'Accept: application/json' \
-H 'Authorization: Bearer <YOUR_API_KEY>' \
--data-raw '{
  "provider": "openrouter",
  "model": "gpt-4o",
  "messages": [
    {
      "role": "user",
      "content": "Tell me a story about a talking cat."
    }
  ],
  "temperature": 0.7,
  "top_p": 0.9,
  "top_k": 50,
  "frequency_penalty": 0.2,
  "presence_penalty": 0.5
}'
```

### Beam Search Parameters
 Note: This is not available on all models, if the model you support does not support it, the parameter will be dropped.

- **beam_size** (integer): Determines the number of beams (sequences) to keep at each step during generation. This setting increases the probability of finding optimal sequences but requires more computational resources.

```bash
curl -L -X POST 'https://apipie.ai/v1/chat/completions' \
-H 'Content-Type: application/json' \
-H 'Accept: application/json' \
-H 'Authorization: Bearer <YOUR_API_KEY>' \
--data-raw '{
  "provider": "openrouter",
  "model": "llama-3.2-1b-instruct",
  "messages": [
    {
      "role": "user",
      "content": "What is the capital of France?"
    }
  ],
  "beam_size": 5
}'
```

### Other Parameters

- **n** (integer): Number of completions to generate for a single input.
- **max_tokens** (integer): The maximum number of tokens to generate for each completion.
- **stream** (boolean): If true, the API returns a stream of data chunks as the completion is generated, rather than waiting for the entire response.

```bash
curl -L -X POST 'https://apipie.ai/v1/chat/completions' \
-H 'Content-Type: application/json' \
-H 'Accept: application/json' \
-H 'Authorization: Bearer <YOUR_API_KEY>' \
--data-raw '{
  "provider": "openrouter",
  "model": "gpt-4o",
  "messages": [
    {
      "role": "user",
      "content": "How does streaming work in AI?"
    }
  ],
  "stream": true
}'
```

### Integrity and Verification

Our unique [integrity feature](https://APIpie.ai/docs/Features/Integrity) helps ensure response accuracy and reduce hallucinations:

- **integrity** (integer): Controls the verification process where the model evaluates its own response. Set to 12 or 13 for different verification levels.
- **integrity_model** (string): Optionally specify a different model for verification checks.

Learn more about response verification in our [Integrity Guide](https://APIpie.ai/docs/Features/Integrity).

```bash
curl -L -X POST 'https://apipie.ai/v1/chat/completions' \
-H 'Content-Type: application/json' \
-H 'Accept: application/json' \
-H 'Authorization: Bearer <YOUR_API_KEY>' \
--data-raw '{
  "provider": "openrouter",
  "model": "gpt-4o",
  "messages": [
    {
      "role": "user",
      "content": "Why is the sky blue?"
    }
  ],
  "integrity": 13,
  "integrity_model": "gpt-3.5-turbo"
}'
```

### Example of Streaming Response

```json
data: {"id":"chatcmpl-fc2e9121675cd68b07b6d1eb5e2b11e8","object":"chat.completion.chunk","created":1729535567,"provider":"openrouter","model":"openai/gpt-4o","choices":[{"index":0,"delta":{"role":"assistant","content":""},"logprobs":null,"finish_reason":null}],"system_fingerprint":"null"}

data: {"id":"chatcmpl-fc2e9121675cd68b07b6d1eb5e2b11e8","object":"chat.completion.chunk","created":1729535567,"provider":"openrouter","model":"openai/gpt-4o","choices":[{"index":1,"delta":{"content":"The"},"logprobs":null,"finish_reason":null}],"system_fingerprint":"null"}
...
data: {"id":"chatcmpl-fc2e9121675cd68b07b6d1eb5e2b11e8","object":"chat.completion.chunk","created":1729535567,"provider":"openrouter","model":"openai/gpt-4o","choices":[{"index":100,"delta":{"content":" sky"},"logprobs":null,"finish_reason":null}],"system_fingerprint":"null"}

data: {"id":"chatcmpl-fc2e9121675cd68b07b6d1eb5e2b11e8","object":"chat.completion.chunk","created":1729535567,"provider":"openrouter","model":"openai/gpt-4o","choices":[{"index":101,"delta":{"content":""},"logprobs":null,"finish_reason":null}],"system_fingerprint":"null"}

data: {"id":"chatcmpl-fc2e9121675cd68b07b6d1eb5e2b11e8","object":"chat.completion.chunk","created":1729535567,"provider":"openrouter","model":"openai/gpt-4o","choices":[{"index":102,"delta":{"content":""},"logprobs":null,"finish_reason":null}],"system_fingerprint":"null"}

data: {"id":"chatcmpl-fc2e9121675cd68b07b6d1eb5e2b11e8","object":"chat.completion.chunk","created":1729535567,"provider":"openrouter","model":"openai/gpt-4o","choices":[{"index":0,"delta":{"content":""},"logprobs":null,"finish_reason":"stop"}],"system_fingerprint":"null"}

data: {"id":"chatcmpl-fc2e9121675cd68b07b6d1eb5e2b11e8","object":"chat.completion.chunk","created":1729535567,"model":"openai/gpt-4o","system_fingerprint":"null","choices":[],"usage":{"prompt_tokens":13,"completion_tokens":100,"total_tokens":113,"prompt_characters":20,"response_characters":527,"cost":0.001878,"latency_ms":2831}}

data: [DONE]
```

---

## Usage Metrics in the Response

We provide comprehensive usage data with every request to help you track costs and performance. Metrics include:

- **prompt_tokens**: Number of tokens in the input prompt.
- **completion_tokens**: Number of tokens generated in the model’s response.
- **total_tokens**: Sum of `prompt_tokens` and `completion_tokens`.
- **prompt_characters**: Number of characters in the input prompt.
- **response_characters**: Number of characters in the model’s response.
- **cost**: The estimated cost of the request.
- **latency_ms**: Time taken for the model to generate a response.

### Example Response with Usage Metrics

```json
{
  "id": "chatcmpl-5fde5f7fffe8d6dc1f18aab4a138d4b7",
  "object": "chat.completion",
  "created": 1729535643,
  "provider": "openrouter",
  "model": "openai/gpt-4o",
  "choices": [
    {
      "index": 0,
      "message": {
        "role": "assistant",
        "content": "The sky appears blue primarily due to a phenomenon called Rayleigh scattering. Here's how it works..."
      },
      "logprobs": null,
      "finish_reason": "stop"
    }
  ],
  "usage": {
    "prompt_tokens": 13,
    "completion_tokens": 100,
    "total_tokens": 113,
    "prompt_characters": 20,
    "response_characters": 474,
    "cost": 0.001878,
    "latency_ms": 2727
  },
  "system_fingerprint": "fp_f4d98523ab4ae852"
}
```

**Note:** We are a leader in query usage reporting, offering extensive data tracking for every request. Additionally, historical billing data is available via API for audit purposes.

## Best Practices and Considerations

### Rate Limits and Quotas

Each provider has specific rate limits and quotas. For optimal performance:
- Use [model pools](https://APIpie.ai/docs/Features/Pools) for high-volume applications
- Implement proper error handling and retries
- Monitor your [usage](https://APIpie.ai/docs/Features/Usage) to stay within limits

### Model-Specific Considerations

Different models have varying capabilities and limitations:
- Check the [Models Overview](https://APIpie.ai/docs/Features/Models) for specific model capabilities
- Some models support longer context windows (up to 200K tokens)
- Consider these factors when choosing a model:
  - Input/output token limits
  - Response latency requirements
  - Cost per token
  - Specialized capabilities (code, math, analysis)
  - Production requirements (SLA, availability)
  - Regulatory and compliance needs

For detailed model comparisons and performance metrics, see our [Models Guide](https://APIpie.ai/docs/Features/Models).


### Error Handling

Common error scenarios and recommended handling:
```json
{
  "error": {
    "message": "Error description",
    "type": "invalid_request_error",
    "param": "messages",
    "code": "context_length_exceeded"
  }
}
```

- **context_length_exceeded**: Reduce input length or use a model with larger context window
- **rate_limit_exceeded**: Implement exponential backoff or use [model pools](https://APIpie.ai/docs/Features/Pools)
- **invalid_request_error**: Check request parameters against the API specification

### Security Best Practices

To ensure secure API usage:
- Rotate API keys regularly
- Use environment variables for key storage
- Implement proper input validation
- Consider using our [integrity checks](https://APIpie.ai/docs/Features/Integrity) for sensitive applications
