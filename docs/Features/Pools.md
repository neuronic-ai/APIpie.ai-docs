
<div align="center">
    <img src="https://apipie.ai/docs/img/Features/pooling-banner.png" alt="Pooling Feature Banner" width="100%" />
</div>

Unleash the potential of AI Model Pooling, a breakthrough feature designed to enhance the reliability, redundancy, and data security of AI-generated outputs. This guide delves into the essence of Pools, a service that aggregates multiple similar models to ensure optimal performance and service continuity, especially beneficial for large-scale and sensitive AI applications.

## Why Use AI Model Pooling?

AI Model Pooling offers higher rate limits, reliable redundancy, and improved data security. By spreading requests across multiple providers and similar models in a pool, it ensures consistent response delivery. This method not only enhances reliability but also minimizes the exposure of sensitive data to any single AI provider. AI Model Pooling is particularly useful for applications where high availability and data privacy are crucial.

## Understanding AI Model Pooling Settings

### Pool Structures

- **Model Aggregation:** Each pool contains several similar models that provide higher rate limits and ensure redundancy.
- **Automatic Failover:** If a request fails due to a provider error, the pool will automatically reroute the query to another member until a successful response is obtained.
- **Context Length Value:** The suffix value (e.g., 4k, 8k) indicates the maximum response tokens supported by the models within a pool.

Below is an API example to demonstrate how to leverage model pooling:

```bash
curl -L -X GET 'https://apipie.ai/v1/models?subtype=pool' \
-H 'Authorization: Bearer <YOUR_API_KEY>' \
-H 'Content-Type: application/json' \
{
    "object": "list",
    "data": [
        {
            "type": "llm",
            "subtype": "pool",
            "provider": "pool",
            "model": "gpt-3.5_4k",
            "description": "A pool of like models for higher rate limits, reliable redundancy and improved data security",
            "max_response_tokens": 4096
        }
    ]
}
```
Now we can use any model from that list in a regular chat completions format like this >

```bash
curl -L -X POST 'https://apipie.ai/v1/chat/completions' \
-H 'Content-Type: application/json' \
-H 'Accept: application/json' \
-H 'Authorization: Bearer <TOKEN>' \
--data-raw '{
  "messages": [
    {
      "role": "system",
      "content": "Why is the sky blue?"
    },
  "provider": "pool",
  "model": "gpt4o_16k"
}'
```

This API call showcases how to list the available pools, enabling optimized selection based on your application requirements.

## Benefits of AI Model Pooling for Businesses

Leverage AI Model Pooling for enhanced reliability and data privacy across AI applications. By ensuring a seamless and dependable service, Pools make it possible to maintain service standards even during peak times or unforeseen provider issues.

## How to Set Up AI Model Pooling

To effectively integrate Pools into your AI workflows, follow these steps:

1. **Configure Your API Call:**
   - Change the `provider` to "pool".
   - Use the desired pool name in the `model` field.

2. **Access the Model List:**
   - Use the models route with filter `subtype=pool` to retrieve available pools and their details.

3. **Test and Validate Results:**  
   - Continually monitor outcomes to ensure the pooling mechanism meets your application’s needs.

## Tips & Tricks

- **Optimize Requests:** Use Pools to handle higher request volumes or when you need a response every time, without fail.
- **Greater Privacy:** Distribute data exposure across multiple models and providers.
- **Select Appropriate Pools:** Match pools based on model capabilities and response token limits to your use case needs.

## FAQs

1. **How does Model Pooling enhance reliability?**
   - By rerouting failed requests across multiple similar models on failure, ensuring a consistent response.

2. **Are there any additional costs associated with Pooling?**
   - No, there is no additional cost. Various providers may charge different rates for the same model, but there are no hidden additional fees beyond standard usage rates.

3. **Can I use Model Pooling with any AI application?**
   - While most applications can benefit, it is especially useful where reliability and data security are priorities.

4. **Is there any impact on response time when using Pools?**
   - Failover responses are swift, typically with negligible impact on perceived user latency.

5. **How to verify available Pools?**
   - Utilize the models API endpoint with relevant filters to view current pools.
  
6. **Do pools support streaming?**
   - Yes, all pools support streaming. Note that some Bedrock models may aggregate before streaming. Use the ChatX pools for guaranteed full streaming and memory support.

## Links

- [Chat Completions API](https://apipie.ai/docs/api/chatcompletions)
- [Fetch Models API](https://apipie.ai/docs/api/fetchmodels)
- [Ragtune API](https://apipie.ai/docs/api/ragtune)
- [Vectors API](https://apipie.ai/docs/api/vectors)

## Conclusion

By using AI Model Pooling, you can ensure optimal service reliability and data security in your AI projects. We encourage you to implement Pooling to maximize the benefits and efficiencies of your AI applications. Thank you for choosing Neuronic AI, your trusted AI solutions partner.
