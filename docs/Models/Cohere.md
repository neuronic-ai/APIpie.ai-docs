<div align="center">
<img src="https://apipie.ai/docs/img/Models/Cohere.png" alt="Cohere" width="100%" />
</div>

:::info
For detailed information about using models with APIpie, check out our [Models Overview](https://APIpie.ai/docs/Features/Models) and [Completions Guide](https://APIpie.ai/docs/Features/Completions).
:::

### **Description**

[Cohere](https://cohere.com/) is a leading provider of enterprise-grade language AI models. Their [Command series](https://docs.cohere.com/docs/command) represents state-of-the-art models optimized for production environments, offering exceptional performance in natural language understanding, generation, and task completion. These models are available through various providers integrated with [APIpie's routing system](https://APIpie.ai/docs/Features/Routing).

#### **Key Features**

- **Extended Token Capacity:** Models support context lengths from 4K to 128K tokens, with [Command-R models](https://docs.cohere.com/docs/command-r) optimized for processing long documents.
- **Multi-Provider Availability:** Accessible through [Amazon Bedrock](https://aws.amazon.com/bedrock), [OpenRouter](https://openrouter.ai/), [EdenAI](https://www.edenai.co).
- **Diverse Applications:** Optimized for chat, [instruction-following](https://docs.cohere.com/docs/prompt-engineering), and [text generation](https://docs.cohere.com/docs/text-generation) tasks.
- **Enterprise Focus:** Models designed for production-ready deployment with consistent performance and [enterprise-grade security](https://cohere.com/security).
- **Advanced Capabilities:** Features include [semantic search](https://docs.cohere.com/docs/semantic-search), text classification, and content moderation.

---

### **Model Comparison and Monitoring**

When choosing between Cohere models, APIpie provides comprehensive monitoring tools to help make informed decisions:

**Performance Monitoring:**
- Real-time availability tracking across providers (Bedrock, OpenRouter, EdenAI)
- Latency metrics and historical performance data
- Response time comparisons between different model versions

**Pricing & Cost Analysis:**
- Live pricing updates through our [Models Route](https://APIpie.ai/docs/Features/Models) & [Dashboard](https://apipie.ai/dashboard) 
- Cost comparisons and pricing trends across different providers
- Usage-based cost optimization recommendations

**Health Metrics:**
- Global AI health dashboard for real-time status
- Provider reliability tracking
- Model uptime statistics

This monitoring system helps users:
- Compare costs and pricing across different Cohere models and providers
- Track performance metrics to optimize response times
- Make data-driven decisions based on availability and reliability
- Monitor system health and anticipate potential issues

:::tip
Use the [Models Route](https://APIpie.ai/docs/Features/Models) to access real-time pricing and performance data for all Cohere models.
:::

### **Model List in the Cohere Series**

#### **Model List updates dynamically please see [the Models Route](https://APIpie.ai/docs/Features/Models#fetching-models) for the up to date list of models**

:::info
For detailed performance metrics and benchmarks, see the [Cohere Model Performance](https://artificialanalysis.ai/providers/cohere) documentation and [Command Model Cards](https://docs.cohere.com/v2/docs/models).
:::

#### Language Models (LLMs)

|                          |                |                     |                                |              |
| ------------------------ | -------------- | ------------------- | ------------------------------ | ------------ |
| **Model Name**           | **Max Tokens** | **Response Tokens** | **Providers**                  | **Subtype**  |
| command                  | 4,096          | 4,000               | OpenRouter, EdenAI             | Chat         |
| command-text-v14         | 4,000          | 4,000               | Bedrock                        | Chat         |
| command-light-text-v14   | 4,000          | 4,000               | Bedrock                        | Chat         |
| command-r-v1             | 128,000        | 4,000               | Bedrock                        | Chat         |
| command-r-plus-v1        | 128,000        | 4,000               | Bedrock                        | Chat         |
| command-r                | 128,000        | 4,000               | OpenRouter, EdenAI             | Chat         |
| command-r-plus           | 128,000        | 4,000               | OpenRouter, EdenAI             | Chat         |
| command-r-08-2024        | 128,000        | 4,000               | OpenRouter                     | Chat         |
| command-r-plus-08-2024   | 128,000        | 4,000               | OpenRouter                     | Chat         |
| command-r-plus-04-2024   | 128,000        | 4,000               | OpenRouter                     | Chat         |
| command-r-03-2024        | 128,000        | 4,000               | OpenRouter                     | Chat         |
| command-r7b-12-2024      | 128,000        | 4,000               | OpenRouter                     | Chat         |
| command-light           | 4,096          | 4,000               | EdenAI                         | Chat         |
| command-light-nightly   | 4,096          | 4,000               | EdenAI                         | Chat         |
| command-nightly         | 4,096          | 4,000               | EdenAI                         | Chat         |

#### Embedding Models

|                               |            |                |                 |              |
| ----------------------------- | ---------- | -------------- | --------------- | ------------ |
| **Model Name**                | **Dimensions** | **Provider**  | **Language**    | **Type**     |
| embed-english-v3              | 512        | Bedrock        | English         | Embedding    |
| embed-multilingual-v3         | 512        | Bedrock        | Multilingual    | Embedding    |
| embed-english-v3.0            | -          | EdenAI         | English         | Embedding    |
| embed-english-light-v3.0      | -          | EdenAI         | English         | Embedding    |
| embed-multilingual-v3.0       | -          | EdenAI         | Multilingual    | Embedding    |
| embed-english-v2.0            | -          | EdenAI         | English         | Embedding    |
| embed-english-light-v2.0      | -          | EdenAI         | English         | Embedding    |
| embed-multilingual-v2.0       | -          | EdenAI         | Multilingual    | Embedding    |
| 4096embed-english-v2.0        | 4,096      | EdenAI         | English         | Embedding    |
| 1024embed-english-light-v2.0  | 1,024      | EdenAI         | English         | Embedding    |
| 768__embed-multilingual-v2.0  | 768        | EdenAI         | Multilingual    | Embedding    |
| 4096__embed-english-v2.0      | 4,096      | EdenAI         | English         | Embedding    |
| 1024__embed-english-light-v2.0| 1,024      | EdenAI         | English         | Embedding    |

---

### Example API Call

Below is an example of how to use the [Chat Completions API](https://APIpie.ai/docs/Features/Completions) to interact with a model from the **Cohere Series**, such as `command`.
```bash
curl -L -X POST 'https://apipie.ai/v1/chat/completions' \
-H 'Content-Type: application/json' \
-H 'Accept: application/json' \
-H 'Authorization: Bearer <YOUR_API_KEY>' \
--data-raw '{
  "provider": "cohere",
  "model": "command",
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

The expected response structure for the Cohere model might look like this:

```json
{
  "id": "chatcmpl-12345example12345",
  "object": "chat.completion",
  "created": 1729535643,
  "provider": "cohere",
  "model": "command",
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
- **Model:** Use any model from the Cohere Series, such as `command` or others suited to your task. See [Models Guide](https://APIpie.ai/docs/Features/Models#fetching-models).
- **Max Tokens:** Set the maximum response token count (e.g., 150 in this example).
- **Messages:** Format your request with a sequence of messages, including user input and system instructions. See [message formatting](https://APIpie.ai/docs/Features/Completions).

This example demonstrates how to seamlessly query models from the Cohere Series for conversational or instructional tasks.

---

### **Applications and Integrations**

- **Conversational AI:** Powering chatbots, virtual assistants, and other dialogue-based systems. Try it with [LibreChat](https://APIpie.ai/docs/Integrations/LibreChat) or [OpenWebUI](https://APIpie.ai/docs/Integrations/OpenwebUI).
- **Enterprise Solutions:** Leveraging Cohere's models for business applications and customer service automation.
- **Content Generation:** Creating high-quality text content using [Cohere's generation capabilities](https://docs.cohere.com/docs/text-generation).
- **Extended Context Tasks:** Processing long documents with models supporting up to 128K tokens. Learn more in our [Models Guide](https://APIpie.ai/docs/Features/Models).
- **Multilingual Support:** Handling text processing tasks across [multiple languages](https://docs.cohere.com/docs/multilingual-language-models) effectively.
- **RAG Applications:** Building powerful [retrieval-augmented generation systems](https://docs.cohere.com/docs/retrieval-augmented-generation-rag) with Cohere's models.

---

### **Ethical Considerations**

Cohere models are designed with responsible AI practices in mind. Users should implement appropriate safeguards and consider potential biases in model outputs. For guidance on responsible AI usage, see Cohere's [Responsible AI Guidelines](https://cohere.com/blog/the-enterprise-guide-to-ai-safety).

---

### **Licensing**

Cohere models are available through their [commercial licensing terms](https://cohere.com/terms-of-use). For detailed licensing information and usage terms, consult the [official Cohere documentation](https://docs.cohere.com/) and respective hosting providers.

:::tip
Try out the Cohere models in APIpie's various [supported integrations.](https://APIpie.ai/docs/Sandbox/Chat)
:::
