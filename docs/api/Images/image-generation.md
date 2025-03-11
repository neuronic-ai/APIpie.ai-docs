# Image Generation

## Endpoint: POST /v1/images/generations

[APIpie.ai](https://apipie.ai) generates images based on the prompt using various image generation models, including OpenAI's DALL-E.

For more information on image generation capabilities, visit the [APIpie documentation](https://apipie.ai/docs).

## Request

### Body Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| prompt | string | Yes | Text description of the desired image(s) |
| model | string | No | The model to use for image generation (e.g., "dall-e-3") |
| n | integer | No | The number of images to generate (currently only supports 1) |
| size | string | No | The size of the generated images (e.g., "1024x1024" is supported by all models) |
| quality | string | No | The quality of the image that will be generated ("standard" or "hd") |
| response_format | string | No | The format in which the generated images are returned ("b64_json" or "url") |
| style | string | No | The style of the generated images ("vivid" or "natural", not applicable to all providers) |
| image | string | No | The URL to an image you want the image model to update (Not supported by Dall-e-3) |

### Example Request

```json
{
  "prompt": "Its a picture of a dog, driving a car",
  "model": "dall-e-3",
  "n": 1,
  "size": "1024x1024",
  "quality": "standard",
  "response_format": "url",
  "style": "vivid"
}
```

## Response

### 200 OK

| Property | Type | Description |
|----------|------|-------------|
| created | integer | UTC timestamp of when the image was created |
| data | array | Array of generated image data |

### Example Response

```json
{
  "created": 1677858242,
  "data": [
    {
      "url": "https://apipie.ai/temp/uniquefilename.jpg",
      "revised_prompt": "A labrador retriever with lush chocolate fur is driving a red 1974 Stingray and..."
    }
  ]
}
```

The `revised_prompt` field, if present, contains the actual prompt that was processed, as some providers automatically enhance the original prompt.

For more details on image generation models and their capabilities, see the [APIpie API documentation](https://apipie.ai/docs).
