<div align="center">
    <img src="https://apipie.ai/docs/img/Features/voices-banner.png" alt="Voice Generation Feature Banner" width="100%" />
</div>

Transform text into natural-sounding speech with our enterprise-ready Voice Synthesis API. Perfect for developers, content creators, and businesses looking to add professional voice capabilities to their applications. Our API supports leading AI models from [ElevenLabs](https://elevenlabs.io) and [OpenAI](https://platform.openai.com/docs/guides/text-to-speech), offering 30+ premium voices, multilingual support, and advanced customization options with enterprise-grade reliability.

:::info
For detailed information about using models with APIpie, check out our [Models Overview](https://APIpie.ai/docs/Features/Models) and [Completions Guide](https://APIpie.ai/docs/Features/Completions).
:::

## 🎙️ Voice Synthesis Overview

The Voice Synthesis API allows developers to convert text into high-quality speech using state-of-the-art AI models. The API supports both [ElevenLabs](https://elevenlabs.io) and [OpenAI](https://platform.openai.com/docs/guides/text-to-speech) voice models, providing:

- 30+ premium voices across multiple languages and accents
- Advanced voice customization and style control
- Real-time voice generation with low latency
- Enterprise-grade reliability and scalability
- Comprehensive usage analytics and monitoring
- Secure API access with rate limiting

## 🎯 Model Comparison and Capabilities

### Model Feature Comparison

| Feature | ElevenLabs | OpenAI TTS |
|---------|------------|------------|
| Voice Quality | High fidelity with emotion control | Professional studio quality |
| Language Support | 30+ languages | Primary focus on English |
| Generation Speed | Variable (Flash to Standard) | Consistently fast |
| Customization | Extensive voice settings | Basic voice selection |
| Cost Efficiency | Pay per character | Pay per character |
| Real-time Generation | Yes (with Flash models) | Yes |
| Voice Cloning | Available | Not available |
| Enterprise Support | Yes | Yes |

### ElevenLabs Models

:::info
Visit our [Models Overview](https://APIpie.ai/docs/Features/Models) for the most up-to-date list of supported voice models and their capabilities.
:::

| Model | Description | Max Tokens | Provider |
|-------|-------------|------------|----------|
| eleven_multilingual_v2 | Latest multilingual model with enhanced quality | 5000 | elevenlabs |
| eleven_multilingual_v1 | First generation multilingual model | 5000 | elevenlabs |
| eleven_monolingual_v1 | English-optimized model | 5000 | elevenlabs |
| eleven_turbo_v2 | Fast generation model | 5000 | elevenlabs |
| eleven_turbo_v2_5 | Enhanced turbo model | 5000 | elevenlabs |
| eleven_flash_v2 | Ultra-fast generation | 5000 | elevenlabs |
| eleven_flash_v2_5 | Latest ultra-fast model | 5000 | elevenlabs |

### OpenAI Models

| Model | Description | Provider |
|-------|-------------|----------|
| tts-1-hd | High-definition voice models | openai |
| tts-1-1106 | Standard voice models | openai |

## 🗣️ Available Voices

### Technical Specifications

| Specification | Details |
|--------------|---------|
| Audio Format | MP3, WAV |
| Sample Rate | 16kHz - 48kHz |
| Bit Depth | 16-bit, 24-bit |
| Channels | Mono, Stereo |
| Latency | 200ms - 2000ms |
| Max Input Length | 5000 tokens |
| Rate Limiting | Yes (configurable) |

### ElevenLabs Voices

:::tip
Browse more voices in the [ElevenLabs Voice Library](https://elevenlabs.io/voice-library)
:::

#### Professional Narration
- **Rachel**: Young female, American accent, calm tone - ideal for narration
- **Drew**: Middle-aged male, American accent - perfect for news reading
- **Antoni**: Young male, American accent - well-rounded narrator
- **Thomas**: Young male, American accent - calm meditation voice
- **Bill**: Older male, American accent - trustworthy narration

#### Character Voices
- **Clyde**: Middle-aged male, American accent - war veteran character
- **Dave**: Young male, British-Essex accent - conversational gaming voice
- **Fin**: Older male, Irish accent - sailor character
- **Glinda**: Middle-aged female, American accent - witch character
- **Charlotte**: Young female, Swedish accent - seductive character

#### News & Media
- **Paul**: Middle-aged male, American accent - ground reporter
- **Sarah**: Young female, American accent - soft news voice
- **Daniel**: Middle-aged male, British accent - authoritative news
- **Alice**: Middle-aged female, British accent - confident news
- **Joseph**: Middle-aged male, British accent - field reporter

### OpenAI Voices

#### HD Voices
- **Shimmer**: Clear and expressive
- **Alloy**: Versatile and balanced
- **Echo**: Warm and natural
- **Fable**: Engaging storyteller
- **Onyx**: Deep and authoritative
- **Nova**: Bright and energetic

## 📝 API Parameters and Configuration

:::info
For detailed API documentation and integration guides, visit our [API Reference](https://APIpie.ai/docs/category/api/audio).
:::

### Required Parameters
- **model**: The AI model to use for voice generation
- **voice**: The specific voice to use
- **input**: The text to convert to speech

### Optional Parameters (ElevenLabs)
- **stability** (0-1): Controls voice stability
- **similarity_boost** (0-1): Enhances similarity to the original voice
- **style** (0-1): Adjusts speaking style intensity
- **use_speaker_boost** (boolean): Enhances speaker clarity

## 💡 Example API Calls

### ElevenLabs Example

```bash
curl -X POST 'https://apipie.ai/v1/audio/speech' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer YOUR_API_KEY' \
--data-raw '{
  "model": "eleven_multilingual_v2",
  "voice": "Rachel",
  "input": "Hello! This is a test of the ElevenLabs text to speech API.",
  "voice_settings": {
    "stability": 0.5,
    "similarity_boost": 0.75
  }
}'
```

### OpenAI Example

```bash
curl -X POST 'https://apipie.ai/v1/audio/speech' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer YOUR_API_KEY' \
--data-raw '{
  "model": "tts-1-hd",
  "voice": "shimmer",
  "input": "Hello! This is a test of the OpenAI text to speech API."
}'
```

## 📊 Response Examples

### ElevenLabs Response

```json
{
  "created": 1729535643,
  "audio": {
    "content_type": "audio/mpeg",
    "url": "https://example.com/generated-audio.mp3"
  },
  "usage": {
    "text_characters": 57,
    "cost": 0.004275,
    "latency_ms": 1200
  }
}
```

### OpenAI Response

```json
{
  "created": 1729535643,
  "audio": {
    "content_type": "audio/mpeg",
    "url": "https://example.com/generated-audio.mp3"
  },
  "usage": {
    "text_characters": 52,
    "cost": 0.003500,
    "latency_ms": 800
  }
}
```

## 🎯 Common Use Cases

1. **Content Creation**
   - Audiobook production
   - Podcast generation
   - Video narration
   - E-learning content

2. **Entertainment**
   - Game character voices
   - Animation dubbing
   - Interactive storytelling
   - Voice-enabled NPCs

3. **Business Applications**
   - IVR systems
   - Virtual assistants
   - Customer service
   - Corporate training

4. **Accessibility**
   - Screen readers
   - Text-to-speech for visually impaired
   - Language learning tools
   - Reading assistance

## ⚡ Best Practices

1. **Model Selection**
   - Use multilingual models for multiple language support
   - Use turbo/flash models for faster generation
   - Use HD models for highest quality output

2. **Voice Selection**
   - Choose voices based on use case
   - Consider accent and age appropriate for content
   - Test multiple voices to find the best fit

3. **Text Preparation**
   - Use punctuation to control pacing
   - Break long text into natural segments
   - Include phonetic spelling for unusual words

4. **Performance Optimization**
   - Cache frequently used audio
   - Implement proper error handling
   - Monitor usage and costs

## ⚠️ Error Handling

Common errors and solutions:

```json
{
  "error": {
    "code": "invalid_voice",
    "message": "The specified voice is not available for this model."
  }
}
```
Solution: Verify voice compatibility with chosen model.

```json
{
  "error": {
    "code": "text_too_long",
    "message": "Input text exceeds maximum length for selected model."
  }
}
```
Solution: Break text into smaller segments.

## 🔒 Security and Ethics

- Voice generation requires responsible use
- Implement appropriate content filtering
- Monitor for potential misuse
- Secure API access and authentication
- Respect voice rights and permissions

## 📚 Additional Resources

- [ElevenLabs Documentation](https://docs.elevenlabs.io)
- [OpenAI TTS Documentation](https://platform.openai.com/docs/guides/text-to-speech)
- [ElevenLabs Voice Library](https://elevenlabs.io/voice-library)
- [ElevenLabs Blog](https://elevenlabs.io/blog)
- [OpenAI TTS Examples](https://platform.openai.com/examples?category=speech)
- [Speech Synthesis Technology Overview](https://arxiv.org/abs/2106.15561)
