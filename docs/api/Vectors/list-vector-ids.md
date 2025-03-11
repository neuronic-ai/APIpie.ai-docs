# List vector IDs in a collection

## Endpoint: POST /v1/vectors/list

[APIpie.ai](https://apipie.ai) provides this endpoint to retrieve a list of vector IDs for the specified collection.

For more information on vector database capabilities, visit the [APIpie Vector documentation](https://apipie.ai/docs/Features/Pinecone).

## Request

### Body Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| collectionName | string | Yes | Name of the vector collection to list IDs from |
| limit | integer | No | Maximum number of vector IDs to return |
| prefix | string | No | Filter vector IDs by prefix |
| paginationToken | string | No | Token for pagination to get the next set of results |

### Example Request

```json
{
  "collectionName": "my-collection",
  "limit": 100,
  "prefix": "prefix",
  "paginationToken": "token123"
}
```

This request should be sent to: `https://api.apipie.ai/v1/vectors/list`

## Response

### 200 OK

| Property | Type | Description |
|----------|------|-------------|
| vectorIds | array of strings | List of vector IDs in the collection |
| nextPaginationToken | string | Token to use for retrieving the next set of results |

### Example Response

```json
{
  "vectorIds": ["id1", "id2", "id3", "id4", "id5"],
  "nextPaginationToken": "next-token-123"
}
```

### Error Responses

| Status Code | Description |
|-------------|-------------|
| 400 | Bad request |
| 404 | Collection not found |
| 500 | Internal server error |

## Notes

- Use the `limit` parameter to control how many IDs are returned in a single request
- The `prefix` parameter can be used to filter IDs that start with a specific string
- If there are more results than the specified limit, a `nextPaginationToken` will be provided
- To retrieve the next set of results, include the `nextPaginationToken` in your next request
- If `nextPaginationToken` is not returned, it means there are no more results to retrieve
- For more details on vector operations and management, see the [APIpie documentation](https://apipie.ai/docs)
