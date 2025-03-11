# List vector collections

## Endpoint: POST /v1/vectors/listcollections

[APIpie.ai](https://apipie.ai) provides this endpoint to return a list of vector collections for the authenticated user. A collection is equivalent to a namespace, this is not a pinecone enterprise "collection".

For more information on vector database capabilities, visit the [APIpie Vector documentation](https://apipie.ai/docs/Features/Pinecone).

## Request

This endpoint requires an empty JSON object in the request body.

### Example Request

```bash
curl -X POST https://api.apipie.ai/v1/vectors/listcollections \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{}'
```

## Response

### 200 OK

Returns an array of strings, where each string is the name of a vector collection.

### Example Response

```json
[
  "my-collection",
  "product-embeddings",
  "document-vectors"
]
```

### Error Responses

| Status Code | Description |
|-------------|-------------|
| 400 | Bad request |
| 500 | Internal server error |

## Notes

- This endpoint lists all vector collections associated with your API key
- Collections are equivalent to namespaces in Pinecone terminology
- This is not the same as a Pinecone enterprise "collection"
- Use this endpoint to discover what collections are available before querying or modifying them
- For more details on vector operations and management, see the [APIpie documentation](https://apipie.ai/docs)
