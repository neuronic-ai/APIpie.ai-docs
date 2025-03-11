<div align="center">
<img src="https://apipie.ai/docs/img/openai-white.png" alt="OpenAI" width="100%" />
</div>

:::info
For detailed information about using models with APIpie, check out our [Models Overview](https://APIpie.ai/docs/Features/Models) and [Completions Guide](https://APIpie.ai/docs/Features/Completions).
:::

### **Model Comparison and Monitoring**

When choosing between OpenAI models, APIpie provides comprehensive monitoring tools to help make informed decisions:

**Performance Monitoring:**
- Real-time availability tracking across providers (OpenAI, OpenRouter, EdenAI, DeepInfra)
- Latency metrics and historical performance data
- Response time comparisons between different model versions
- Specific performance tracking for GPT-4, GPT-3.5, and O1 variants

**Pricing & Cost Analysis:**
- Live pricing updates through our [Models Route](https://APIpie.ai/docs/Features/Models) & [Dashboard](https://apipie.ai/dashboard) 
- Cost comparisons across different providers and model variants
- Usage-based optimization recommendations
- Provider-specific pricing tracking

**Health Metrics:**
- Global AI health dashboard for real-time status
- Provider reliability tracking
- Model uptime statistics
- Performance monitoring across different capabilities (chat, vision, audio, voice)

This monitoring system helps users:
- Compare costs and pricing across different OpenAI models and providers
- Track performance metrics to optimize response times
- Make data-driven decisions based on availability and reliability
- Monitor system health and anticipate potential issues
- Choose optimal provider based on performance and cost needs

:::tip
Use the [Models Route](https://APIpie.ai/docs/Features/Models) to access real-time pricing and performance data for all OpenAI models.
:::

### **Description**

[OpenAI's](https://openai.com/) suite of language models represents the cutting edge in artificial intelligence technology. These models, including the renowned [GPT-4,](https://platform.openai.com/docs/models/#gpt-4o) [GPT-3.5](https://platform.openai.com/docs/models/#gpt-3-5-turbo) and [o1 series](https://platform.openai.com/docs/models/#o1), deliver exceptional performance across a wide range of tasks. The models are available through various providers integrated with [APIpie's routing system](https://APIpie.ai/docs/Features/Routing).

The models come in several specialized variants:
- **Chat Models:** Standard chat models optimized for dialogue and instruction-following
- **ChatX Models:** Enhanced versions with additional capabilities like function calling and structured output
- **O1 Models:** Next-generation models  offering superior performance and reliability
- **Vision Models:** Capable of understanding and analyzing images alongside text
- **Audio Models:** Specialized for audio processing and transcription tasks
- **Voice Models:** Text-to-speech models with various voice options
- **Code Models:** Optimized for programming and technical documentation tasks

The O1 series represents OpenAI's latest advancement in language models, offering:
- Improved reasoning and problem-solving capabilities with up to 200K token context
- Enhanced consistency in outputs through specialized variants (preview, mini)
- Better handling of complex instructions with optimized response generation
- Superior performance in specialized tasks with provider-specific optimizations
- Flexible deployment options across multiple providers

#### **Key Features**

- **Extended Context Windows:** Models support context lengths from 4K to 128K tokens, enabling processing of extensive documents and conversations.
- **Multi-Provider Availability:** Accessible through [OpenAI](https://openai.com/), [OpenRouter](https://openrouter.ai/), [EdenAI](https://www.edenai.co/), and [DeepInfra](https://deepinfra.com/).
- **Advanced Capabilities:**
  - Function calling for structured tool use
  - JSON mode for reliable structured output
  - Parallel function calling for efficiency
  - System message control
  - Reproducible outputs with seeds
  - Temperature and top_p controls
  - O1 optimizations for enhanced performance
- **Multimodal Processing:** Support for text, images, and audio in a single conversation

---

### **Model List**

#### **Model List updates dynamically please see [the Models Route](https://APIpie.ai/docs/Features/Models#fetching-models) for the up to date list of models**

:::info
For information about model performance and benchmarks, see [OpenAI's Model Overview](https://platform.openai.com/docs/models/overview).
:::

|                                      |                |                     |                                       |                 |
| ------------------------------------ | -------------- | ------------------- | ------------------------------------- | --------------- |
| **Model Name**                       | **Max Tokens** | **Response Tokens** | **Providers**                         | **Type/Subtype**|
| gpt-4-turbo-preview                  | 128,000        | 4,096               | OpenAI                                | LLM/ChatX       |
| gpt-4-turbo                          | 128,000        | 4,096               | OpenAI, EdenAI                        | LLM/ChatX       |
| gpt-4-turbo-2024-04-09              | 4,096          | 4,096               | OpenAI, EdenAI                        | LLM/Chat        |
| gpt-4-1106-preview                   | 4,096          | 4,096               | OpenAI, EdenAI                        | LLM/Chat        |
| gpt-4                                | 8,191          | 4,096               | OpenAI, OpenRouter, EdenAI            | LLM/Chat        |
| gpt-4-0613                          | 8,192          | 8,192               | OpenAI                                | LLM/ChatX       |
| gpt-4-0314                          | 8,191          | 4,096               | EdenAI                                | LLM/Chat        |
| gpt-4-32k-0314                      | 32,767         | 4,096               | EdenAI                                | LLM/Chat        |
| gpt-4o                               | 128,000        | 16,384              | OpenAI, OpenRouter, EdenAI            | LLM/Chat,ChatX,Code|
| gpt-4o-mini                          | 128,000        | 16,384              | OpenAI, EdenAI                        | LLM/Chat,ChatX  |
| gpt-4o-mini-2024-07-18              | 16,384         | 16,384              | OpenAI                                | LLM/Chat,ChatX  |
| gpt-4o-2024-05-13                    | 4,096          | 4,096               | OpenAI, EdenAI                        | LLM/Chat,ChatX  |
| gpt-4o-2024-08-06                    | 16,384         | 16,384              | OpenAI                                | LLM/Chat,ChatX  |
| gpt-4o-2024-11-20                    | 16,384         | 16,384              | OpenAI, OpenRouter                    | LLM/Chat,ChatX  |
| o1-preview                           | 128,000        | 32,768              | OpenAI                                | LLM/ChatX       |
| o1-mini                             | 128,000        | 32,768              | EdenAI                                | LLM/Chat        |
| o1                                  | 200,000        | 100,000             | OpenRouter                            | LLM             |
| gpt-4-vision-preview                 | 128,000        | 4,096               | OpenAI, OpenRouter                    | Vision/Multimodal|
| gpt-4-1106-vision-preview           | 128,000        | 4,096               | OpenAI                                | Vision/ChatX    |
| gpt-4o-audio-preview                 | 16,384         | 16,384              | OpenAI                                | LLM             |
| gpt-4o-mini-audio-preview           | 128,000        | 16,384              | OpenAI                                | LLM             |
| gpt-4o-audio-preview-2024-12-17     | 16,384         | 16,384              | OpenAI                                | LLM             |
| gpt-4o-mini-audio-preview-2024-12-17| 128,000        | 16,384              | OpenAI                                | LLM             |
| gpt-3.5-turbo                        | 16,384         | 4,096               | OpenAI, EdenAI                        | LLM/Chat        |
| gpt-3.5-turbo-16k                    | 16,385         | 4,096               | EdenAI                                | LLM/Chat        |
| gpt-3.5-turbo-0125                   | 16,385         | 4,096               | OpenAI, EdenAI                        | LLM/Chat        |
| gpt-3.5-turbo-1106                   | 16,385         | 4,096               | OpenAI, EdenAI                        | LLM/Chat        |
| gpt-3.5-turbo-instruct              | 4,095          | 4,096               | OpenRouter                            | LLM/Chat        |
| tts-1-hd shimmer                    | -              | -                   | OpenAI                                | Voice/TTS       |
| tts-1-hd alloy                      | -              | -                   | OpenAI                                | Voice/TTS       |
| tts-1-hd echo                       | -              | -                   | OpenAI                                | Voice/TTS       |
| tts-1-hd fable                      | -              | -                   | OpenAI                                | Voice/TTS       |
| tts-1-hd onyx                       | -              | -                   | OpenAI                                | Voice/TTS       |
| tts-1-hd nova                       | -              | -                   | OpenAI                                | Voice/TTS       |
| tts-1-1106 alloy                    | -              | -                   | OpenAI                                | Voice/TTS       |
| tts-1-1106 echo                     | -              | -                   | OpenAI                                | Voice/TTS       |
| tts-1-1106 fable                    | -              | -                   | OpenAI                                | Voice/TTS       |
| tts-1-1106 onyx                     | -              | -                   | OpenAI                                | Voice/TTS       |
| tts-1-1106 nova                     | -              | -                   | OpenAI                                | Voice/TTS       |
| clip-vit-large-patch14-336          | -              | -                   | DeepInfra                             | Vision/Classification|
| clip-vit-large-patch14              | -              | -                   | DeepInfra                             | Vision/Classification|
| clip-vit-base-patch32               | -              | -                   | DeepInfra                             | Vision/Classification|
| whisper-large                       | -              | -                   | DeepInfra                             | Voice/ASR       |
| whisper-medium                      | -              | -                   | DeepInfra                             | Voice/ASR       |
| whisper-medium.en                   | -              | -                   | DeepInfra                             | Voice/ASR       |
| whisper-timestamped-medium          | -              | -                   | DeepInfra                             | Voice/ASR       |
| whisper-timestamped-medium.en       | -              | -                   | DeepInfra                             | Voice/ASR       |
| whisper-base                        | -              | -                   | DeepInfra                             | Voice/ASR       |
| whisper-base.en                     | -              | -                   | DeepInfra                             | Voice/ASR       |
| whisper-small                       | -              | -                   | DeepInfra                             | Voice/ASR       |
| whisper-small.en                    | -              | -                   | DeepInfra                             | Voice/ASR       |
| whisper-tiny                        | -              | -                   | DeepInfra                             | Voice/ASR       |
| whisper-tiny.en                     | -              | -                   | DeepInfra                             | Voice/ASR       |

---

### Example API Call

Below is an example of how to use the [Chat Completions API](https://APIpie.ai/docs/Features/Completions) with OpenAI's GPT-4 model:

```bash
curl -L -X POST 'https://apipie.ai/v1/chat/completions' \
-H 'Content-Type: application/json' \
-H 'Accept: application/json' \
-H 'Authorization: Bearer <YOUR_API_KEY>' \
--data-raw '{
  "provider": "openai",
  "model": "gpt-4-turbo-preview",
  "max_tokens": 150,
  "messages": [
    {
      "role": "user",
      "content": "What are the key differences between renewable and non-renewable energy sources?"
    }
  ]
}'
```

---

### Response Example

The expected response structure from an OpenAI model:

```json
{
  "id": "chatcmpl-abc123example456",
  "object": "chat.completion",
  "created": 1709234567,
  "provider": "openai",
  "model": "gpt-4-turbo-preview",
  "choices": [
    {
      "index": 0,
      "message": {
        "role": "assistant",
        "content": "Renewable and non-renewable energy sources differ in several key ways:\n\n1. Replenishment:\n- Renewable: Naturally replenished within a human lifetime (solar, wind, hydro)\n- Non-renewable: Take millions of years to form (fossil fuels)\n\n2. Environmental Impact:\n- Renewable: Generally lower emissions and environmental impact\n- Non-renewable: Higher carbon emissions and environmental degradation\n\n3. Availability:\n- Renewable: Unlimited but dependent on natural conditions\n- Non-renewable: Limited and depleting resources"
      },
      "logprobs": null,
      "finish_reason": "stop"
    }
  ],
  "usage": {
    "prompt_tokens": 20,
    "completion_tokens": 110,
    "total_tokens": 130,
    "prompt_characters": 82,
    "response_characters": 380,
    "cost": 0.003500,
    "latency_ms": 2800
  },
  "system_fingerprint": "fp_abc123def456"
}
```

---

### API Highlights

- **Provider:** Specify the provider or leave blank for [automatic selection](https://APIpie.ai/docs/Features/Routing).
- **Model:** Choose from OpenAI's range of models based on your needs. See [Models Guide](https://APIpie.ai/docs/Features/Models#fetching-models).
- **Max Tokens:** Set the maximum response length (varies by model).
- **Messages:** Structure your conversations with role-based messages. See [message formatting](https://APIpie.ai/docs/Features/Completions).

---

### **Applications and Integrations**

- **Conversational AI:** Power chatbots and virtual assistants with [GPT-4 and GPT-3.5](https://platform.openai.com/docs/guides/chat). Try with [LibreChat](https://APIpie.ai/docs/Integrations/LibreChat).
- **High-Performance Tasks:** Utilize O1 models for applications requiring superior reliability and consistent outputs.
- **Vision Tasks:** Process and analyze images with [GPT-4 Vision](https://platform.openai.com/docs/guides/vision) models.
- **Audio Processing:** Handle audio tasks with specialized audio preview models.
- **Extended Context:** Process long documents with models supporting up to 128K tokens. See our [Models Guide](https://APIpie.ai/docs/Features/Models).
- **Code Generation:** Leverage models for programming tasks and technical documentation.

---

### **Ethical Considerations**

OpenAI models are powerful tools that require responsible use. Users should implement appropriate safeguards and consider potential biases. For guidance, refer to OpenAI's [Usage Policies](https://openai.com/policies/usage-policies) and [Safety Best Practices](https://platform.openai.com/docs/guides/safety-best-practices).

---

### **Licensing**

OpenAI's models are available under commercial terms through their [API Service Terms](https://openai.com/policies/terms-of-use). For detailed licensing information and usage guidelines, consult the [OpenAI Platform Documentation](https://platform.openai.com/docs) and respective hosting providers.

:::tip
Try out OpenAI models in APIpie's various [supported integrations](https://APIpie.ai/docs/Sandbox/Chat).
:::
