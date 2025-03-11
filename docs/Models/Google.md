<div align="center">
<img src="https://apipie.ai/docs/img/Models/Gemini.png" alt="Google Gemini" width="100%" />
</div>

:::info
For detailed information about using models with APIpie, check out our [Models Overview](https://APIpie.ai/docs/Features/Models) and [Completions Guide](https://APIpie.ai/docs/Features/Completions).
:::

### **Description**

[Google's AI models](https://ai.google/get-started/our-models/), including the [Gemini Series](https://blog.google/technology/ai/google-gemini-ai/) and [Gemma Series](https://ai.google.dev/gemma/), represent cutting-edge advancements in artificial intelligence. Developed by [Google DeepMind](https://deepmind.google/), these models leverage state-of-the-art technology to deliver exceptional performance across various AI tasks. The models are available through multiple providers integrated with [APIpie's routing system](https://APIpie.ai/docs/Features/Routing).

The [Gemini Series](https://deepmind.google/technologies/gemini/) represents Google's most advanced AI models, capable of sophisticated reasoning across text, code, images, and video. Meanwhile, the [Gemma Series](https://ai.google.dev/gemma) offers efficient, open-source models built on the same research and technology as Gemini. These models are accessible through [Google Cloud's Vertex AI platform](https://cloud.google.com/vertex-ai/docs/generative-ai/learn/models) and various third-party providers.

#### **Key Features**

- **Advanced Token Processing:** Models support context lengths from 4K to 2M tokens for comprehensive text processing, with [optimized performance](https://cloud.google.com/vertex-ai/docs/generative-ai/learn/models#context_window) across different scales.
- **Multi-Provider Access:** Available through platforms like [Google Cloud](https://cloud.google.com/vertex-ai), [OpenRouter](https://openrouter.ai/), [EdenAI](https://www.edenai.co/), and more, with [enterprise-grade security](https://cloud.google.com/security/products).
- **Versatile Applications:** Optimized for chat, instruction-following, code generation, and [multimodal tasks](https://deepmind.google/technologies/gemini/#capabilities), with state-of-the-art performance across domains.


---

### **Model Comparison and Monitoring**

When choosing between Google's models, APIpie provides comprehensive monitoring tools to help make informed decisions:

**Performance Monitoring:**
- Real-time availability tracking across providers (Together, Deepinfra, OpenRouter, EdenAI)
- Latency metrics and historical performance data
- Response time comparisons between different model versions and families
- Specific performance tracking for Gemini and Gemma variants

**Pricing & Cost Analysis:**
- Live pricing updates through our [Models Route](https://APIpie.ai/docs/Features/Models) & [Dashboard](https://apipie.ai/dashboard) 
- Cost comparisons across different providers and model types
- Usage-based optimization recommendations
- Separate tracking for proprietary and open-source model costs

**Health Metrics:**
- Global AI health dashboard for real-time status
- Provider reliability tracking
- Model uptime statistics
- Performance monitoring across different model capabilities (text, code, vision)

This monitoring system helps users:
- Compare costs and pricing across different Google models and providers
- Track performance metrics to optimize response times
- Make data-driven decisions based on availability and reliability
- Monitor system health and anticipate potential issues
- Choose between proprietary and open-source options based on needs

:::tip
Use the [Models Route](https://APIpie.ai/docs/Features/Models) to access real-time pricing and performance data for all Google models.
:::


### **Model List in the Google Series**

#### **Model List updates dynamically please see [the Models Route](https://APIpie.ai/docs/Features/Models#fetching-models) for the up to date list of models**

:::info
For information about model performance and benchmarks, see the [Gemini Technical Report](https://storage.googleapis.com/deepmind-media/gemini/gemini_1_report.pdf) and [Gemma Technical Report](https://storage.googleapis.com/deepmind-media/gemma/gemma-report.pdf).
:::

|                                |                |                     |                                |                 |
| ------------------------------ | -------------- | ------------------- | ------------------------------ | --------------- |
| **Model Name**                 | **Max Tokens** | **Response Tokens** | **Providers**                  | **Subtype**     |
| gemini-pro-1.5                | 2,000,000      | 8,192              | OpenRouter                     | Text            |
| gemini-flash-1.5              | 1,000,000      | 8,192              | OpenRouter                     | Chat            |
| gemini-flash-1.5-8b           | 1,000,000      | 8,192              | OpenRouter                     | Chat            |
| gemini-pro                    | 91,728         | 22,937             | EdenAI                         | Chat            |
| palm-2-codechat-bison-32k     | 91,750         | 22,937             | OpenRouter                     | Code            |
| palm-2-chat-bison-32k         | 32,768         | 8,192              | OpenRouter                     | Chat            |
| gemini-pro                    | 32,760         | 8,192              | OpenRouter                     | Text            |
| palm-2-codechat-bison         | 20,070         | 2,867              | OpenRouter                     | Code            |
| palm-2-chat-bison             | 9,216          | 1,024              | OpenRouter                     | Chat            |
| gemma-7b-it                   | 8,192          | 8,192              | Deepinfra                      | Chat            |
| gemma-2-27b-it                | 8,192          | 8,192              | Together                       | Chat            |
| gemma-2b-it                   | 8,192          | 8,192              | Together                       | Chat            |
| gemma-2-27b-it                | 8,192          | 4,096              | OpenRouter                     | Text            |
| gemma-2-9b-it                 | 4,096          | 4,096              | OpenRouter, Monster, Together  | Chat            |
| gemini-pro-vision             | 16,384         | 2,048              | OpenRouter, EdenAI             | Vision          |
| gemini-1.5-flash              | -              | -                   | EdenAI                         | Chat            |
| gemini-1.5-pro                | -              | -                   | EdenAI                         | Chat            |
| gemini-1.5-flash-latest       | -              | -                   | EdenAI                         | Chat            |
| gemini-1.5-pro-exp-0801       | -              | -                   | EdenAI                         | Chat            |
| gemini-1.5-pro-exp-0827       | -              | -                   | EdenAI                         | Chat            |
| gemini-1.5-pro-latest         | -              | -                   | EdenAI                         | Chat            |
| gemini-1.5-flash-8b           | -              | -                   | EdenAI                         | Chat            |
| chat-bison                    | -              | -                   | EdenAI                         | Chat            |
| gemma-1.1-7b-it               | -              | -                   | Deepinfra                      | Chat            |
| vit-base-patch16-224          | -              | -                   | Deepinfra                      | Image           |
| vit-base-patch16-384          | -              | -                   | Deepinfra                      | Image           |
| textembedding-gecko           | 768            | -                   | EdenAI                         | Embedding       |

---

### Example API Call

Below is an example of how to use the [Chat Completions API](https://APIpie.ai/docs/Features/Completions) to interact with a model from the **Google Series**, such as `gemini-pro-1.5`.
```bash
curl -L -X POST 'https://apipie.ai/v1/chat/completions' \
-H 'Content-Type: application/json' \
-H 'Accept: application/json' \
-H 'Authorization: Bearer <YOUR_API_KEY>' \
--data-raw '{
  "provider": "openrouter",
  "model": "gemini-pro-1.5",
  "max_tokens": 150,
  "messages": [
    {
      "role": "user",
      "content": "What are the key differences between machine learning and deep learning?"
    }
  ]
}'
```

---

### Response Example

The expected response structure for a Google model might look like this:

```json
{
  "id": "chatcmpl-12345example12345",
  "object": "chat.completion",
  "created": 1729535643,
  "provider": "openrouter",
  "model": "gemini-pro-1.5",
  "choices": [
    {
      "index": 0,
      "message": {
        "role": "assistant",
        "content": "Machine learning and deep learning differ in several key aspects:\n\n1. **Complexity**: Machine learning uses simpler algorithms for pattern recognition, while deep learning uses complex neural networks with multiple layers.\n\n2. **Data Requirements**: Machine learning can work with smaller datasets, but deep learning typically needs vast amounts of data to be effective.\n\n3. **Feature Extraction**: Machine learning often requires manual feature engineering, while deep learning automatically learns and extracts relevant features.\n\n4. **Hardware Requirements**: Machine learning algorithms can run on standard computers, but deep learning usually needs powerful GPUs for efficient processing.\n\n5. **Applications**: Machine learning is suited for structured data analysis, while deep learning excels in complex tasks like image recognition and natural language processing."
      },
      "logprobs": null,
      "finish_reason": "stop"
    }
  ],
  "usage": {
    "prompt_tokens": 18,
    "completion_tokens": 132,
    "total_tokens": 150,
    "prompt_characters": 72,
    "response_characters": 548,
    "cost": 0.003000,
    "latency_ms": 2800
  },
  "system_fingerprint": "fp_123abc456def"
}
```

---

### API Highlights

- **Provider:** Specify the provider or leave blank for [automatic selection](https://APIpie.ai/docs/Features/Routing).
- **Model:** Use any model from the Google Series, such as `gemini-pro-1.5` or others suited to your task. See [Models Guide](https://APIpie.ai/docs/Features/Models#fetching-models).
- **Max Tokens:** Set the maximum response token count (e.g., 150 in this example).
- **Messages:** Format your request with a sequence of messages, including user input and system instructions. See [message formatting](https://APIpie.ai/docs/Features/Completions).

This example demonstrates how to seamlessly query models from the Google Series for conversational or instructional tasks.

---

### **Applications and Integrations**

- **Enterprise Solutions:** Powering business applications with [Google Cloud's Vertex AI](https://cloud.google.com/vertex-ai), including [industry-specific solutions](https://cloud.google.com/solutions#industry-solutions).
- **Multimodal Tasks:** Using vision-enabled models for image understanding and analysis with [Gemini Pro Vision](https://deepmind.google/technologies/gemini/), supporting advanced [computer vision applications](https://cloud.google.com/vertex-ai/docs/generative-ai/multimodal/overview).
- **Research and Development:** Leveraging Gemma's open-source capabilities for innovation and experimentation, with [comprehensive documentation](https://ai.google.dev/gemma/docs) and [community resources](https://github.com/google/gemma_pytorch).
- **Extended Context Processing:** Handling long documents with models supporting up to 2M tokens, ideal for document analysis and [knowledge processing](https://cloud.google.com/vertex-ai/docs/generative-ai/learn/overview). Learn more in our [Models Guide](https://APIpie.ai/docs/Features/Models).
- **Chat Applications:** Building conversational AI systems with [LibreChat](https://APIpie.ai/docs/Integrations/LibreChat) or [OpenWebUI](https://APIpie.ai/docs/Integrations/OpenwebUI), leveraging [Google's chat model best practices](https://cloud.google.com/vertex-ai/docs/generative-ai/chat/chat-prompts).

---

### **Ethical Considerations**

Google's AI models are designed with responsible AI principles in mind. Users should implement appropriate safeguards and consider potential biases in model outputs. For guidance on responsible AI usage, see Google's [AI Principles](https://ai.google/responsibility/principles/), [Responsible AI Practices](https://ai.google/responsibility/responsible-ai-practices/).

---

### **Licensing**

The Google Series includes both proprietary and open-source models. While Gemini models are available through Google Cloud with specific terms of service, [Gemma models](https://github.com/google-deepmind/gemma/blob/main/LICENSE) are released under the Apache 2.0 license for research and commercial use. For detailed licensing information, consult the [model-specific documentation](https://cloud.google.com/vertex-ai/docs/generative-ai/learn/model-versioning), usage guidelines.

:::tip
Try out the Google models in APIpie's various [supported integrations.](https://APIpie.ai/docs/Sandbox/Chat)
:::
