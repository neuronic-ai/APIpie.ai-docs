# List collections for RAG tuning

## Endpoint: POST /ragtune/listCollections

[APIpie.ai](https://apipie.ai) provides this endpoint to return a list of collections associated with the user identified by the API key.

For more granular control or to implement your own RAG solution, refer to our [`/vectors` route](https://apipie.ai/docs/api/vectors).

For more information on RAG tuning capabilities, visit the [APIpie RAG documentation](https://apipie.ai/docs/Features/Ragtune).

## Request

This endpoint doesn't require any parameters in the request body.

### Example Request

```bash
curl -X POST https://api.apipie.ai/ragtune/listCollections \
  -H "Authorization: Bearer YOUR_API_KEY"
```

## Response

### 200 OK

Returns an array of collection objects.

| Property | Type | Description |
|----------|------|-------------|
| collection | string | Name of the RAG tune collection |

### Example Response

```json
[
  {
    "collection": "my-ragtune-collection"
  },
  {
    "collection": "another-collection"
  },
  {
    "collection": "documentation-collection"
  }
]
```

### Error Responses

| Status Code | Description |
|-------------|-------------|
| 500 | Internal server error |

For more details on RAG tuning and collection management, see the [APIpie documentation](https://apipie.ai/docs).
