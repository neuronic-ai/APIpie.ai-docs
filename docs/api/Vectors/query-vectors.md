# Query vectors in a collection

## Endpoint: POST /v1/vectors/query

[APIpie.ai](https://apipie.ai) provides this endpoint to query the vectors in the specified collection based on input criteria.

For more information on vector database capabilities, visit the [APIpie Vector documentation](https://apipie.ai/docs/Features/Pinecone).

## Request

### Body Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| collectionName | string | Yes | Name of the vector collection to query |
| vector | array of numbers | Yes | The query vector to find similar vectors for |
| topK | integer | No | Number of most similar vectors to return |
| includeValues | boolean | No | Whether to include the vector values in the response |
| includeMetadata | boolean | No | Whether to include metadata in the response |
| filter | object | No | Filter criteria for the query |
| metatag | string | No | Filter by specific metatag |

### Example Request

```json
{
  "collectionName": "my-collection",
  "vector": [0.1, 0.2, 0.3, ...],
  "topK": 10,
  "includeValues": true,
  "includeMetadata": false,
  "filter": {
    "key": "value"
  },
  "metatag": "tag123"
}
```

This request should be sent to: `https://api.apipie.ai/v1/vectors/query`

## Response

### 200 OK

The response includes the query results with the most similar vectors to the query vector.

Example Response:

```json
{
  "matches": [
    {
      "id": "vector-id-1",
      "score": 0.95,
      "values": [0.1, 0.2, 0.3, ...],
      "metadata": {
        "key": "value"
      }
    },
    {
      "id": "vector-id-2",
      "score": 0.87,
      "values": [0.2, 0.3, 0.4, ...],
      "metadata": {
        "key": "value"
      }
    }
  ]
}
```

### Error Responses

| Status Code | Description |
|-------------|-------------|
| 400 | Bad request |
| 404 | Collection not found |
| 500 | Internal server error |

## Notes

- The `vector` parameter should be an array of numbers representing the embedding you want to find similar vectors for
- The `topK` parameter determines how many similar vectors to return (default is usually 10)
- Set `includeValues` to true if you need the actual vector values in the response
- Set `includeMetadata` to true if you need the metadata associated with each vector
- The `filter` parameter allows you to narrow down the search based on metadata fields
- The `metatag` parameter is a shorthand for filtering by a specific tag
- The response includes a similarity score for each match, with higher scores indicating greater similarity
- For more details on vector operations and semantic search, see the [APIpie documentation](https://apipie.ai/docs)
