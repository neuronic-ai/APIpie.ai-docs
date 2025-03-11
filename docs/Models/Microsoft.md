<div align="center">
<img src="https://apipie.ai/docs/img/Models/Microsoft.png" alt="Microsoft AI" width="100%" />
</div>

:::info
For detailed information about using models with APIpie, check out our [Models Overview](https://APIpie.ai/docs/Features/Models) and [Completions Guide](https://APIpie.ai/docs/Features/Completions).
:::

### **Model Comparison and Monitoring**

When choosing between Microsoft models, APIpie provides comprehensive monitoring tools to help make informed decisions:

**Performance Monitoring:**
- Real-time availability tracking across providers (OpenRouter, Monster API, Together)
- Latency metrics and historical performance data
- Response time comparisons between different model versions
- Specific performance tracking for Phi and WizardLM variants

**Pricing & Cost Analysis:**
- Live pricing updates through our [Models Route](https://APIpie.ai/docs/Features/Models) & [Dashboard](https://apipie.ai/dashboard) 
- Cost comparisons across different providers and model variants
- Usage-based optimization recommendations
- Provider-specific pricing tracking

**Health Metrics:**
- Global AI health dashboard for real-time status
- Provider reliability tracking
- Model uptime statistics
- Performance monitoring across different capabilities

This monitoring system helps users:
- Compare costs and pricing across different Microsoft models and providers
- Track performance metrics to optimize response times
- Make data-driven decisions based on availability and reliability
- Monitor system health and anticipate potential issues
- Choose optimal provider based on performance and cost needs

:::tip
Use the [Models Route](https://APIpie.ai/docs/Features/Models) to access real-time pricing and performance data for all Microsoft models.
:::

### **Description**

The [Microsoft Phi Series](https://www.microsoft.com/en-us/research/blog/phi-2-the-surprising-power-of-small-language-models/) represents Microsoft's innovative approach to efficient and powerful language models. Developed by [Microsoft Research](https://www.microsoft.com/en-us/research/), these models demonstrate exceptional performance through advanced scaling techniques and architectural improvements. The models are available through various providers integrated with [APIpie's routing system](https://APIpie.ai/docs/Features/Routing), offering flexibility in deployment options.

#### **Key Features**

- **Advanced Architecture:** Models leverage [Microsoft's scaling techniques](https://www.microsoft.com/en-us/research/blog/phi-2-the-surprising-power-of-small-language-models/) for optimal performance with smaller parameter counts
- **Extended Context Windows:** Support for context lengths from 2K to 128K tokens, with the latest Phi-3 series offering enhanced long-context understanding
- **Multi-Provider Availability:** Accessible through platforms like [OpenRouter](https://openrouter.ai/) and [Monster API](https://monsterapi.ai/)
- **Diverse Applications:** Optimized for chat, instruction-following, and complex reasoning tasks with state-of-the-art performance
- **Resource Efficiency:** Industry-leading performance-to-size ratio, making them ideal for cost-effective deployments
- **Research-Backed Development:** Built on Microsoft's extensive [research in efficient ML](https://www.microsoft.com/en-us/research/focus-area/ai-and-microsoft-research/) and model scaling

---

### **Model List in the Microsoft Series**

#### **Model List updates dynamically please see [the Models Route](https://APIpie.ai/docs/Features/Models#fetching-models) for the up to date list of models**

:::info
For detailed performance analysis and benchmarks, see the [Microsoft Phi-2 Technical Report](https://arxiv.org/abs/2311.16716) and [Phi-2 Research Updates](https://www.microsoft.com/en-us/research/blog/phi-2-the-surprising-power-of-small-language-models/).
:::

|                                   |                |                     |                    |                 |
| --------------------------------- | -------------- | ------------------- | ------------------ | --------------- |
| **Model Name**                    | **Max Tokens** | **Response Tokens** | **Providers**      | **Subtype**     |
| resnet-50                        | -              | -                   | deepinfra          | image-classification |
| beit-base-patch16-224-pt22k-ft22k | -              | -                   | deepinfra          | image-classification |
| wizardlm-2-8x22b                 | 65536          | 4096                | openrouter         | chatx|text-generation |
| WizardLM-2-7B                    | 32000          | 32000               | deepinfra          | chatx|text-generation |
| WizardLM-2-8x22B                 | 65536          | 65536               | deepinfra          | chatx|text-generation |
| wizardlm-2-7b                    | 32000          | 4096                | openrouter         | text-generation|chatx |
| phi-3-mini-128k-instruct         | 128000         | 128000              | openrouter         | chatx            |
| phi-3-medium-128k-instruct       | 128000         | 128000              | openrouter         | chatx            |
| phi-3.5-mini-128k-instruct       | 128000         | 128000              | openrouter         | chatx            |
| nova-micro-v1                    | 128000         | 5120                | bedrock            |                 |
| nova-micro-v1                    | 128000         | 5120                | openrouter         | chat             |
| WizardLM-2-8x22B                 | 65536          | 65536               | together           | chat             |

---

### Example API Call

Below is an example of how to use the [Chat Completions API](https://APIpie.ai/docs/Features/Completions) to interact with a model from the **Microsoft Series**, such as `phi-3-medium-128k-instruct`.
```bash
curl -L -X POST 'https://apipie.ai/v1/chat/completions' \
-H 'Content-Type: application/json' \
-H 'Accept: application/json' \
-H 'Authorization: Bearer <YOUR_API_KEY>' \
--data-raw '{
  "provider": "openrouter",
  "model": "phi-3-medium-128k-instruct",
  "max_tokens": 150,
  "messages": [
    {
      "role": "user",
      "content": "What are the key principles of machine learning?"
    }
  ]
}'
```

---

### Response Example

The expected response structure for the Microsoft model might look like this:

```json
{
  "id": "chatcmpl-12345example12345",
  "object": "chat.completion",
  "created": 1729535643,
  "provider": "openrouter",
  "model": "phi-3-medium-128k-instruct",
  "choices": [
    {
      "index": 0,
      "message": {
        "role": "assistant",
        "content": "The key principles of machine learning include:\n\n1. **Data Quality**: High-quality, diverse training data is essential\n\n2. **Feature Selection**: Identifying relevant input variables\n\n3. **Model Selection**: Choosing appropriate algorithms for the task\n\n4. **Training & Validation**: Using separate datasets to ensure generalization\n\n5. **Evaluation**: Measuring performance with appropriate metrics\n\nThese principles form the foundation of effective machine learning systems."
      },
      "logprobs": null,
      "finish_reason": "stop"
    }
  ],
  "usage": {
    "prompt_tokens": 12,
    "completion_tokens": 98,
    "total_tokens": 110,
    "prompt_characters": 45,
    "response_characters": 420,
    "cost": 0.001850,
    "latency_ms": 2800
  },
  "system_fingerprint": "fp_123abc456def"
}
```

---

### API Highlights

- **Provider:** Specify the provider or leave blank for [automatic selection](https://APIpie.ai/docs/Features/Routing).
- **Model:** Use any model from the Microsoft Series, such as `phi-3-medium-128k-instruct` or others suited to your task. See [Models Guide](https://APIpie.ai/docs/Features/Models#fetching-models).
- **Max Tokens:** Set the maximum response token count (e.g., 150 in this example).
- **Messages:** Format your request with a sequence of messages, including user input and system instructions. See [message formatting](https://APIpie.ai/docs/Features/Completions).

This example demonstrates how to seamlessly query models from the Microsoft Series for conversational or instructional tasks.

---

### **Applications and Integrations**

- **Efficient AI Solutions:** Ideal for applications requiring high performance with resource constraints, leveraging Microsoft's optimized architecture
- **Research and Education:** Perfect for academic and research applications, with comprehensive documentation and research papers.
- **Extended Context Processing:** Latest models support up to 128K tokens for advanced document analysis and long-form content understanding
- **Enterprise Applications:** Production-ready for business applications with Microsoft's enterprise-grade reliability
- **Development and Testing:** Excellent for rapid prototyping and development with fast inference times and consistent outputs
- **Natural Language Processing:** State-of-the-art performance in text understanding, generation, and analysis tasks

---

### **Ethical Considerations**

Microsoft's AI models should be used responsibly with appropriate safeguards and consideration of potential biases. For guidance on responsible AI usage, see Microsoft's [Responsible AI Standards](https://www.microsoft.com/en-us/ai/responsible-ai).

---

### **Licensing**

The Microsoft Phi Series models are available under specific terms and conditions. For detailed licensing information, consult the [Microsoft Research Open Source](https://opensource.microsoft.com/) documentation.

:::tip
Try out the Microsoft models in APIpie's various [supported integrations.](https://APIpie.ai/docs/Sandbox/Chat)
:::
