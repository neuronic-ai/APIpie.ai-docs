<div align="center">
<img src="https://apipie.ai/docs/img/Models/Hermes.png" alt="Hermes" width="100%" />
</div>
:::info
For detailed information about using models with APIpie, check out our [Models Overview](https://APIpie.ai/docs/Features/Models) and [Completions Guide](https://APIpie.ai/docs/Features/Completions).
:::

### **Model Comparison and Monitoring**

When choosing between Hermes models, APIpie provides comprehensive monitoring tools to help make informed decisions:

**Performance Monitoring:**
- Real-time availability tracking across providers (OpenRouter, Together, Deepinfra)
- Latency metrics and historical performance data
- Response time comparisons between different model versions
- Specific performance tracking for vision-enabled models

**Pricing & Cost Analysis:**
- Live pricing updates through our [Models Route](https://APIpie.ai/docs/Features/Models) & [Dashboard](https://apipie.ai/dashboard) 
- Cost comparisons across different providers and model variants
- Usage-based optimization recommendations
- Provider-specific pricing tracking

**Health Metrics:**
- Global AI health dashboard for real-time status
- Provider reliability tracking
- Model uptime statistics
- Performance monitoring across different capabilities (text, vision)

This monitoring system helps users:
- Compare costs and pricing across different Hermes models and providers
- Track performance metrics to optimize response times
- Make data-driven decisions based on availability and reliability
- Monitor system health and anticipate potential issues
- Choose optimal provider based on performance and cost needs

:::tip
Use the [Models Route](https://APIpie.ai/docs/Features/Models) to access real-time pricing and performance data for all Hermes models.
:::

### **Description**

The Hermes Series represents a collection of advanced large language models, primarily developed by [Nous Research](https://nousresearch.com/) and the open-source AI community. These models are fine-tuned versions built on top of powerful base models like [Llama](https://ai.meta.com/llama/), [Mistral](https://mistral.ai/), and [Mixtral](https://mistral.ai/news/mixtral-of-experts/). The models leverage state-of-the-art [Direct Preference Optimization (DPO)](https://arxiv.org/abs/2305.18290) and other advanced training techniques for enhanced performance in natural language processing and instruction-following tasks. You can explore the models' technical details and training methodologies on their [Hugging Face model cards](https://huggingface.co/NousResearch). The models are available through various providers integrated with [APIpie's routing system](https://APIpie.ai/docs/Features/Routing).

#### **Key Features**

- **Extended Token Capacity:** Models support context lengths from 4K to 32K tokens for handling various text processing needs, with advanced [attention mechanisms](https://arxiv.org/abs/1706.03762) for efficient processing.
- **Multi-Provider Availability:** Accessible across platforms like [OpenRouter](https://openrouter.ai/), [Together](https://www.together.ai/), and [Deepinfra](https://deepinfra.com/).
- **Diverse Applications:** Optimized for chat, instruction-following, and vision tasks through specialized [multi-task training](https://arxiv.org/abs/2302.06646).
- **Advanced Architecture:** Built on state-of-the-art base models with specialized fine-tuning using techniques like [constitutional AI](https://arxiv.org/abs/2212.08073) and [RLHF](https://arxiv.org/abs/2203.02155).

---

### **Model List in the Hermes Series**

#### **Model List updates dynamically please see [the Models Route](https://APIpie.ai/docs/Features/Models#fetching-models) for the up to date list of models**

|                                      |                |                     |                                       |                 |
| ------------------------------------ | -------------- | ------------------- | ------------------------------------- | --------------- |
| **Model Name**                       | **Max Tokens** | **Response Tokens** | **Provider**                          | **Type**        |
| nous-hermes-llama2-13b              | 4,096          | 4,096               | openrouter                            | llm             |
| nous-hermes-2-mixtral-8x7b-dpo      | 32,768         | 32,768              | openrouter                            | llm             |
| nous-hermes-2-vision-7b             | 4,096          | 4,096               | openrouter                            | vision          |
| openhermes-2.5-mistral-7b           | 4,096          | 4,096               | openrouter                            | llm             |
| chronos-hermes-13b-v2               | 4,096          | 4,096               | deepinfra                             | llm             |
| Nous-Hermes-2-Mixtral-8x7B-DPO      | 32,768         | 32,768              | together                              | llm             |

:::info
For information about model performance and benchmarks, see the [Nous Research Blog](https://nousresearch.com/blog) and explore detailed evaluations on the [Open LLM Leaderboard](https://huggingface.co/spaces/HuggingFaceH4/open_llm_leaderboard).
:::

---

### Example API Call

Below is an example of how to use the [Chat Completions API](https://APIpie.ai/docs/Features/Completions) to interact with a model from the **Hermes Series**, such as `nous-hermes-2-mixtral-8x7b-dpo`.

```bash
curl -L -X POST 'https://apipie.ai/v1/chat/completions' \
-H 'Content-Type: application/json' \
-H 'Accept: application/json' \
-H 'Authorization: Bearer <YOUR_API_KEY>' \
--data-raw '{
  "provider": "openrouter",
  "model": "nous-hermes-2-mixtral-8x7b-dpo",
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

The expected response structure for the Hermes model might look like this:

```json
{
  "id": "chatcmpl-12345example12345",
  "object": "chat.completion",
  "created": 1729535643,
  "provider": "openrouter",
  "model": "nous-hermes-2-mixtral-8x7b-dpo",
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
- **Model:** Use any model from the Hermes Series, such as `nous-hermes-2-mixtral-8x7b-dpo` or others suited to your task. See [Models Guide](https://APIpie.ai/docs/Features/Models#fetching-models).
- **Max Tokens:** Set the maximum response token count (e.g., 150 in this example).
- **Messages:** Format your request with a sequence of messages, including user input and system instructions. See [message formatting](https://APIpie.ai/docs/Features/Completions).

This example demonstrates how to seamlessly query models from the Hermes Series for conversational or instructional tasks.

---

### **Applications and Integrations**

- **Conversational AI:** Powering chatbots, virtual assistants, and other dialogue-based systems. Try it with [LibreChat](https://APIpie.ai/docs/Integrations/LibreChat), [OpenWebUI](https://APIpie.ai/docs/Integrations/OpenwebUI), or integrate with popular frameworks like [LangChain](https://python.langchain.com/) and [LlamaIndex](https://www.llamaindex.ai/).
- **Vision Tasks:** Using vision-enabled models like `nous-hermes-2-vision-7b` for image understanding and multimodal applications, leveraging [advanced vision-language architectures](https://arxiv.org/abs/2303.08891).
- **Extended Context Tasks:** Processing longer documents with models supporting up to 32K tokens, utilizing efficient [attention mechanisms](https://arxiv.org/abs/2307.08621). Learn more in our [Models Guide](https://APIpie.ai/docs/Features/Models).
- **Instruction Following:** Leveraging advanced fine-tuning techniques like [DPO](https://arxiv.org/abs/2305.18290) and [Constitutional AI](https://arxiv.org/abs/2212.08073) for improved task completion and instruction following.
- **Research and Development:** Contributing to open-source AI development through [model merging](https://arxiv.org/abs/2306.01708), [knowledge distillation](https://arxiv.org/abs/2310.05344), and other techniques.

---

### **Ethical Considerations**

The Hermes models are powerful tools that should be used responsibly. Users should implement appropriate safeguards and consider potential biases in model outputs.

---

### **Licensing**

The Hermes Series models are available under various licenses depending on their base models and providers. For detailed licensing information, consult the respective model repositories on [Hugging Face](https://huggingface.co/NousResearch).

:::tip
Try out the Hermes models in APIpie's various [supported integrations.](https://APIpie.ai/docs/Sandbox/Chat)
:::
