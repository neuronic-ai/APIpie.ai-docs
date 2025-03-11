<div align="center">
    <img src="https://apipie.ai/docs/img/Features/usage-banner.png" alt="Historic Usage Feature Banner" width="100%" />
</div>

Apipie provides an advanced **Historic Usage** feature that allows users to fetch detailed information on their past API queries. This level of transparency and user awareness is unmatched, as to our knowledge, no other provider offers this level of historic usage data available via API. 

With the Historic Usage API, developers can access comprehensive logs of past queries, including crucial details like the provider used, latency, token count, costs, and even the source IP address. This guide outlines the available API route, the parameters for making requests, and provides detailed explanations for each field in the response. The transparency provided by Apipie enables you to manage your usage and costs efficiently.

## Fetching Query History

You can fetch the history of queries sorted by timestamp in descending order using the following API route:

```bash
GET https://apipie.ai/v1/queries/
```

### Query Parameters

- **limit** (optional): Limits the number of returned queries per page.  
  Example: `limit=100`
  
- **offset** (optional): Offset used for pagination.  
  Example: `offset=0`

### Example API Call

Here is an example of how to fetch the last 20 queries:

```bash
curl -L -X GET 'https://apipie.ai/v1/queries/?limit=20&offset=0' \
-H 'Accept: application/json' \
-H 'Authorization: Bearer <YOUR_API_KEY>'
```

## Response Structure

The response is a JSON object with a list of query records, each containing detailed information. Here is an example of the response structure:

```json
{
  "items": [
    {
      "id": 158939,
      "username": "kilroy",
      "timestamp": "2024-10-21T19:09:39.000Z",
      "app": "imageai",
      "provider": "openai",
      "route": "dall-e-3",
      "unit": "image",
      "prompt_tokens": 78,
      "prompt_char": 367,
      "response_tokens": 0,
      "response_char": 0,
      "cost": "0.0800000000",
      "latency_ms": 15587,
      "source_ip": "49.130.235.231",
      "chat_id": null
    }
    ...
  ],
  "limit": 20,
  "offset": 0
}
```

### Explanation of Fields

1. **id**:  
   The internal ID of the query. This is a unique identifier for each query. Example: `158939`

2. **username**:  
   The name of the user who made the request. This will typically be the username associated with the API key used. Example: `kilroy`

3. **timestamp**:  
   The exact time the query was made, in ISO format. This helps to track when the request was sent and completed. Example: `2024-10-21T19:09:39.000Z`

4. **app**:  
   The name of the application or API key that initiated the query. Example: `imageai`

5. **provider**:  
   The AI service provider used for the query. This could be OpenAI, Together, or any other provider supported by Apipie. Example: `openai`

6. **route**:  
   The unique identifier of the AI model used within the provider. This typically refers to the model's route, such as `gpt-4o`, `dall-e-3`, or `llama-2-13b-chat`. Example: `dall-e-3`

7. **unit**:  
   The unit used for cost calculations. Depending on the query type, this could be `character` or `token` for text-based queries or `image` for image generation. Example: `image`

8. **prompt_tokens**:  
   The number of tokens used in the input prompt. This is applicable for language model-based queries. Example: `78`

9. **prompt_char**:  
   The number of characters in the input prompt. This is useful for assessing the size of the input in text-based queries. Example: `367`

10. **response_tokens**:  
    The number of tokens generated in the response. This is relevant for text-based responses, but may be `0` for queries like image generation. Example: `0`

11. **response_char**:  
    The number of characters in the response. Like `response_tokens`, this is typically used for text-based responses. Example: `0`

12. **cost**:  
    The total cost of the query, represented as a decimal value with up to 12 decimal places. Example: `0.0800000000`

13. **latency_ms**:  
    The total latency for the query in milliseconds. This indicates how long it took for the request to be processed. Example: `15587`

14. **source_ip**:  
    The source IP addresses from which the request originated. This field provides transparency about where the request came from and is particularly useful for tracking or auditing. Example: `49.130.235.231`

15. **chat_id**:  
    For chat-based queries, this field contains the unique identifier of the conversation or chat session as provided from the underlying provider. We keep this to track abuse. This field may be `null` for non-chat queries. Example: `null`

16. **limit**:  
    The `limit` parameter that was applied to the request, indicating how many records were returned in this API call. Example: `20`

17. **offset**:  
    The `offset` parameter that was applied to the request, indicating the starting point of the query history returned. Example: `0`, you could use `100`to start at 100 records prior.


## Using Historic Usage for Cost and Performance Analysis

By leveraging the detailed data returned from the Historic Usage API, you can track:

- **Cost Management**: Use the `cost` field to analyze and manage your API expenses. By understanding how much each query costs, you can optimize your API usage and adjust for budgetary constraints.
  
- **Latency Insights**: Analyze the `latency_ms` field to monitor performance across various queries. If certain queries consistently show high latency, you may want to adjust your AI model or routing settings.

- **Token Utilization**: With the `prompt_tokens` and `response_tokens` fields, you can track how token-heavy your requests and responses are. This can help you reduce token usage where necessary.

- **Security and Auditing**: The `source_ip` field provides transparency for auditing purposes, allowing you to see where each query originated.

## Conclusion

The **Historic Usage** feature of Apipie stands out by offering an unprecedented level of transparency. With detailed records of each query, users have full visibility into their API usage, allowing for better cost management, performance monitoring, and security auditing. Explore this feature today to gain more control over your API interactions.
