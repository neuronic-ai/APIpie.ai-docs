
<div align="center">
    <img src="https://apipie.ai/docs/img/Features/models-banner.png" alt="Models Route Feature Banner" width="100%" />
</div>

The Models Route feature allows you to easily fetch and filter AI models available through our API, enabling precise selections based on model types, subtypes, providers, and more. This guide provides details on how to use the Models Route feature effectively for your AI applications.

## Fetching Models

You can retrieve a list of available models or filter them based on specific criteria like type, subtype, and provider. Below is the API endpoint for fetching models:

```bash
GET https://apipie.ai/v1/models
```

### Query Parameters

Here are the parameters you can use to filter the model results:

- **type** (string): Filter by the type of model (e.g., `llm`, `vision`, `embedding`, `image`, `voice`, `moderation`, `coding`, `free`).  
  Example: `llm`
  
- **subtype** (string): Filter by the subtype of the model (e.g., `chat`, `fill-mask`, `question-answering`, `tts`, `stt`, `multimodal`).  
  Example: `chat`
  
- **provider** (string): Filter by the provider of the model (e.g., `openrouter`).  
  Example: `openrouter`
  
- **combination** (string): Combine filters for provider and subtype.  
  Example: `provider=openrouter&subtype=chat`
  
- **enabled** (integer): Filter only enabled models (`1` for enabled, `0` for disabled).  
  Example: `enabled=1&subtype=chat`
  
- **voices**: Retrieve a list of available voices for TTS models.  
  Example: `voices`
  
- **restrictions**: Retrieve a list of country restrictions for models.  
  Example: `restrictions`

### Example API Requests

Below are some example requests using curl:

```bash
curl "https://apipie.ai/v1/models?type=llm"
curl "https://apipie.ai/v1/models?type=vision"
curl "https://apipie.ai/v1/models?type=embedding"
curl "https://apipie.ai/v1/models?type=coding"
curl "https://apipie.ai/v1/models?type=free"
curl "https://apipie.ai/v1/models?type=llm&provider=openai"
curl "https://apipie.ai/v1/models?type=llm&model=gpt-3.5-turbo-0125"
```

### Pool Filtering: Subtype = Pool

You can filter all available pools by setting the `subtype=pool` parameter in your API call. This lists all models grouped into pools.

Example:

```bash
curl "https://apipie.ai/v1/models?subtype=pool"
```

### ChatX Filtering: Subtype = ChatX

The `subtype=chatx` filter allows you to list all models that support streaming and memory services, ensuring a high-quality chat experience. These models are designed for real-time applications that require context retention across queries.

Example:

```bash
curl "https://apipie.ai/v1/models?subtype=chatx"
```

### list voices: ?voices
We will provde a list of all voices available from all our voice providers along with some voice details if available.

```bash
curl -X GET 'https://apipie.ai/v1/models?voices'
{
  "object": "list",
  "data": [
    {
      "provider": "elevenlabs",
      "model": "eleven_multilingual_v2",
      "voice_id": "21m00Tcm4TlvDq8ikWAM",
      "name": "Rachel",
      "description": "description: calm, age: young, gender: female, accent: american, use case: narration"
    },
    {
      "provider": "elevenlabs",
      "model": "eleven_multilingual_v1",
      "voice_id": "21m00Tcm4TlvDq8ikWAM",
      "name": "Rachel",
      "description": "description: calm, age: young, gender: female, accent: american, use case: narration"
    },
    {
      "provider": "elevenlabs",
      "model": "eleven_monolingual_v1"...
```

### list restrictions: ?restrictions
We use this to list all the countries you are allowed to serve this AI to, serving any countries prohibited by any of these restricitons could cause significant consequences from APIpie to the underlyign aggregator and or the model provider themselves banning you and potentially with legal implications, you must not be a relay to work around these restrictions.  If there are any providers not listed here, they are generally opensource and widely available without restriction. 

```bash
curl -X GET 'https://apipie.ai/v1/models?restrictions'
{
  "object": "list",
  "data": [
    {
      "restrict_id": 2,
      "name": "openai",
      "countries": "{\"countries\":[{\"name\":\"Albania\",\"alpha-2\":\"AL\"},{\"name\":\"Algeria\",\"alpha-2\":\"DZ\"},{\"name\":\"Afghanistan\",\"alpha-2\":\"AF\"},{\"name\":\"Andorra\",\"alpha-2\":\"AD\"},{\"name\":\"Angola\",\"alpha-2\":\"AO\"},{\"name\":\"Antigua and Barbuda\",\"alpha-2\":\"AG\"},{\"name\":\"Argentina\",\"alpha-2\":\"AR\"},{\"name\":\"Armenia\",\"alpha-2\":\"AM\"},{\"name\":\"Australia\",...
...
```

## Model Record Structure

Here’s a summary of the fields in each model record, if available:

- `enabled`: Whether the model is currently available (1 = enabled, 0 = disabled).
- `type`: The type of model (e.g., `llm`, `vision`, `embedding`).
- `subtype`: The subtype of the model (e.g., `chat`, `tts`).
- `provider`: The provider of the model (e.g., `openrouter`).
- `route/model`: The API route for the specific model.
- `description`: A description of the model's features and capabilities.
- `max_tokens`: The maximum number of tokens for the model.
- `max_response_tokens`: The maximum number of tokens in the model's response.
- `req_price`: The cost of a token for the model's input. (Some providers dont tell us the price until after the query so we dont track them here)
- `res_price`: The cost of a token for the model's output.
- `price_type`: The type of pricing (e.g., per token, per request).
- `price_unit`: The unit of pricing (e.g., USD).
- `latency`: The latency at various prompt sizes, 2000 char/ 4000 char/ 8000 char/ 16000 char / 32000 char+ / Total average latency per query across all prompt sizes
- `avg_cost`: The average cost of using the model for a request and response (can flcutuate based on usage for models that price input differently than output).
- `query_count`: The number of queries made to the model.
- `available`: Indicates whether the model is available for use.
- `img`: The cost per image when using vision models and uploading images
- `img_json`: The cost per image when generating images, various sizes and qualities are listed in json format
 

## Tips & Tricks

- **Leverage Filters for Precision**: Use the `type`, `subtype`, and `provider` filters together to narrow down the exact models you need for specific tasks. For example, filtering by `subtype=chat` and `provider=openrouter` ensures you only receive chat-based models from OpenRouter.
  
- **Use Pool and ChatX Subtypes**: The `subtype=pool` filter is ideal for querying models grouped into performance or use-case pools, while `subtype=chatx` ensures you're using models optimized for real-time chat applications with streaming and memory capabilities.
  
- **Balance Cost and Capability**: Some models come with higher costs due to their advanced features (e.g., large token limits or memory support). Assess the requirements of your application and choose models that balance performance and cost.
  
- **Use Voice and Restriction Filters**: If you're working with TTS or have specific geographic deployment needs, use `voices` or `restrictions` as query parameters to get more detailed options on voice models or country-specific availability.
  
- **Test Different Providers**: Different providers may offer similar models with varying levels of accuracy, performance, and cost. Experiment with different providers to find the best match for your project.

## FAQs

1. **What is the primary use of the Models Route feature?**
   - The Models Route feature allows users to retrieve and filter available AI models based on type, subtype, provider, and more for targeted AI model integration.

2. **Can I filter models by both type and provider?**
   - Yes, you can combine filters such as `type=llm` and `provider=openai` to get a more refined list of models matching both criteria.

3. **What does the `subtype=chatx` filter do?**
   - The `chatx` subtype lists models that support streaming and memory services, providing a better experience for real-time chat applications.

4. **How can I retrieve available voices for TTS models?**
   - You can use the `voices` query parameter to fetch all available TTS voices. This will list models that support text-to-speech functionalities.

5. **Is the response time affected by the filters used?**
   - Response times are primarily affected by the specific model's latency and availability, rather than the filters applied. However, models with advanced features like memory or high token limits may introduce slightly longer response times.


## Links

- [Fetch Models API Documentation](https://apipie.ai/docs/api/fetchmodels)


## Conclusion

With this guide, you now have a clear understanding of how to use the Models Route feature to fetch and filter AI models effectively. Whether you need to query specific types, providers, or subtypes, our API offers robust capabilities to integrate the right models for your AI-powered projects.

**Note:** Always review the cost implications based on the filters applied, as certain models may incur higher API usage fees due to their enhanced capabilities.

