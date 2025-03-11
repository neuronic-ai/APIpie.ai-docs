<div align="center">
<img src="https://apipie.ai/docs/img/Models/AWS.png" alt="Amazon Bedrock" width="100%" />
</div>

:::info
For detailed information about using models with APIpie, check out our [Models Overview](https://APIpie.ai/docs/Features/Models) and [Completions Guide](https://APIpie.ai/docs/Features/Completions).
:::

### **Description**

[Amazon's Titan and Nova models](https://aws.amazon.com/ai/generative-ai/nova/) represent AWS's proprietary family of foundation models, available through [Amazon Bedrock](https://aws.amazon.com/bedrock/) - AWS's unified AI model platform. These models are designed to handle a variety of tasks including text generation, image generation, and embeddings, offering enterprise-grade reliability and performance through [APIpie's routing system](https://APIpie.ai/docs/Features/Routing).

### **Amazon Bedrock as a Provider**

While this guide focuses on Amazon's own Titan and Nova models, Amazon Bedrock serves as a comprehensive AI model platform hosting both Amazon's proprietary models and those from other leading providers. Through APIpie's unified API, you can seamlessly access:

- Amazon's proprietary models (Titan, Nova)
- Third-party provider models hosted on Bedrock
- Comprehensive monitoring and cost tracking
- Automatic model routing and fallback

APIpie simplifies Bedrock integration by providing:
- Single API endpoint for all Bedrock models
- Unified pricing and performance monitoring
- Automated provider selection and failover
- Consistent response format across all models

For a complete list of available models and providers, see our [Models Route](https://APIpie.ai/docs/Features/Models).

#### **Model Families**

**Titan Models:**
- **Text Series:** Ranging from lite to premier versions, optimized for different performance and resource needs
- **Embedding Models:** Specialized for text and image embeddings, ideal for search and recommendation systems
- **Image Generation:** Advanced models for creating and manipulating images

**Nova Models:**
- **Text Processing:** Specialized in handling extremely long contexts up to 300K tokens
- **Performance Tiers:** From micro to pro versions, balancing efficiency and capability
- **Specialized Variants:** Canvas and Reel versions for specific use cases

#### **Key Features**

- **Extended Token Capacity:** Models support context lengths from 4K to 300K tokens for various processing needs.
- **Diverse Capabilities:** Text generation, image generation, and embedding models available.
- **Enterprise Focus:** Built for production-grade applications with AWS's reliability.
- **Optimized Performance:** Models ranging from lightweight to high-performance versions.

---

### **Model Comparison and Monitoring**

When choosing between Titan and Nova models, APIpie provides comprehensive monitoring tools to help make informed decisions:

**Performance Monitoring:**
- Real-time availability tracking across providers (Bedrock, OpenRouter)
- Latency metrics and historical performance data
- Response time comparisons between different model versions

**Pricing & Cost Analysis:**
- Live pricing updates through our [Models Route](https://APIpie.ai/docs/Features/Models) & [Dashboard](https://apipie.ai/dashboard) 
- Cost comparisons and pricing trends across different providers

**Health Metrics:**
- Global AI health dashboard for real-time status
- Provider reliability tracking
- Model uptime statistics

This monitoring system helps users:
- Compare costs and pricing across different Titan and Nova models
- Track performance metrics to optimize response times
- Make data-driven decisions based on availability and reliability
- Monitor system health and anticipate potential issues

:::tip
Use the [Models Route](https://APIpie.ai/docs/Features/Models) to access real-time pricing and performance data for all Amazon models.
:::

### **Model Feature Comparison**

When choosing between Titan and Nova models, consider these key differences:

**Titan Models:**
- Best for: General-purpose text generation, image tasks, and embeddings
- Strengths: 
  - More versatile with text, image, and embedding capabilities
  - Lower latency for standard tasks
  - Optimized for production workloads
- Use when:
  - You need image generation or embedding capabilities
  - Working with standard context lengths
  - Requiring fast response times

**Nova Models:**
- Best for: Long-form content and complex document processing
- Strengths:
  - Much larger context windows (up to 300K tokens)
  - Specialized for long-form content
  - Advanced text processing capabilities
- Use when:
  - Processing very long documents
  - Needing extensive context for responses
  - Working with complex, multi-part texts

---

### **Model List**

#### **Amazon's Titan & Nova Models**

While Amazon Bedrock hosts various provider models, this section focuses on Amazon's own Titan and Nova series. For a complete list of all available models through Bedrock and other providers, see our [Models Route](https://APIpie.ai/docs/Features/Models).

:::info
For detailed information about model capabilities and performance, visit the [Amazon Titan Documentation](https://docs.aws.amazon.com/bedrock/latest/userguide/titan.html).
:::

|                                      |                |                     |                                       |                 |
| ------------------------------------ | -------------- | ------------------- | ------------------------------------- | --------------- |
| **Model Name**                       | **Max Tokens** | **Response Tokens** | **Providers**                         | **Type**        |
| titan-tg1-large                     | 32,000         | 32,000              | Bedrock                               | LLM             |
| titan-text-lite-v1                  | 4,000          | 4,000               | Bedrock                               | LLM             |
| titan-text-express-v1               | 8,000          | 8,000               | Bedrock                               | LLM             |
| titan-text-premier-v1               | 32,000         | 32,000              | Bedrock                               | LLM             |
| olympus-premier-v1                  | -              | -                   | Bedrock                               | LLM             |
| titan-embed-g1-text-02             | 8,192          | 8,192               | Bedrock                               | Embedding       |
| titan-embed-text-v1                 | 8,192          | 8,192               | Bedrock                               | Embedding       |
| titan-embed-text-v2                 | -              | -                   | Bedrock                               | Embedding       |
| titan-image-generator-v1            | -              | -                   | Bedrock                               | Image           |
| titan-image-generator-v2            | -              | -                   | Bedrock                               | Image           |
| titan-embed-image-v1                | -              | -                   | Bedrock                               | Image           |
| nova-pro-v1                         | 300,000        | 5,120               | Bedrock, OpenRouter                   | LLM             |
| nova-lite-v1                        | 300,000        | 5,120               | Bedrock, OpenRouter                   | LLM             |
| nova-micro-v1                       | 128,000        | 5,120               | Bedrock, OpenRouter                   | LLM             |
| nova-canvas-v1                      | -              | -                   | Bedrock                               | LLM             |
| nova-reel-v1                        | -              | -                   | Bedrock                               | LLM             |

---

### Example API Call

Below is an example of how to use the [Chat Completions API](https://APIpie.ai/docs/Features/Completions) to interact with a Titan model.
```bash
curl -L -X POST 'https://apipie.ai/v1/chat/completions' \
-H 'Content-Type: application/json' \
-H 'Accept: application/json' \
-H 'Authorization: Bearer <YOUR_API_KEY>' \
--data-raw '{
  "provider": "bedrock",
  "model": "titan-text-premier-v1",
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

The expected response structure for a Titan model might look like this:

```json
{
  "id": "chatcmpl-12345example12345",
  "object": "chat.completion",
  "created": 1729535643,
  "provider": "bedrock",
  "model": "titan-text-premier-v1",
  "choices": [
    {
      "index": 0,
      "message": {
        "role": "assistant",
        "content": "Photosynthesis is the process by which plants convert sunlight into chemical energy. Here's how it works:\n\n1. **Light Absorption**: Plants capture sunlight using chlorophyll in their leaves\n\n2. **Water and CO2**: They take in water through roots and carbon dioxide through leaf pores\n\n3. **Chemical Reaction**: Using sunlight's energy, they convert H2O and CO2 into glucose and oxygen:\n   6CO2 + 6H2O + light → C6H12O6 + 6O2\n\nThis process produces food for the plant and releases oxygen as a byproduct."
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

- **Provider:** Specify "bedrock" as the provider or leave blank for [automatic selection](https://APIpie.ai/docs/Features/Routing).
- **Model Selection:**
  - Use Titan models for general text generation and embeddings
  - Use Nova models for extended context processing
  - See [Models Guide](https://APIpie.ai/docs/Features/Models#fetching-models) for the complete list
- **Max Tokens:** Set according to model capacity (varies by model)
- **Messages:** Format your request following the [message formatting guide](https://APIpie.ai/docs/Features/Completions)

---

### **Applications and Integrations**

**Titan Applications:**
- **Text Generation:** 
  - Content creation and chat applications
  - Premier variant (32K context) for complex tasks
  - Express variant (8K context) for balanced performance
  - Lite variant (4K context) for efficient processing
- **Image Generation:** 
  - Creating and editing images
  - Visual content generation
  - Image manipulation and enhancement
- **Embeddings:** 
  - Semantic search implementation
  - Document similarity analysis
  - Content recommendation systems
  - Cross-modal applications with image embeddings

**Nova Applications:**
- **Extended Context Processing:**
  - Document analysis up to 300K tokens
  - Long-form content generation
  - Complex document summarization
- **Specialized Processing:**
  - Canvas variant for visual-heavy content
  - Reel variant for sequential content
  - Micro variant for efficient processing of medium-length content (128K tokens)

**Integration Options:**
- Try the models with [LibreChat](https://APIpie.ai/docs/Integrations/LibreChat) or [OpenWebUI](https://APIpie.ai/docs/Integrations/OpenwebUI)

---

### **Ethical Considerations**

Amazon's models are designed with responsible AI principles. Users should implement appropriate safeguards and consider potential biases. For guidance, see AWS's [Responsible AI Guidelines](https://aws.amazon.com/machine-learning/responsible-ai/).

---

### **Licensing**

Titan and Nova models are available through AWS Bedrock. Usage is subject to [AWS Service Terms](https://aws.amazon.com/service-terms/). For detailed information, consult the [Amazon Bedrock documentation](https://docs.aws.amazon.com/bedrock/).

:::tip
Try out the Titan and Nova models in APIpie's various [supported integrations.](https://APIpie.ai/docs/Sandbox/Chat)
:::
