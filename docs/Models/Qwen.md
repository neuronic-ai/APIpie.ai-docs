<div align="center">
<img src="https://apipie.ai/docs/img/Models/Qwen.jpeg" alt="Qwen" width="100%" />
</div>

:::info
For detailed information about using models with APIpie, check out our [Models Overview](https://APIpie.ai/docs/Features/Models) and [Completions Guide](https://APIpie.ai/docs/Features/Completions).
:::

### **Model Comparison and Monitoring**

When choosing between Qwen models, APIpie provides comprehensive monitoring tools to help make informed decisions:

**Performance Monitoring:**
- Real-time availability tracking across providers (OpenRouter, EdenAI, Together, Bedrock)
- Latency metrics and historical performance data
- Response time comparisons between different model versions
- Specific performance tracking for Chat, Instruction, and Vision-Language variants

**Pricing & Cost Analysis:**
- Live pricing updates through our [Models Route](https://APIpie.ai/docs/Features/Models) & [Dashboard](https://apipie.ai/dashboard) 
- Cost comparisons across different providers and model variants
- Usage-based optimization recommendations
- Provider-specific pricing tracking

**Health Metrics:**
- Global AI health dashboard for real-time status
- Provider reliability tracking
- Model uptime statistics
- Performance monitoring across different capabilities (chat, instruction, vision)

This monitoring system helps users:
- Compare costs and pricing across different Qwen models and providers
- Track performance metrics to optimize response times
- Make data-driven decisions based on availability and reliability
- Monitor system health and anticipate potential issues
- Choose optimal model based on performance and cost needs

:::tip
Use the [Models Route](https://APIpie.ai/docs/Features/Models) to access real-time pricing and performance data for all Qwen models.
:::

### **Description**

The [Qwen Series](https://github.com/QwenLM/Qwen) represents a comprehensive family of transformer-based models optimized for a wide range of NLP applications. Developed by [Alibaba Cloud](https://www.alibabacloud.com/), these models leverage cutting-edge technology to deliver exceptional performance in conversational AI, instruction-following tasks, and extended-context interactions. The models are available through various providers integrated with [APIpie's routing system](https://APIpie.ai/docs/Features/Routing).

#### **Key Features**

- **Extended Token Capacity:** All models support up to 32,768 tokens for efficient handling of long-text inputs and context-rich conversations. 
- **Multi-Provider Availability:** Accessible across platforms like [OpenRouter](https://openrouter.ai/), [EdenAI](https://www.edenai.co/), [Together](https://www.together.ai/), and [Amazon Bedrock](https://aws.amazon.com/bedrock/).
- **Diverse Subtypes:** Includes Chat, Instruction, and Vision-Language variants tailored for specific applications.
- **Scalability:** Models ranging from lightweight solutions (1.5B parameters) to high-capacity configurations (72B parameters) for advanced tasks.

---

### **Model List in the Qwen Series**

#### **Model List updates dynamically please see [the Models Route](https://APIpie.ai/docs/Features/Models#fetching-models) for the up to date list of models**

:::info
For information about model performance and benchmarks, see the [Qwen Technical Report](https://github.com/QwenLM/Qwen/blob/main/QWEN_TECHNICAL_REPORT.pdf).
:::

|                        |                |                     |                                       |                 |
| ---------------------- | -------------- | ------------------- | ------------------------------------- | --------------- |
| **Model Name**         | **Max Tokens** | **Response Tokens** | **Providers**                         | **Subtype**     |
| qwen-2-72b-instruct    | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Instruction     |
| qwen-2-7b-instruct     | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Instruction     |
| Qwen2-1.5B-Instruct    | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Instruction     |
| Qwen2-7B-Instruct      | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Instruction     |
| Qwen1.5-14B-Chat       | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Chat            |
| Qwen1.5-1.8B-Chat      | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Chat            |
| Qwen1.5-32B-Chat       | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Chat            |
| Qwen1.5-7B-Chat        | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Chat            |
| Qwen1.5-0.5B-Chat      | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Chat            |
| Qwen1.5-4B-Chat        | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Chat            |
| qwen-2-vl-7b-instruct  | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Vision-Language |
| qwen-2-vl-72b-instruct | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Vision-Language |
| qwen-2.5-72b-instruct  | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Instruction     |
| qwen-2.5-7b-instruct   | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Instruction     |
| eva-qwen-2.5-32b       | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Instruction     |
| Qwen2-72B-Instruct     | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Instruction     |
| Qwen2-72B              | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Chat            |
| Qwen1.5-0.5B           | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Chat            |
| Qwen1.5-1.8B           | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Chat            |
| Qwen1.5-4B             | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Chat            |
| Qwen1.5-7B             | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Chat            |
| Qwen1.5-72B            | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Chat            |
| Qwen2-7B               | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Chat            |
| Qwen2-1.5B             | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Chat            |
| Qwen1.5-32B            | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Chat            |
| Qwen1.5-14B            | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Chat            |
| qwen1-5\_32k           | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Chat            |
| qwen2\_32k             | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Chat            |

---

### Example API Call

Below is an example of how to use the [Chat Completions API](https://APIpie.ai/docs/Features/Completions) to interact with a model from the **Qwen Series**, such as `qwen-2-7b-instruct`.
```bash
curl -L -X POST 'https://apipie.ai/v1/chat/completions' \
-H 'Content-Type: application/json' \
-H 'Accept: application/json' \
-H 'Authorization: Bearer <YOUR_API_KEY>' \
--data-raw '{
  "provider": "openrouter",
  "model": "qwen-2-7b-instruct",
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

The expected response structure for the Qwen model might look like this:

```json
{
  "id": "chatcmpl-12345example12345",
  "object": "chat.completion",
  "created": 1729535643,
  "provider": "openrouter",
  "model": "qwen-2-7b-instruct",
  "choices": [
    {
      "index": 0,
      "message": {
        "role": "assistant",
        "content": "Photosynthesis is the process by which green plants, algae, and some bacteria convert light energy into chemical energy. Here’s how it works:\n\n1. **Light Absorption**: Plants capture light energy using a pigment called chlorophyll, which is found in chloroplasts.\n\n2. **Water and Carbon Dioxide**: They absorb water through their roots and carbon dioxide from the air.\n\n3. **Glucose Production**: The light energy is used to convert water and carbon dioxide into glucose (a sugar) and oxygen. The equation is:\n   \n   6CO2 + 6H2O + light energy → C6H12O6 + 6O2\n\nThis process provides energy for the plant and releases oxygen into the atmosphere."
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
- **Model:** Use any model from the Qwen Series, such as `qwen-2-7b-instruct` or others suited to your task. See [Models Guide](https://APIpie.ai/docs/Features/Models#fetching-models).
- **Max Tokens:** Set the maximum response token count (e.g., 150 in this example).
- **Messages:** Format your request with a sequence of messages, including user input and system instructions. See [message formatting](https://APIpie.ai/docs/Features/Completions).

This example demonstrates how to seamlessly query models from the Qwen Series for conversational or instructional tasks.

---

### **Applications and Integrations**

- **Conversational AI:** Powering chatbots, virtual assistants, and other dialogue-based systems. Try it with [LibreChat](https://APIpie.ai/docs/Integrations/LibreChat) or [OpenWebUI](https://APIpie.ai/docs/Integrations/OpenwebUI).
- **Instructional Scenarios:** Tailored for executing complex, multi-step tasks based on user inputs. See [Qwen's instruction guide](https://github.com/QwenLM/Qwen/tree/main/examples).
- **Vision-Language Models:** Addressing multimodal tasks combining textual and visual inputs using specialized VL models. Learn more in [Qwen-VL documentation](https://github.com/QwenLM/Qwen-VL).
- **Extended Context Tasks:** Providing coherent responses for long-sequence inputs. See our [Models Guide](https://APIpie.ai/docs/Features/Models) for details.

---

### **Ethical Considerations**

The Qwen models are highly capable but lack inherent moderation systems. Users are encouraged to implement safeguards for appropriate deployment in sensitive contexts. For guidance on responsible AI usage, see [Alibaba Cloud's Best Practices.](https://resource.alibabacloud.com/bestpractice)

---

### **Licensing**

The Qwen Series is released under flexible licensing terms, allowing for both commercial and non-commercial usage. For detailed terms, consult the [official Qwen repository](https://github.com/QwenLM/Qwen/blob/main/LICENSE), [model cards](https://huggingface.co/Qwen), and respective hosting providers.

:::tip
Try out the Qwen models in APIpie's various [supported integrations.](https://APIpie.ai/docs/Sandbox/Chat)
:::
