<div align="center">
<img src="https://apipie.ai/docs/img/Models/Grok.png" alt="Grok" width="100%" />
</div>

:::info
For detailed information about using models with APIpie, check out our [Models Overview](https://APIpie.ai/docs/Features/Models) and [Completions Guide](https://APIpie.ai/docs/Features/Completions).
:::

### **Description**

The [Grok Series](https://x.ai/) represents xAI's family of state-of-the-art large language models. These models, developed by [xAI](https://x.ai/), leverage cutting-edge technology to deliver exceptional performance in natural language processing, instruction-following tasks, and multimodal interactions. Grok is known for its real-time knowledge capabilities through [X platform integration](https://twitter.com/grok) and its unique personality that combines intelligence with wit. The models are available through [APIpie's routing system](https://APIpie.ai/docs/Features/Routing).

For technical details and performance metrics, see the [Grok technical report](https://x.ai/blog/grok-os).
#### **Key Features**

- **Extended Token Capacity:** Models support context lengths up to 131K tokens for handling extensive text processing needs.
- **Multimodal Capabilities:** Vision-enabled models for processing both text and images with state-of-the-art performance.
- **Real-time Knowledge:** Access to current information through X platform integration, setting it apart from other LLMs.
- **Provider Availability:** Accessible through [OpenRouter](https://openrouter.ai/).
- **Diverse Applications:** Optimized for chat, instruction-following, vision tasks, and real-time data analysis.
- **Unique Personality:** Combines factual responses with wit and humor, creating engaging interactions.

---

### **Model Comparison and Monitoring**

When choosing between Grok models, APIpie provides comprehensive monitoring tools to help make informed decisions:

**Performance Monitoring:**
- Real-time availability tracking through OpenRouter
- Latency metrics and historical performance data
- Response time comparisons between different model versions
- Specific performance tracking for vision-enabled models

**Pricing & Cost Analysis:**
- Live pricing updates through our [Models Route](https://APIpie.ai/docs/Features/Models) & [Dashboard](https://apipie.ai/dashboard) 
- Cost comparisons across different Grok versions
- Usage-based optimization recommendations
- Vision model cost tracking

**Health Metrics:**
- Global AI health dashboard for real-time status
- Provider reliability tracking
- Model uptime statistics
- Performance monitoring across different capabilities (text, vision)

This monitoring system helps users:
- Compare costs and pricing across different Grok models
- Track performance metrics to optimize response times
- Make data-driven decisions based on availability and reliability
- Monitor system health and anticipate potential issues
- Choose between standard and vision-enabled models based on needs

:::tip
Use the [Models Route](https://APIpie.ai/docs/Features/Models) to access real-time pricing and performance data for all Grok models.
:::

### **Model List in the Grok Series**

#### **Model List updates dynamically please see [the Models Route](https://APIpie.ai/docs/Features/Models#fetching-models) for the up to date list of models**

|                    |            |              |           |           |        |
| ------------------ | ---------- | ------------ | --------- | --------- | ------ |
| **Model Name**     | **Max Tokens** | **Response Tokens** | **Provider** | **Subtype** | **Type** |
| grok-beta         | 131,072    | 131,072      | openrouter | chatx     | llm    |
| grok-vision-beta  | 8,192      | 8,192        | openrouter | multimodal| vision |
| grok-2-1212       | 131,072    | 131,072      | openrouter | chatx     | llm    |
| grok-2-vision-1212| 32,768     | 32,768       | openrouter | multimodal| vision |

---

### Example API Call

Below is an example of how to use the [Chat Completions API](https://APIpie.ai/docs/Features/Completions) to interact with a model from the **Grok Series**, such as `grok-beta`.
```bash
curl -L -X POST 'https://apipie.ai/v1/chat/completions' \
-H 'Content-Type: application/json' \
-H 'Accept: application/json' \
-H 'Authorization: Bearer <YOUR_API_KEY>' \
--data-raw '{
  "provider": "openrouter",
  "model": "grok-beta",
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

The expected response structure for the Grok model might look like this:

```json
{
  "id": "chatcmpl-12345example12345",
  "object": "chat.completion",
  "created": 1729535643,
  "provider": "openrouter",
  "model": "grok-beta",
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

- **Provider:** Specify "openrouter" as the provider or leave blank for [automatic selection](https://APIpie.ai/docs/Features/Routing).
- **Model:** Use any model from the Grok Series, such as `grok-beta` or `grok-vision-beta`. See [Models Guide](https://APIpie.ai/docs/Features/Models#fetching-models).
- **Max Tokens:** Set the maximum response token count (e.g., 150 in this example).
- **Messages:** Format your request with a sequence of messages, including user input and system instructions. See [message formatting](https://APIpie.ai/docs/Features/Completions).

This example demonstrates how to seamlessly query models from the Grok Series for conversational or instructional tasks.

---

### **Applications and Integrations**

- **Conversational AI:** Powering chatbots, virtual assistants, and other dialogue-based systems. Try it with [LibreChat](https://APIpie.ai/docs/Integrations/LibreChat) or [OpenWebUI](https://APIpie.ai/docs/Integrations/OpenwebUI).
- **Vision Tasks:** Using vision-enabled models like `grok-vision-beta` and `grok-2-vision-1212` for image understanding and multimodal applications. Learn more about [vision capabilities](https://x.ai/blog/grok-1.5v).
- **Extended Context Tasks:** Processing long documents with models supporting up to 131K tokens. Learn more in our [Models Guide](https://APIpie.ai/docs/Features/Models).
- **Real-time Analysis:** Leveraging Grok's connection to the X platform for current events, trends, and social media analysis.
- **Research & Development:** Supporting academic and industrial research with reproducible results

---

### **Ethical Considerations**

The Grok models are powerful tools that should be used responsibly. Users should implement appropriate safeguards and consider potential biases in model outputs. For guidance on responsible AI usage, refer to [AI Safety Approach](https://www.safe.ai/) and [Ethical AI Guidelines](https://www.unesco.org/en/artificial-intelligence/recommendation-ethics). The development team maintains transparency through their open science initiative and regular safety assessments.


---

### **Licensing**
For detailed licensing information and usage terms, consult [xAI terms](https://x.ai/legal/terms-of-service).

:::tip
Try out the Grok models in APIpie's various [supported integrations.](https://APIpie.ai/docs/Sandbox/Chat)
:::
