<div align="center">
<img src="https://apipie.ai/docs/img/Models/Meta.png" alt="Meta Llama" width="100%" />
</div>

:::info
For detailed information about using models with APIpie, check out our [Models Overview](https://APIpie.ai/docs/Features/Models) and [Completions Guide](https://APIpie.ai/docs/Features/Completions).
:::

### **Model Comparison and Monitoring**

When choosing between Llama models, APIpie provides comprehensive monitoring tools to help make informed decisions:

**Performance Monitoring:**
- Real-time availability tracking across providers (OpenRouter, EdenAI, Together, Deepinfra, Monster, Bedrock)
- Latency metrics and historical performance data
- Response time comparisons between different model versions and families
- Specific performance tracking for specialized variants (Code Llama, Llama Guard)

**Pricing & Cost Analysis:**
- Live pricing updates through our [Models Route](https://APIpie.ai/docs/Features/Models) & [Dashboard](https://apipie.ai/dashboard) 
- Cost comparisons across different providers and model variants
- Usage-based optimization recommendations
- Provider-specific pricing tracking

**Health Metrics:**
- Global AI health dashboard for real-time status
- Provider reliability tracking
- Model uptime statistics
- Performance monitoring across different capabilities (text, code, vision, moderation)

This monitoring system helps users:
- Compare costs and pricing across different Llama models and providers
- Track performance metrics to optimize response times
- Make data-driven decisions based on availability and reliability
- Monitor system health and anticipate potential issues
- Choose optimal provider based on performance and cost needs

:::tip
Use the [Models Route](https://APIpie.ai/docs/Features/Models) to access real-time pricing and performance data for all Llama models.
:::

### **Description**

The [Llama Series](https://ai.meta.com/llama/) represents Meta's family of state-of-the-art large language models. These open-source models, developed by [Meta AI](https://ai.meta.com/), leverage cutting-edge technology to deliver exceptional performance in natural language processing, instruction-following tasks, and extended-context interactions. The models are available through various providers integrated with [APIpie's routing system](https://APIpie.ai/docs/Features/Routing).

#### **Key Features**

- **Extended Token Capacity:** Models support context lengths from 4K to 131K tokens for handling various text processing needs.
- **Multi-Provider Availability:** Accessible across platforms like [OpenRouter](https://openrouter.ai/), [EdenAI](https://www.edenai.co/), [Together](https://www.together.ai/), [Deepinfra](https://deepinfra.com/), [Monster](https://monsterapi.ai/), and [Amazon Bedrock](https://aws.amazon.com/bedrock/).
- **Diverse Applications:** Optimized for chat, instruction-following, code generation, vision, and moderation tasks.
- **Scalability:** Models ranging from efficient 1B parameter configurations to powerful 405B parameter versions.

---

### **Model List in the Llama Series**

#### **Model List updates dynamically please see [the Models Route](https://APIpie.ai/docs/Features/Models#fetching-models) for the up to date list of models**

:::info
For information about model performance and benchmarks, see the [Llama Technical Report](https://ai.meta.com/research/publications/llama-2-open-foundation-and-fine-tuned-chat-models/).
:::

|                                      |                |                     |                                       |                 |
| ------------------------------------ | -------------- | ------------------- | ------------------------------------- | --------------- |
| **Model Name**                       | **Max Tokens** | **Response Tokens** | **Provider**                          | **Type**        |
| nous-hermes-llama2-13b              | 4,096          | 4,096               | openrouter                            | llm             |
| llama-2-13b-chat                    | 4,096          | 4,096               | openrouter                            | llm             |
| llama2-13b-chat-v1                  | 4,096          | 3,996               | bedrock                               | llm             |
| llama2-70b-chat-v1                  | 4,096          | 3,996               | bedrock                               | llm             |
| Llama-2-70b-chat-hf                 | 4,096          | 4,096               | deepinfra                             | llm             |
| CodeLlama-70b-Instruct-hf           | 4,096          | 4,096               | deepinfra                             | code            |
| CodeLlama-34b-Instruct-hf           | 16,384         | 16,384              | deepinfra                             | code            |
| Phind-CodeLlama-34B-v2              | 16,384         | 16,384              | deepinfra                             | code            |
| Llama-2-7b-chat-hf                  | 4,096          | 4,096               | deepinfra                             | llm             |
| Llama-2-13b-chat-hf                 | 4,096          | 4,096               | deepinfra                             | llm             |
| Meta-Llama-3-70B-Instruct           | 8,192          | 8,192               | deepinfra                             | llm             |
| Meta-Llama-3-8B-Instruct            | 8,192          | 8,192               | deepinfra                             | llm             |
| llama-3-lumimaid-8b                 | 24,576         | 2,048               | openrouter                            | llm             |
| llama-guard-2-8b                    | 8,192          | 8,192               | openrouter                            | llm             |
| llama-3-lumimaid-70b                | 8,192          | 2,048               | openrouter                            | llm             |
| llama3-8b-instruct-v1               | 8,192          | 8,092               | bedrock                               | llm             |
| llama3-70b-instruct-v1              | 8,192          | 8,092               | bedrock                               | llm             |
| Meta-Llama-3-8B-Instruct            | 8,192          | 8,192               | monster                               | llm             |
| llama-3-8b-instruct                 | 8,192          | 8,192               | openrouter                            | llm             |
| llama-3-70b-instruct                | 8,192          | 8,192               | openrouter                            | llm             |
| llama-3.1-sonar-large-128k-online   | 127,072        | 127,072             | openrouter                            | llm             |
| llama-3.1-sonar-large-128k-chat     | 131,072        | 131,072             | openrouter                            | llm             |
| llama-3.1-sonar-small-128k-online   | 127,072        | 127,072             | openrouter                            | llm             |
| llama-3.1-sonar-small-128k-chat     | 131,072        | 131,072             | openrouter                            | llm             |
| llama-3.1-sonar-huge-128k-online    | 127,072        | 127,072             | openrouter                            | llm             |
| llama-3.1-lumimaid-8b               | 32,768         | 2,048               | openrouter                            | llm             |
| meta-llama-3.1-8b-instruct          | 8,192          | 8,192               | openrouter                            | llm             |
| llama-3.2-3b-instruct               | 131,000        | 131,000             | openrouter                            | llm             |
| llama-3.2-1b-instruct               | 131,072        | 131,072             | openrouter                            | llm             |
| llama-3.2-90b-vision-instruct       | 131,072        | 131,072             | openrouter                            | vision          |
| llama-3.2-11b-vision-instruct       | 131,072        | 4,096               | openrouter                            | vision          |
| llama-3.1-nemotron-70b-instruct     | 131,000        | 131,000             | openrouter                            | llm             |
| llama-3.1-lumimaid-70b              | 16,384         | 2,048               | openrouter                            | llm             |
| llama-3.3-70b-instruct              | 131,072        | 131,072             | openrouter                            | llm             |
| llama3-1-405b-instruct-v1:0         | -              | -                   | edenai                                | llm             |
| llama3-1-70b-instruct-v1:0          | -              | -                   | edenai                                | llm             |
| llama3-1-8b-instruct-v1:0           | -              | -                   | edenai                                | llm             |
| llama3-70b-instruct-v1:0            | -              | -                   | edenai                                | llm             |
| llama3-8b-instruct-v1:0             | -              | -                   | edenai                                | llm             |
| eva-llama-3.33-70b                  | 16,384         | 4,096               | openrouter                            | llm             |
| Llama-3.1-Nemotron-70B-Instruct-HF  | 32,768         | 32,768              | together                              | llm             |
| Llama-3.3-70B-Instruct-Turbo        | 131,072        | 131,072             | together                              | llm             |
| Llama-3.2-11B-Vision-Instruct-Turbo | 131,072        | 131,072             | together                              | llm             |
| Llama-3-8b-chat-hf                  | 8,192          | 8,192               | together                              | llm             |
| Llama-Guard-3-11B-Vision-Turbo      | 131,072        | 131,072             | together                              | moderation      |
| Llama-3-70b-chat-hf                 | 8,192          | 8,192               | together                              | llm             |
| Llama-3.2-3B-Instruct-Turbo         | 131,072        | 131,072             | together                              | llm             |
| Meta-Llama-3.1-405B-Instruct-Turbo  | 130,815        | 130,815             | together                              | llm             |
| scb10x-llama3-typhoon-v1-5x-4f316   | 8,192          | 8,192               | together                              | llm             |
| Meta-Llama-3.1-8B-Instruct-Turbo-128K | 131,072      | 131,072             | together                              | llm             |
| Meta-Llama-3.1-8B-Instruct-Turbo    | 131,072        | 131,072             | together                              | llm             |
| Llama-2-13b-chat-hf                 | 4,096          | 4,096               | together                              | llm             |
| Llama-3.2-90B-Vision-Instruct-Turbo | 131,072        | 131,072             | together                              | llm             |
| Meta-Llama-3.1-70B-Instruct-Turbo   | 131,072        | 131,072             | together                              | llm             |
| Meta-Llama-3-8B-Instruct-Turbo      | 8,192          | 8,192               | together                              | llm             |
| Meta-Llama-3-8B-Instruct-Lite       | 8,192          | 8,192               | together                              | llm             |
| scb10x-llama3-typhoon-v1-5-8b-instruct | 8,192       | 8,192               | together                              | llm             |
| Llama-2-70b-hf                      | 4,096          | 4,096               | together                              | llm             |
| LlamaGuard-2-8b                     | 8,192          | 8,192               | together                              | moderation      |
| Llama-Guard-7b                      | 4,096          | 4,096               | together                              | moderation      |
| Meta-Llama-3-70B-Instruct-Turbo     | 8,192          | 8,192               | together                              | llm             |
| Meta-Llama-3-70B-Instruct-Lite      | 8,192          | 8,192               | together                              | llm             |
| Llama-Rank-V1                       | 8,192          | 8,192               | together                              | llm             |
| Llama-2-7b-chat-hf                  | 4,096          | 4,096               | together                              | llm             |
| Meta-Llama-Guard-3-8B               | 8,192          | 8,192               | together                              | moderation      |
| llama3-1-8b-instruct-v1             | 128,000        | 128,000             | bedrock                               | llm             |
| llama3-1-70b-instruct-v1            | 128,000        | 128,000             | bedrock                               | llm             |
| llama3-2-11b-instruct-v1            | 128,000        | 128,000             | bedrock                               | llm             |
| llama3-2-90b-instruct-v1            | 128,000        | 128,000             | bedrock                               | llm             |
| llama3-2-1b-instruct-v1             | 128,000        | 128,000             | bedrock                               | llm             |
| llama3-2-3b-instruct-v1             | 8,192          | 8,092               | bedrock                               | llm             |
| llama3-3-70b-instruct-v1            | 8,192          | 8,092               | bedrock                               | llm             |

---

### Example API Call

Below is an example of how to use the [Chat Completions API](https://APIpie.ai/docs/Features/Completions) to interact with a model from the **Llama Series**, such as `llama-3-70b-instruct`.
```bash
curl -L -X POST 'https://apipie.ai/v1/chat/completions' \
-H 'Content-Type: application/json' \
-H 'Accept: application/json' \
-H 'Authorization: Bearer <YOUR_API_KEY>' \
--data-raw '{
  "provider": "openrouter",
  "model": "llama-3-70b-instruct",
  "max_tokens": 150,
  "messages": [
    {
      "role": "user",
      "content": "Can you explain how photosynthesis works?"
    }
  ]
}'
```

---

### Response Example

The expected response structure for the Llama model might look like this:

```json
{
  "id": "chatcmpl-12345example12345",
  "object": "chat.completion",
  "created": 1729535643,
  "provider": "openrouter",
  "model": "llama-3-70b-instruct",
  "choices": [
    {
      "index": 0,
      "message": {
        "role": "assistant",
        "content": "Photosynthesis is the process by which green plants, algae, and some bacteria convert light energy into chemical energy. Here's how it works:\n\n1. **Light Absorption**: Plants capture light energy using a pigment called chlorophyll, which is found in chloroplasts.\n\n2. **Water and Carbon Dioxide**: They absorb water through their roots and carbon dioxide from the air.\n\n3. **Glucose Production**: The light energy is used to convert water and carbon dioxide into glucose (a sugar) and oxygen. The equation is:\n   \n   6CO2 + 6H2O + light energy → C6H12O6 + 6O2\n\nThis process provides energy for the plant and releases oxygen into the atmosphere."
      },
      "logprobs": null,
      "finish_reason": "stop"
    }
  ],
  "usage": {
    "prompt_tokens": 15,
    "completion_tokens": 125,
    "total_tokens": 140,
    "prompt_characters": 45,
    "response_characters": 520,
    "cost": 0.002250,
    "latency_ms": 3100
  },
  "system_fingerprint": "fp_123abc456def"
}
```

---

### API Highlights

- **Provider:** Specify the provider or leave blank for [automatic selection](https://APIpie.ai/docs/Features/Routing).
- **Model:** Use any model from the Llama Series, such as `llama-3-70b-instruct` or others suited to your task. See [Models Guide](https://APIpie.ai/docs/Features/Models#fetching-models).
- **Max Tokens:** Set the maximum response token count (e.g., 150 in this example).
- **Messages:** Format your request with a sequence of messages, including user input and system instructions. See [message formatting](https://APIpie.ai/docs/Features/Completions).

This example demonstrates how to seamlessly query models from the Llama Series for conversational or instructional tasks.

---

### **Applications and Integrations**

- **Conversational AI:** Powering chatbots, virtual assistants, and other dialogue-based systems. Try it with [LibreChat](https://APIpie.ai/docs/Integrations/LibreChat) or [OpenWebUI](https://APIpie.ai/docs/Integrations/OpenwebUI).
- **Code Generation:** Using [CodeLlama](https://ai.meta.com/blog/code-llama-large-language-model-coding/) variants for programming tasks, code completion, and technical documentation.
- **Content Moderation:** Leveraging [LlamaGuard](https://ai.meta.com/research/publications/llama-guard-llm-based-input-output-safeguard-for-human-ai-conversations/) models for content filtering and safety checks.
- **Vision Tasks:** Using vision-enabled models for image understanding and multimodal applications.
- **Extended Context Tasks:** Processing long documents with models supporting up to 131K tokens. Learn more in our [Models Guide](https://APIpie.ai/docs/Features/Models).

---

### **Ethical Considerations**

The Llama models are powerful tools that should be used responsibly. Users should implement appropriate safeguards and consider potential biases in model outputs. For guidance on responsible AI usage, see Meta's [AI Responsibility Guidelines.](https://ai.meta.com/llama/responsible-use-guide/)

---

### **Licensing**

The Llama Series is available under [Meta's community license agreement](https://github.com/facebookresearch/llama/blob/main/LICENSE), which allows for both research and commercial use under specific terms. For detailed licensing information, consult the [official Llama repository](https://github.com/facebookresearch/llama), [model cards](https://huggingface.co/meta-llama), and respective hosting providers.

:::tip
Try out the Llama models in APIpie's various [supported integrations.](https://APIpie.ai/docs/Sandbox/Chat)
:::
