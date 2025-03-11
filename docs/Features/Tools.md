
<div align="center">
    <img src="https://apipie.ai/docs/img/Features/tools-banner.png" alt="Tools Support Feature Banner" width="100%" />
</div>

Explore the flexibility and power of our Tools Support feature, enabling seamless integration with both OpenAI and Anthropic models to handle a wide array of tool-based queries. This feature enhances AI capabilities, giving businesses the freedom to choose how tool requests are processed.

## Why Use Tools Support?

Tools Support allows you to configure which model responds to your tool queries. You can select any model from either OpenAI or Anthropic to handle tool-based requests, ensuring you get the most effective response depending on your specific use case. The feature supports all models available on our platform and provides the flexibility to customize how your tool queries are handled.

## Understanding Tools Configuration

### ToolsModel Selection

- **Default Model**: If no specific tools model is selected, the default `gpt-4o-mini` is used. This model is optimized for efficiency and accuracy, offering reliable tool responses at a lower cost.
- **Custom Model**: You can select any OpenAI or Anthropic model to handle tool calls. This is useful when you want to leverage specific model strengths for particular tools, such as weather updates or information retrieval.

When using a different model for tools, we first send your request to the tools model with minimal `max_tokens`. If the response includes a tool call, we process it and return the tool's response. If no tool is called, we send the request to your chosen model to continue processing.

### Tools Query Process

If your tool and query models are the same, the entire process happens within a single query. If the tool model is different, your request is divided into two phases:
- **Phase 1**: A query is sent to the tools model to check for any tool invocations.
- **Phase 2**: If the tool model doesn't return a tool response, the request is forwarded to your chosen model for standard processing.

In cases where tools are invoked, you only pay for the tool query cost and the final model response. We optimize token usage by minimizing token consumption for tool checks.

### Example API Call Using Tools

Here’s how you can integrate tools in an API call:

```bash
curl -L -X POST 'https://apipie.ai/v1/chat/completions' \
-H 'Content-Type: application/json' \
-H 'Accept: application/json' \
-H 'Authorization: Bearer <TOKEN>' \
--data-raw '{
  "messages": [
    {
      "role": "user",
      "content": "what is the weather in dallas and what are some fun facts about Dallas?"
    }
  ],
  "model": "gpt-4o",
  "provider": "openrouter",
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
              "description": "City and state for the weather report, e.g., Dallas, TX"
            },
            "unit": {
              "type": "string",
              "enum": ["celsius", "fahrenheit"]
            }
          },
          "required": ["location", "unit"]
        }
      }
    },
    {
      "type": "function",
      "function": {
        "name": "fun_city_facts",
        "description": "Get interesting facts about a city",
        "parameters": {
          "type": "object",
          "properties": {
            "location": {
              "type": "string",
              "description": "City to learn fun facts about, e.g., Dallas, TX"
            }
          },
          "required": ["location"]
        }
      }
    }
  ],
  "tool_choice": "auto",
  "tools_model": "gpt-4o-mini"
}'
```

### Example Response:

```json
{
  "id": "chatcmpl-8de1a7f199e44f616238f6f6dbf7dcf9",
  "object": "chat.completion",
  "created": 1729442924,
  "model": "gpt-4o",
  "choices": [
    {
      "index": 0,
      "message": {
        "role": "assistant",
        "content": "Please bear with me for a moment while I gather the current weather information and some fun facts about Dallas for you.",
        "tool_calls": [
          {
            "id": "call_vEOdJs1QG6zqvzVjYqA1Dl3h",
            "type": "function",
            "function": {
              "name": "get_current_weather",
              "arguments": "{\"location\": \"Dallas, TX\", \"unit\": \"fahrenheit\"}"
            }
          },
          {
            "id": "call_gGlaXomXwVpThaH2ol6CqmfB",
            "type": "function",
            "function": {
              "name": "fun_city_facts",
              "arguments": "{\"location\": \"Dallas, TX\"}"
            }
          }
        ]
      },
      "logprobs": null,
      "finish_reason": "tool_calls"
    }
  ],
  "usage": {
    "prompt_tokens": 159,
    "completion_tokens": 80,
    "total_tokens": 239,
    "prompt_characters": 194,
    "response_characters": 310,
    "cost": "0.00199500",
    "latency_ms": 1791
  },
  "system_fingerprint": "fp_d1ab9353"
}
```

This API request demonstrates how to specify tool invocations in your query, and the response shows how tools are invoked and handled by the system.

## Benefits of Tools Support for Businesses

The Tools Support feature provides unmatched flexibility and accuracy for handling tool-based queries. By allowing different models for tools, businesses can optimize costs and performance for specific use cases, such as:
- Real-time data retrieval, like weather reports or fact-checking.
- Dynamic integration of functions for improved user experiences.
- Reduced overhead by utilizing the most cost-effective models for non-critical queries.

**Note:** If the model designated for tools does not return a tool response, additional API charges apply for forwarding the query to the user's primary model.

## Setting Up Tools Support

To effectively use Tools Support in your AI workflows, follow these steps:

1. **Choose Your Tools Model:**
   - Set the `tools_model` parameter to any supported OpenAI or Anthropic model based on your needs.
   - Use the default `gpt-4o-mini` for cost-effective and reliable responses.

2. **Configure Tool Query Settings:**  
   - Ensure your API request includes the appropriate tool-related parameters and functions.

3. **Monitor and Optimize:**  
   - Track the performance of tool queries to assess their impact on response times and costs.

## Tips & Tricks

- **Leverage Tools for Dynamic Data**: Use tools for real-time data retrieval, like weather and factual data.
- **Customize Your Tools Model**: Adjust the tools model to match the complexity of your queries.
- **Optimize Token Usage**: Keep `max_tokens` low for tool queries to reduce costs.

## FAQs

1. **What is the default tools model?**
   - The default tools model is `gpt-4o-mini`, which balances accuracy and cost-effectiveness.

2. **Can I use Anthropic models for tools queries?**
   - Yes, both OpenAI and Anthropic models are supported for tool queries.

3. **What happens if the tools model doesn't return a tool response?**
   - The query is sent to your primary model for standard processing, incurring an additional charge.

4. **Is there any delay when using tools?**
   - There may be a slight delay when streaming tool responses due to the additional data processing.


## Links

- [Chat Completions API](https://apipie.ai/docs/api/chatcompletions)
- [Fetch Models API](https://apipie.ai/docs/api/fetchmodels)

## Conclusion

With Tools Support, you're equipped to make the most of AI's ability to integrate external functions seamlessly. By customizing the model that handles tool queries, you can enhance your AI's capabilities while maintaining control over costs and performance.
