
<div align="center">
    <img src="https://apipie.ai/docs/img/Features/IMM.png" alt="Integrated Model Memory (IMM) - Advanced AI Memory Management System" width="100%" />
</div>

# Integrated Model Memory (IMM)

## Overview

Integrated Model Memory (IMM) is our implementation of [Cache Augmented Generation (CAG)](https://github.com/hhhuang/CAG), designed to revolutionize how AI applications handle conversation context. Unlike traditional CAG systems that are typically tied to specific models, IMM provides a model-independent memory solution that works seamlessly across [all supported AI models](https://APIpie.ai/docs/Models/Overview.md). This means your conversation history and context persist within a session regardless of which model you use - you can start a conversation with [GPT-4](https://platform.openai.com/docs/models/gpt-4), continue with [Claude](https://docs.anthropic.com/claude/docs), and switch to [Mistral](https://docs.mistral.ai/) while maintaining complete context. This unique approach eliminates the complexity of manual memory management while providing intelligent context retention across conversations.

As our enhanced implementation of CAG, IMM simplifies AI development by automating critical memory-related tasks:
- Automatic context management
- Seamless conversation history tracking
- Intelligent memory expiration handling
- Multi-session support for different users or use cases

## Key Features and Benefits

### Effortless Implementation
- Enable memory with a simple `"memory": 1` parameter
- No need for complex vector database management
- Automatic context retention and retrieval

### Advanced Session Management
- Create independent memory instances with `mem_session`
- Perfect for multi-user applications
- Isolated conversation contexts for different use cases

### Smart Memory Controls
- Configure memory expiration with `mem_expire`
- Automatic cleanup of outdated conversations
- Efficient resource management

### Developer-Friendly Design
- Simple API integration
- Flexible configuration options
- Model-independent memory management
- Persistent session memory across different models
- Intelligent caching and retrieval mechanisms

---
## Implementation Guide

### Enabling Memory Management

Activate IMM by including the memory parameter in your API request:

```bash {6-8}
curl https://apipie.ai/v1/chat/completions \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer <Your APIpie API Key>" \
  -data-raw '{
  "stream": true,       
  "memory": 1,            
  "mem_expire": 120,      
  "mem_session": "test123", 
  "provider": "openai",
  "model": "gpt-4o",
  "max_tokens": 100,
  "messages": [
    {
      "role": "user",
      "content": "where did I put my car keys? I already forgot."
    }
  ]
}'
```

### Verifying Memory Functionality

To see Integrated Model Memory in action, follow this sequence:

#### Step 1: Save Information to Memory

```bash {5-7}
curl -X POST "https://apipie.ai/v1/chat/completions" \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer <Your APIpie API Key>" \
  --data-raw '{
    "memory": 1,           
    "mem_expire": 60,      
    "mem_session": "test123", 
    "provider": "openai",
    "model": "gpt-4o",
    "max_tokens": 100,
    "messages": [
      { 
        "role": "user",
        "content": "I put my car keys in the coffee can by the swing on the front porch."
      },
      { 
        "role": "assistant",
        "content": "Okay, I will keep your secret safe."
      },
      { 
        "role": "user",
        "content": "Why is the sky blue?"
      },
      { 
        "role": "assistant",
        "content": "The sky appears blue due to a phenomenon called Rayleigh scattering..."
      },
      { 
        "role": "user",
        "content": "What did I just ask you?"
      }
    ]
  }'
```

#### Step 2: Ask a Follow-up Question

Now, ask the AI where you put your car keys and note how you do not need to include the message history:

```bash {5-6}
curl -X POST "https://apipie.ai/v1/chat/completions" \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer <Your APIpie API Key>" \
  --data-raw '{
    "memory": 1,           
    "mem_session": "cross_model_test", 
    "provider": "openai",
    "model": "gpt-4o",
    "max_tokens": 50,
    "messages": [
      { 
        "role": "user",
        "content": "Where did I put my car keys?"
      }
    ]
  }'
```

#### Expected Response

```json
{
  "id": "chatcmpl-6008a7442651dc5b433b58db12fa88ee",
  "object": "chat.completion",
  "created": 1737469664,
  "provider": "openai",
  "model": "gpt-4o",
  "choices": [
    {
      "index": 0,
      "message": {
        "role": "assistant",
        "content": "You put your car keys in the coffee can by the swing on the front porch."
      },
      "logprobs": null,
      "finish_reason": "stop"
    }
  ]
}
```

This confirms that the AI correctly remembers past conversations and can recall stored information.

### Cross-Model Memory Example

One of IMM's unique features is its ability to maintain context across different AI models within the same session. Here's how to switch models while preserving conversation context:
# Start with GPT-4
```bash {7-8}
curl -X POST "https://apipie.ai/v1/chat/completions" \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer <Your APIpie API Key>" \
  --data-raw '{
    "memory": 1,
    "mem_session": "cross_model_test", 
    "provider": "openai",  
    "model": "gpt-4o",     
    "messages": [
      { 
        "role": "user",
        "content": "My favorite color is blue."
      }
    ]
  }'
```

# Continue with Claude, maintaining context
```bash {7-8}
curl -X POST "https://apipie.ai/v1/chat/completions" \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer <Your APIpie API Key>" \
  --data-raw '{
    "memory": 1,
    "mem_session": "cross_model_test",
    "provider": "anthropic",
    "model": "claude-2",
    "messages": [
      { 
        "role": "user",
        "content": "What's my favorite color?"
      }
    ]
  }'
```
# Switch to Mistral, still maintaining context
```bash {7-8}
curl -X POST "https://apipie.ai/v1/chat/completions" \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer <Your APIpie API Key>" \
  --data-raw '{
    "memory": 1,
    "mem_session": "cross_model_test",
    "provider": "mistral",
    "model": "mistral-large",
    "messages": [
      { 
        "role": "user",
        "content": "Can you confirm my favorite color?"
      }
    ]
  }'
```

Each model will have access to the full conversation history, demonstrating IMM's unique ability to maintain context across different AI models.

---
### Managing Multiple Sessions

Create separate memory contexts for different users or applications, separate the sessions by differentiating the mem_session string.

```bash {7}
curl -X POST "https://apipie.ai/v1/chat/completions" \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer <Your APIpie API Key>" \
  --data-raw '{
    "memory": 1,           
    "mem_expire": 60,      
    "mem_session": "user456", 
    "provider": "openai",
    "model": "gpt-4o",
    "max_tokens": 100,
    "messages": [
      { 
        "role": "user",
        "content": "donde esta la bibliteca?"
      }
    ]
  }'
```

### Memory Expiration Control

Set custom expiration times for conversation contexts to a maximum 1440 min with a default of 15:

```bash {6}
curl -X POST "https://apipie.ai/v1/chat/completions" \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer <Your APIpie API Key>" \
  --data-raw '{
    "memory": 1,           
    "mem_expire": 120,      
    "mem_session": "timed_session",
    "provider": "openai",
    "model": "gpt-4o",
    "messages": [
      { 
        "role": "user",
        "content": "This conversation will expire in 120 minutes."
      }
    ]
  }'
```

### Clearing Memory

Clear specific session memory when needed, If you do not specify a session the default unnammed session will be cleared:

```bash {6}
curl -X POST "https://apipie.ai/v1/chat/completions" \
-H "Content-Type: application/json" \
-H "Authorization: Bearer <Your APIpie API Key>" \
--data-raw '{
"memory": 1,           
"mem_clear": 1,        
"mem_session": "session_to_clear",  
"provider": "openai",
"model": "gpt-4o",
"messages": [
{
"role": "user",
"content": "Clear this session's memory."
}
]
}'
```

Expected response:

```json
{
  "queryResults": "Memory session deleted successfully",
  "queryDetails": {
    "provider": "openai",
    "route": "gpt-4o",
    "promptTokens": 0,
    "responseTokens": 0,
    "promptChar": 0,
    "responseChar": 31,
    "cost": 0,
    "latencyMs": 0
  }
}
```

## Performance Considerations

### System Impact
- Minimal latency increase for enhanced context awareness
- Efficient memory management through [Pinecone integration](https://APIpie.ai/docs/Features/Pinecone.md) (powered by [Pinecone's vector database](https://docs.pinecone.io/docs/overview))
- Optimized resource utilization

### Best Practices
- Use unique session IDs for different conversation contexts
- Implement appropriate memory expiration times
- Monitor and manage active sessions

### Resource Management
- Automatic cleanup of expired sessions
- Efficient handling of memory resources
- Cost-effective implementation

---

## Advanced Features

### Memory Optimization
- Automatic context prioritization
- Intelligent memory cleanup
- Resource-efficient storage

### Session Control
- Fine-grained session management
- Custom expiration settings
- Independent memory contexts

### Integration Support
- Compatible with [all supported AI models](https://APIpie.ai/docs/Models/Overview.md)
- Seamless API integration
- Flexible implementation options

By implementing Integrated Model Memory, developers can create more intelligent, context-aware AI applications while maintaining efficient resource usage and optimal performance. Learn more about enhancing your AI applications with our [Completions API](https://APIpie.ai/docs/Features/Completions.md) and [RAG tuning capabilities](https://APIpie.ai/docs/Features/Ragtune.md).

## Additional Resources

- [Vector Similarity Search Fundamentals](https://www.pinecone.io/learn/vector-similarity/) - Pinecone's guide to vector search
- [Anthropic's prompt caching](hhttps://docs.anthropic.com/en/docs/build-with-claude/prompt-caching) 
- [OpenAI's prompt caching](https://platform.openai.com/docs/guides/prompt-caching)

---
