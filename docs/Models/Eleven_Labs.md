<div align="center">
<img src="https://apipie.ai/docs/img/Models/ElevenLabs.png" alt="ElevenLabs Models" width="100%" />
</div>

:::info
For detailed information about using models with APIpie, check out our [Models Overview](https://APIpie.ai/docs/Features/Models) and [Completions Guide](https://APIpie.ai/docs/Features/Completions).
:::

### **Description**

[ElevenLabs](https://elevenlabs.io) is a leading provider of state-of-the-art text-to-speech technology. Their advanced AI models offer natural-sounding voice synthesis with unprecedented quality and control. The platform supports multiple languages and can generate highly realistic speech with various voices, accents, and emotional tones.

Learn more about ElevenLabs:
- [Official Documentation](https://docs.elevenlabs.io)
- [Voice Library](https://elevenlabs.io/voice-library)
- [Speech Synthesis Blog](https://elevenlabs.io/blog)
- [Discord Community](https://discord.gg/elevenlabs)
- [GitHub Resources](https://github.com/elevenlabs)

### **Technology Overview**

ElevenLabs utilizes cutting-edge deep learning techniques to create natural-sounding synthetic voices. Their technology incorporates:
- Neural voice cloning
- Multilingual speech synthesis
- Real-time voice generation
- Emotion and style control
- High-fidelity audio output

### **Available Models**

| Model                  | Max Tokens | Provider   | Type  | Description |
|-----------------------|------------|------------|-------|-------------|
| eleven_multilingual_v2 | 5000       | elevenlabs | tts   | Latest multilingual model with enhanced quality |
| eleven_multilingual_v1 | 5000       | elevenlabs | tts   | First generation multilingual model |
| eleven_monolingual_v1  | 5000       | elevenlabs | tts   | English-optimized model |
| eleven_turbo_v2       | 5000       | elevenlabs | tts   | Fast generation model |
| eleven_turbo_v2_5     | 5000       | elevenlabs | tts   | Enhanced turbo model |
| eleven_flash_v2       | 5000       | elevenlabs | tts   | Ultra-fast generation |
| eleven_flash_v2_5     | 5000       | elevenlabs | tts   | Latest ultra-fast model |

### **Available Voices**

ElevenLabs provides a diverse set of pre-made voices with different characteristics:

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

#### Social Media & Casual
- **Laura**: Young female, American accent - upbeat social media
- **Will**: Young female, American accent - friendly social
- **Jessica**: Young female, American accent - expressive conversational
- **Eric**: Middle-aged male, American accent - friendly conversational
- **Chris**: Middle-aged male, American accent - casual style

#### Special Purpose
- **Ethan**: Young male, American accent - ASMR/whisper
- **Nicole**: Young female, American accent - audiobook whisper
- **Dorothy**: Young female, British accent - children's stories
- **Michael**: Older male, American accent - audiobook narration
- **Grace**: Young female, American Southern accent - gentle audiobook

#### Multilingual
- **Giovanni**: Young male, Italian-English accent - foreign audiobook
- **Mimi**: Young female, Swedish-English accent - animation
- **Charlie**: Middle-aged male, Australian accent - conversational
- **James**: Older male, Australian accent - news
- **George**: Middle-aged male, British accent - warm narration

### Example API Call

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

### Response Example

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

### **Voice Settings and Controls**

You can customize the voice output using these parameters:

- **stability** (0-1): Controls voice stability. Higher values make the voice more consistent but less expressive
- **similarity_boost** (0-1): Enhances similarity to the original voice. Higher values make it sound more like the reference
- **style** (0-1): Adjusts speaking style intensity
- **use_speaker_boost** (boolean): Enhances speaker clarity

### **Integration and Use Cases**

ElevenLabs' text-to-speech technology can be integrated into various applications:

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

### **Best Practices and Optimization**

1. **Model Selection**:
   - Use multilingual_v2 for highest quality across languages
   - Use turbo or flash models for faster generation
   - Use monolingual for English-only applications

2. **Voice Selection**:
   - Choose voices based on use case (narration, characters, news, etc.)
   - Consider accent and age appropriate for your content
   - Test multiple voices to find the best fit

3. **Text Preparation**:
   - Use punctuation to control pacing
   - Break long text into natural segments
   - Include phonetic spelling for unusual words

### **Performance and Limitations**

- Maximum text length varies by subscription
- Some voices may have accent or language restrictions
- Generation time varies by model and text length

### **Security and Ethics**

ElevenLabs maintains strict guidelines for voice usage:
- Voice cloning requires explicit consent
- Built-in content filtering
- Usage monitoring and abuse prevention
- Secure API access and authentication

### **Resources and Support**

Get help and learn more:
- [ElevenLabs Status Page](https://status.elevenlabs.io)
- [API Reference](https://api.elevenlabs.io/docs)
- [Speech Synthesis Guide](https://docs.elevenlabs.io/speech-synthesis)
- [Voice Design Guide](https://docs.elevenlabs.io/voice-design)

:::tip
Try out ElevenLabs voices in APIpie's [supported integrations](https://APIpie.ai/docs/Sandbox/Chat)
:::
