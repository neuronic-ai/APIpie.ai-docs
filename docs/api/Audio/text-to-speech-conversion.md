# Text to Speech Conversion

## Endpoint: POST /v1/audio/speech

[APIpie.ai](https://apipie.ai) provides this endpoint to convert text to speech using the specified model and voice settings.

For more information on audio capabilities, visit the [APIpie Voice documentation](https://apipie.ai/docs/Features/Voices).

## Request

### Body Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| provider | string | Yes | Name of the audio provider (e.g., "openai", "elevenlabs") |
| model | string | Yes | Model identifier for the speech synthesis |
| input | string | Yes | Text input to be converted into speech |
| voice | string | Yes | Voice setting for the speech synthesis |
| voiceSettings | object | No | Additional settings for voice modulation |
| responseFormat | string | No | The audio format of the response (e.g., mp3, opus) |
| speed | number | No | Speed of the speech playback (0.25-4.0) |
| stream | boolean | No | Whether to stream the response |

#### Voice Settings Object

| Parameter | Type | Description |
|-----------|------|-------------|
| stability | integer | Stability of the voice modulation (0-1) |
| similarity_boost | integer | Boost the similarity of the voice modulation (0-1) |
| style | integer | Style of the voice modulation (0-1) |
| use_speaker_boost | boolean | Whether to use speaker boost |

### Example Request - OpenAI

```json
{
  "provider": "openai",
  "model": "tts-1-hd",
  "input": "why is the sky blue?",
  "voice": "alloy",
  "responseFormat": "mp3",
  "speed": 1,
  "stream": true
}
```

This request should be sent to: `https://api.apipie.ai/v1/audio/speech`

### Example Request - ElevenLabs

```json
{
  "provider": "elevenlabs",
  "model": "Eleven_Turbo_v2",
  "input": "why is the sky blue?",
  "voice": "21m00Tcm4TIvDq8ikWAM",
  "voiceSettings": {
    "stability": 0.42,
    "similarity_boost": 0.68,
    "style": 0,
    "use_speaker_boost": true
  },
  "stream": true
}
```

## Response

### 200 OK

The response is the audio file or stream in the requested format. Additional usage details are provided in the 'X-Audio-Details' header.

#### Headers

| Header | Description |
|--------|-------------|
| X-Audio-Details | Provides metadata about the audio request, such as provider, route, model, cost, and latency |

Example X-Audio-Details header:
```
{
  "provider": "elevenlabs",
  "route": "eleven_multilingual_v2",
  "model": "eleven_multilingual_v2",
  "voice": "21m00Tcm4TlvDq8ikWAM",
  "promptChar": 20,
  "cost": 0.0042,
  "latencyMs": 1006
}
```

### Error Responses

| Status Code | Description |
|-------------|-------------|
| 400 | Invalid request parameters |

## Notes

- To get a complete list of available voices, query `https://api.apipie.ai/v1/models?voices`
- The response format defaults to mp3 for OpenAI if not specified
- When streaming is enabled, the audio is returned as a stream of chunks
- The X-Audio-Details header provides useful information about the request, including cost and latency
- Different providers may support different voice settings and parameters
- For more details on audio capabilities and voice options, see the [APIpie documentation](https://apipie.ai/docs)
