<div align="center">
<img src="https://apipie.ai/docs/img/Models/Mistral.png" alt="Mistral AI" width="100%" />
</div>

:::info
For detailed information about using models with APIpie, check out our [Models Overview](https://APIpie.ai/docs/Features/Models) and [Completions Guide](https://APIpie.ai/docs/Features/Completions).
:::

### **Model Comparison and Monitoring**

When choosing between Mistral models, APIpie provides comprehensive monitoring tools to help make informed decisions:

**Performance Monitoring:**
- Real-time availability tracking across providers (OpenRouter, Together, Deepinfra, Bedrock, EdenAI)
- Latency metrics and historical performance data
- Response time comparisons between different model versions
- Specific performance tracking for Mixtral and Mistral variants

**Pricing & Cost Analysis:**
- Live pricing updates through our [Models Route](https://APIpie.ai/docs/Features/Models) & [Dashboard](https://apipie.ai/dashboard) 
- Cost comparisons across different providers and model variants
- Usage-based optimization recommendations
- Provider-specific pricing tracking

**Health Metrics:**
- Global AI health dashboard for real-time status
- Provider reliability tracking
- Model uptime statistics
- Performance monitoring across different capabilities (chat, code, embeddings)

This monitoring system helps users:
- Compare costs and pricing across different Mistral models and providers
- Track performance metrics to optimize response times
- Make data-driven decisions based on availability and reliability
- Monitor system health and anticipate potential issues
- Choose optimal provider based on performance and cost needs

:::tip
Use the [Models Route](https://APIpie.ai/docs/Features/Models) to access real-time pricing and performance data for all Mistral models.
:::

### **Description**

[Mistral AI](https://mistral.ai/), a leading European AI company founded by former [DeepMind](https://deepmind.google/) and [Meta AI](https://ai.meta.com/) researchers, develops powerful large language models known for their efficiency and performance. Their models, including the groundbreaking [Mixtral-8x7B](https://mistral.ai/news/mixtral-of-experts/) (which outperforms GPT-3.5)(one of the best 7B models), consistently achieve top rankings in [open-source model benchmarks](https://huggingface.co/spaces/HuggingFaceH4/open_llm_leaderboard). The [Mixtral architecture](https://mistral.ai/news/mixtral-of-experts/) uses a Mixture of Experts approach, allowing it to achieve remarkable performance while maintaining computational efficiency. These models are available through various providers integrated with [APIpie's routing system](https://APIpie.ai/docs/Features/Routing).

#### **Key Features**

- **Extended Token Capacity:** Models support context lengths from 4K to 256K tokens, with specialized variants like [Codestral-Mamba](https://huggingface-co.translate.goog/mistralai/Mamba-Codestral-7B-v0.1) (256K tokens) and [Mistral-Nemo](https://huggingface-co.translate.goog/mistralai/Mistral-Nemo-Instruct-2407) (128K tokens).
- **Multi-Provider Availability:** Accessible through [OpenRouter](https://openrouter.ai/), [Together](https://www.together.ai/), [Deepinfra](https://deepinfra.com/), [Bedrock](https://aws.amazon.com/bedrock/), [EdenAI](https://www.edenai.co/).
- **Diverse Applications:** Optimized for chat, instruction-following, code generation, and embeddings, with specialized models for different tasks.
- **Efficiency:** High performance with optimized parameter counts and innovative architectures like Mixture of Experts and Mamba.

---

### **Model List in the Mistral Series**

#### **Model List updates dynamically please see [the Models Route](https://APIpie.ai/docs/Features/Models#fetching-models) for the up to date list of models**

:::info
For information about model performance and benchmarks, see the [Mistral AI Documentation](https://docs.mistral.ai/) and [Model Cards](https://huggingface.co/mistralai).
:::

|                                      |                |                     |                                       |                 |
| ------------------------------------ | -------------- | ------------------- | ------------------------------------- | --------------- |
| **Model Name**                       | **Max Tokens** | **Response Tokens** | **Providers**                         | **Subtype**     |
| **Mixtral Models**                   |                |                     |                                       |                 |
| Mixtral-8x22B-Instruct-v0.1         | 65,536         | 65,536             | Deepinfra, Together, OpenRouter       | Chat            |
| Mixtral-8x7B-Instruct-v0.1          | 32,768         | 32,768             | Deepinfra, Together                   | Chat            |
| Mixtral-8x7B-v0.1                   | 32,768         | 32,768             | Together                              | Language        |
| mixtral-8x7b-instruct              | 32,768         | 32,768             | OpenRouter                            | Chat            |
| mixtral-8x7b                        | 32,768         | 32,768             | OpenRouter                            | Chat            |
| mixtral-8x7b-instruct-v0           | 4,096          | 4,096              | Bedrock                               | Chat            |
| **Mistral Models**                   |                |                     |                                       |                 |
| Mistral-7B-Instruct-v0.1            | 4,096          | 4,096              | Deepinfra, Together, OpenRouter       | Chat            |
| Mistral-7B-Instruct-v0.2            | 32,768         | 32,768             | Deepinfra, Together, Monster          | Chat            |
| Mistral-7B-Instruct-v0.3            | 32,768         | 4,096              | Together, OpenRouter                  | Chat            |
| Mistral-7B-v0.1                     | 4,096          | 4,096              | Together                              | Language        |
| mistral-7b-instruct                | 32,768         | 32,768             | OpenRouter                            | Chat            |
| mistral-7b-instruct-v0             | 8,192          | 8,192              | Bedrock                               | Chat            |
| mistral-large                       | 128,000        | 128,000            | OpenRouter                            | Chat            |
| mistral-large                       | 8,192          | 8,192              | Bedrock                               | Chat            |
| mistral-medium                      | 32,000         | 32,000             | OpenRouter                            | Chat            |
| mistral-small                       | 32,000         | 32,000             | OpenRouter                            | Chat            |
| mistral-tiny                        | 32,000         | 32,000             | OpenRouter                            | Chat            |
| mistral-small-2402-v1              | 8,192          | 8,192              | Bedrock                               | Chat            |
| mistral-nemo                       | 128,000        | 4,096              | OpenRouter                            | Chat            |
| **Specialized Models**               |                |                     |                                       |                 |
| codestral-mamba                    | 256,000        | 256,000            | OpenRouter                            | Code            |
| openhermes-2.5-mistral-7b          | 4,096          | 4,096              | OpenRouter                            | Chat            |
| pixtral-12b                        | 4,096          | 4,096              | OpenRouter                            | Chat            |
| pixtral-large-2411                 | 128,000        | 128,000            | OpenRouter                            | Chat            |
| ministral-8b                       | 128,000        | 128,000            | OpenRouter                            | Chat            |
| ministral-3b                       | 128,000        | 128,000            | OpenRouter                            | Chat            |
| **Other Variants**                   |                |                     |                                       |                 |
| 1024__mistral-embed                | -              | -                  | EdenAI                                | Embedding       |
| large-latest                       | -              | -                  | EdenAI                                | Chat            |
| tiny                               | -              | -                  | EdenAI                                | Chat            |
| small                              | -              | -                  | EdenAI                                | Chat            |
| ministral-3b-latest               | -              | -                  | EdenAI                                | Chat            |
| ministral-8b-latest               | -              | -                  | EdenAI                                | Chat            |

---

### Example API Call

Below is an example of how to use the [Chat Completions API](https://APIpie.ai/docs/Features/Completions) to interact with a Mistral model:

```bash
curl -L -X POST 'https://apipie.ai/v1/chat/completions' \
-H 'Content-Type: application/json' \
-H 'Accept: application/json' \
-H 'Authorization: Bearer <YOUR_API_KEY>' \
--data-raw '{
  "provider": "openrouter",
  "model": "mixtral-8x7b-instruct",
  "max_tokens": 150,
  "messages": [
    {
      "role": "user",
      "content": "What are the key differences between traditional and quantum computing?"
    }
  ]
}'
```

---

### Response Example

```json
{
  "id": "chatcmpl-12345example12345",
  "object": "chat.completion",
  "created": 1729535643,
  "provider": "openrouter",
  "model": "mixtral-8x7b-instruct",
  "choices": [
    {
      "index": 0,
      "message": {
        "role": "assistant",
        "content": "Here are the key differences between traditional and quantum computing:\n\n1. **Information Processing**\n- Traditional: Uses bits (0 or 1)\n- Quantum: Uses qubits (can be 0, 1, or both simultaneously)\n\n2. **Computation Method**\n- Traditional: Sequential processing\n- Quantum: Parallel processing through superposition\n\n3. **Processing Power**\n- Traditional: Linear scaling\n- Quantum: Exponential scaling for certain tasks\n\n4. **Applications**\n- Traditional: General-purpose computing\n- Quantum: Specialized tasks like cryptography and complex simulations"
      },
      "finish_reason": "stop"
    }
  ],
  "usage": {
    "prompt_tokens": 18,
    "completion_tokens": 132,
    "total_tokens": 150
  }
}
```

---

### API Highlights

- **Provider Selection:** Choose from multiple providers or use [automatic routing](https://APIpie.ai/docs/Features/Routing)
- **Model Options:** Select from various Mistral models based on your needs
- **Token Management:** Set appropriate token limits based on model capabilities
- **Message Formatting:** Structure your prompts effectively using [message formatting](https://APIpie.ai/docs/Features/Completions)

---

### **Applications and Integrations**

- **Conversational AI:** Build chatbots and virtual assistants.
- **Code Generation:** Leverage specialized models like Codestral-Mamba for programming tasks
- **Enterprise Solutions:** Deploy models for business applications
- **Extended Context Processing:** Handle long documents with models supporting up to 256K tokens
- **Research Applications:** Utilize [open-weights models](https://github.com/mistralai) for academic research and development

---

### **Ethical Considerations**

Mistral models should be used responsibly with appropriate safeguards. For guidance on responsible AI usage, see Mistral's [terms](https://mistral.ai/terms/).

---

### **Licensing**

Mistral models are available under various licensing terms, including the [Apache 2.0 License](https://www.apache.org/licenses/LICENSE-2.0) for open-source models. For detailed information, consult [Mistral's documentation](https://docs.mistral.ai/).

:::tip
Try out Mistral models in APIpie's [supported integrations](https://APIpie.ai/docs/Sandbox/Chat).
:::
