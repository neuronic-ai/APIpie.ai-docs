<div align="center">
<img src="https://apipie.ai/docs/img/Models/Perplexity.png" alt="Perplexity" width="100%" />
</div>
:::info
For detailed information about using models with APIpie, check out our [Models Overview](https://APIpie.ai/docs/Features/Models) and [Completions Guide](https://APIpie.ai/docs/Features/Completions).
:::

### **Model Comparison and Monitoring**

When choosing between Perplexity models, APIpie provides comprehensive monitoring tools to help make informed decisions:

**Performance Monitoring:**
- Real-time availability tracking across providers (OpenRouter)
- Latency metrics and historical performance data
- Response time comparisons between different model sizes
- Specific performance tracking for online inference capabilities

**Pricing & Cost Analysis:**
- Live pricing updates through our [Models Route](https://APIpie.ai/docs/Features/Models) & [Dashboard](https://apipie.ai/dashboard) 
- Cost comparisons across different Sonar variants
- Usage-based optimization recommendations
- Real-time inference cost tracking

**Health Metrics:**
- Global AI health dashboard for real-time status
- Provider reliability tracking
- Model uptime statistics
- Performance monitoring across different model sizes (small, large, huge)

This monitoring system helps users:
- Compare costs and pricing across different Perplexity models
- Track performance metrics to optimize response times
- Make data-driven decisions based on availability and reliability
- Monitor system health and anticipate potential issues
- Choose optimal model size based on performance and cost needs

:::tip
Use the [Models Route](https://APIpie.ai/docs/Features/Models) to access real-time pricing and performance data for all Perplexity models.
:::

### **Description**

[Perplexity AI](https://docs.perplexity.ai/guides/model-cards) is pioneering the development of advanced language models with a focus on real-time information processing and extended context understanding. Building upon Meta's [Llama architecture](https://ai.meta.com/llama/), Perplexity has enhanced these foundation models with specialized training and optimizations for online inference. Their Sonar models represent a significant breakthrough, combining Llama's powerful language understanding capabilities with real-time information processing and extended context windows.

This innovative approach leverages Llama's strong foundation while adding crucial features for real-world applications:
- **Online Inference Optimization:** Enhanced the base Llama architecture for real-time processing
- **Extended Context Understanding:** Improved context window handling up to 128K tokens
- **Knowledge Integration:** Added capabilities for real-time information access and processing

These models are available through [APIpie's routing system](https://APIpie.ai/docs/Features/Routing), offering state-of-the-art performance for various applications.

#### **Key Features**

- **Extended Context Processing:** Supports up to 128K tokens context length for comprehensive document analysis and long-form conversations
- **Online Inference:** Designed for real-time information processing and up-to-date knowledge
- **Scalable Architecture:** Available in multiple sizes (small, large, huge) to suit different computational needs
- **High Performance:** Optimized for both speed and accuracy in natural language understanding tasks
- **Knowledge Integration:** Enhanced with real-time information access capabilities
- **Adaptive Learning:** Continuously updated to maintain current knowledge and capabilities

---

### **Available Models**

#### **Model List updates dynamically please see [the Models Route](https://APIpie.ai/docs/Features/Models#fetching-models) for the up to date list of models**

:::info
Perplexity offers various models optimized for different use cases. The following models represent their Sonar series, which excels at real-time information processing with extended context windows. For detailed information about model capabilities and use cases, visit the [Perplexity Blog](https://blog.perplexity.ai/).
:::

|                                    |                |                     |                    |              |
| ---------------------------------- | -------------- | ------------------- | ------------------ | ------------ |
| **Model Name**                     | **Max Tokens** | **Response Tokens** | **Providers**      | **Subtype**  |
| llama-3.1-sonar-small-128k-online | 127,072        | 127,072            | OpenRouter         | Chat         |
| llama-3.1-sonar-large-128k-online | 127,072        | 127,072            | OpenRouter         | Chat         |
| llama-3.1-sonar-huge-128k-online  | 127,072        | 127,072            | OpenRouter         | Chat         |

---

### Example API Call

Below is an example of how to use the [Chat Completions API](https://APIpie.ai/docs/Features/Completions) to interact with a Perplexity model:
```bash
curl -L -X POST 'https://apipie.ai/v1/chat/completions' \
-H 'Content-Type: application/json' \
-H 'Accept: application/json' \
-H 'Authorization: Bearer <YOUR_API_KEY>' \
--data-raw '{
  "provider": "openrouter",
  "model": "llama-3.1-sonar-huge-128k-online",
  "max_tokens": 150,
  "messages": [
    {
      "role": "user",
      "content": "What are the latest developments in quantum computing?"
    }
  ]
}'
```

---

### Response Example

The expected response structure for a Perplexity model:

```json
{
  "id": "chatcmpl-12345example12345",
  "object": "chat.completion",
  "created": 1729535643,
  "provider": "openrouter",
  "model": "llama-3.1-sonar-huge-128k-online",
  "choices": [
    {
      "index": 0,
      "message": {
        "role": "assistant",
        "content": "Recent developments in quantum computing include advances in error correction, new qubit architectures, and breakthrough experiments in quantum supremacy. Companies like IBM, Google, and others continue to make progress in both hardware and software aspects of quantum computing technology."
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

- **Provider:** Specify a provider or leave blank for [automatic selection](https://APIpie.ai/docs/Features/Routing)
- **Model:** Choose from available Perplexity models based on your needs. See [Models Guide](https://APIpie.ai/docs/Features/Models#fetching-models)
- **Max Tokens:** Leverage the extended context window of up to 127K tokens
- **Messages:** Format your request with user inputs and system instructions. See [message formatting](https://APIpie.ai/docs/Features/Completions)

---

### **Applications and Use Cases**

- **Real-time Information Processing:** Ideal for applications requiring current information and knowledge
- **Long-form Content Analysis:** Perfect for processing and analyzing lengthy documents, research papers, or conversations
- **Knowledge-intensive Tasks:** Excellent for research, analysis, and complex problem-solving requiring deep understanding
- **Enterprise Solutions:** Suitable for business applications requiring processing of large documents and real-time information
- **Educational Applications:** Valuable for in-depth learning and research assistance
- **Research and Development:** Powerful tools for scientific research and technological innovation
- **Content Generation:** Advanced capabilities for creating high-quality, well-researched content

Try these models with [LibreChat](https://APIpie.ai/docs/Integrations/LibreChat) or [OpenWebUI](https://APIpie.ai/docs/Integrations/OpenwebUI) for an interactive experience.

---

### **Best Practices**

- Utilize the extended context window effectively by providing comprehensive context when needed
- Consider the model size based on your specific use case - smaller models for faster responses, larger models for more complex tasks
- Implement appropriate error handling and retry mechanisms for optimal performance
- Follow [Perplexity's usage guidelines](https://www.perplexity.ai/hub/getting-started) for best results
- Leverage the real-time information processing capabilities for up-to-date responses
- Structure prompts to take advantage of the models' knowledge integration features

---

### **Resources and Documentation**

- [Perplexity AI Documentation](https://docs.perplexity.ai/)
- [APIpie Models Guide](https://APIpie.ai/docs/Features/Models)
- [Perplexity Research Blog](https://blog.perplexity.ai/)
- [Model Performance Benchmarks](https://blog.perplexity.ai/blog/introducing-pplx-online-llms)

:::tip
Experience the power of Perplexity models in APIpie's various [supported integrations](https://APIpie.ai/docs/Sandbox/Chat).
:::
