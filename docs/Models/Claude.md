<div align="center">
<img src="https://apipie.ai/docs/img/Models/Claude.png" alt="Anthropic Claude" width="100%" />
</div>

:::info
For detailed information about using models with APIpie, check out our [Models Overview](https://APIpie.ai/docs/Features/Models) and [Completions Guide](https://APIpie.ai/docs/Features/Completions).
:::

### **Description**

The [Claude Series](https://www.anthropic.com/claude) represents Anthropic's family of state-of-the-art large language models. These models, developed using [Constitutional AI](https://www.anthropic.com/research), leverage cutting-edge technology to deliver exceptional performance in natural language processing, instruction-following tasks, and extended-context interactions. The models are available through various providers integrated with [APIpie's routing system](https://APIpie.ai/docs/Features/Routing).

#### **Key Features**

- **Extended Token Capacity:** Models support context lengths from 8K to 200K tokens for handling various text processing needs.
- **Multi-Provider Availability:** Accessible across platforms like [OpenRouter](https://openrouter.ai/), [EdenAI](https://www.edenai.co/), [Anthropic](https://www.anthropic.com/), and [Amazon Bedrock](https://aws.amazon.com/bedrock/).
- **Diverse Applications:** Optimized for chat, instruction-following, analysis, writing, and multimodal tasks.
- **Constitutional AI:** Built with advanced safety measures and ethical considerations.
- **Multimodal Capabilities:** Claude-3 models can understand and analyze images alongside text.

---

### **Model Comparison and Monitoring**

When choosing between Claude models, APIpie provides comprehensive monitoring tools to help make informed decisions:

**Performance Monitoring:**
- Real-time availability tracking across providers (Anthropic, OpenRouter, Bedrock, EdenAI)
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
- Compare costs and pricing across different Claude models and providers
- Track performance metrics to optimize response times
- Make data-driven decisions based on availability and reliability
- Monitor system health and anticipate potential issues

:::tip
Use the [Models Route](https://APIpie.ai/docs/Features/Models) to access real-time pricing and performance data for all Claude models.
:::

### **Model List in the Claude Series**

#### **Model List updates dynamically please see [the Models Route](https://APIpie.ai/docs/Features/Models#fetching-models) for the up to date list of models**

:::info
For information about model performance and benchmarks, see the [Claude Technical Report](https://www-files.anthropic.com/production/images/Model-Card-Claude-3.pdf). The Claude-3 and Claude-3.5 series (Opus, Sonnet, Haiku) represent the latest generations with enhanced capabilities including multimodal understanding and increased response token limits up to 8,192 tokens, while the Claude-2 series offers robust performance for text-based tasks.
:::

|                                      |                |                     |                                       |                 |
| ------------------------------------ | -------------- | ------------------- | ------------------------------------- | --------------- |
| **Model Name**                       | **Max Tokens** | **Response Tokens** | **Provider**                          | **Type**        |
| claude-3-opus                        | 200,000        | 4,096               | Anthropic                             | LLM             |
| claude-3-5-sonnet                    | 200,000        | 4,096               | Anthropic                             | LLM             |
| claude-3-opus                        | 200,000        | 4,096               | OpenRouter                            | LLM             |
| claude-3-sonnet                      | 200,000        | 4,096               | OpenRouter                            | Vision          |
| claude-3-haiku                       | 200,000        | 4,096               | OpenRouter                            | Vision          |
| claude-3-5-sonnet                    | 200,000        | 8,192               | OpenRouter                            | LLM             |
| claude-3-5-haiku                     | 200,000        | 8,192               | OpenRouter                            | LLM             |
| claude-3-5-haiku-20241022            | 200,000        | 8,192               | OpenRouter                            | LLM             |
| claude-2.0                           | 100,000        | 4,096               | OpenRouter                            | LLM             |
| claude-2.1                           | 200,000        | 4,096               | OpenRouter                            | LLM             |
| claude-3-sonnet                      | 200,000        | 4,096               | Bedrock                               | Vision          |
| claude-3-haiku                       | 200,000        | 4,096               | Bedrock                               | Vision          |
| claude-3-opus-20240229-v1            | 200,000        | 4,096               | Bedrock                               | LLM             |
| claude-3-5-sonnet                    | 200,000        | 4,096               | Bedrock                               | LLM             |
| claude-3-5-haiku-20241022-v1         | 200,000        | 4,096               | Bedrock                               | LLM             |
| claude-2                             | 200,000        | 4,096               | Bedrock                               | LLM             |
| claude-instant-1                     | 100,000        | 4,096               | Bedrock                               | LLM             |
| claude-3-haiku                       | 200,000        | 4,096               | EdenAI                                | Vision          |
| claude-3-sonnet                      | 200,000        | 4,096               | EdenAI                                | Vision          |
| claude-3-5-sonnet                    | 200,000        | 4,096               | EdenAI                                | LLM             |
| claude-2                             | 200,000        | 4,096               | EdenAI                                | LLM             |
| claude-instant-1                     | 100,000        | 4,096               | EdenAI                                | LLM             |

---

### Example API Call

Below is an example of how to use the [Chat Completions API](https://APIpie.ai/docs/Features/Completions) to interact with a model from the **Claude Series**, such as `claude-3-opus`.
```bash
curl -L -X POST 'https://apipie.ai/v1/chat/completions' \
-H 'Content-Type: application/json' \
-H 'Accept: application/json' \
-H 'Authorization: Bearer <YOUR_API_KEY>' \
--data-raw '{
  "provider": "anthropic",
  "model": "claude-3-opus",
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

The expected response structure for the Claude model might look like this:

```json
{
  "id": "chatcmpl-12345example12345",
  "object": "chat.completion",
  "created": 1729535643,
  "provider": "anthropic",
  "model": "claude-3-opus",
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

- **Provider:** Specify the provider or leave blank for [automatic selection](https://APIpie.ai/docs/Features/Routing).
- **Model:** Use any model from the Claude Series suited to your task. See [Models Guide](https://APIpie.ai/docs/Features/Models#fetching-models).
- **Max Tokens:** Set the maximum response token count (e.g., 150 in this example).
- **Messages:** Format your request with a sequence of messages, including user input and system instructions. See [message formatting](https://APIpie.ai/docs/Features/Completions).

This example demonstrates how to seamlessly query models from the Claude Series for conversational or instructional tasks.

---

### **Applications and Integrations**

- **Conversational AI:** Powering chatbots, virtual assistants, and other dialogue-based systems. Try it with [LibreChat](https://APIpie.ai/docs/Integrations/LibreChat) or [OpenWebUI](https://APIpie.ai/docs/Integrations/OpenwebUI).
- **Analysis and Research:** Leveraging Claude's strong analytical capabilities for data analysis and research tasks.
- **Content Creation:** Using Claude's writing abilities for content generation and editing.
- **Extended Context Tasks:** Processing long documents with models supporting up to 200K tokens. Learn more in our [Models Guide](https://APIpie.ai/docs/Features/Models).
- **Educational Support:** Providing detailed explanations and tutoring across various subjects.
- **Multimodal Analysis:** Using Claude-3's ability to understand and analyze images alongside text for richer interactions.
- **Vision Tasks:** Leveraging image understanding capabilities for tasks like visual analysis, chart interpretation, and document processing.

---

### **Ethical Considerations**

Claude models are built with Constitutional AI principles to ensure safe and ethical behavior. Users should still implement appropriate safeguards and consider potential biases in model outputs. For guidance on responsible AI usage, see Anthropic's [Safety Practices](https://support.anthropic.com/en/articles/8106465-our-approach-to-user-safety).

---

### **Licensing**

The Claude Series is available through Anthropic's API and partner platforms. Usage is subject to Anthropic's [Terms of Service](https://www.anthropic.com/legal/terms) and respective provider agreements. For detailed licensing information, consult [Anthropic's documentation](https://docs.anthropic.com/) and respective hosting providers.

:::tip
Try out the Claude models in APIpie's various [supported integrations.](https://APIpie.ai/docs/Sandbox/Chat)
:::
