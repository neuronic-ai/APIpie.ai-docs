# Delete a collection

## Endpoint: POST /ragtune/deleteCollection

[APIpie.ai](https://apipie.ai) provides this endpoint to delete an entire collection. If you need more fine-grained deletion controls (e.g., deleting specific records), use the [`/vectors` endpoint](https://apipie.ai/docs/api/vectors).

For more information on RAG tuning capabilities, visit the [APIpie RAG documentation](https://apipie.ai/docs/Features/Ragtune).

## Request

### Body Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| collection | string | Yes* | Name of the RAG tune collection to delete |
| collectionName | string | Yes* | Alternative name parameter for the collection |
| deleteAll | boolean | No | Whether to delete all vectors in the collection |
| ids | array of strings | No | Specific vector IDs to delete |
| filter | object | No | Filter criteria for vectors to delete |

*Either `collection` or `collectionName` must be provided.

### Example Request - Delete Entire Collection

```json
{
  "collection": "my-ragtune-collection"
}
```

### Example Request - Delete Specific Vectors

```json
{
  "collection": "my-ragtune-collection",
  "ids": ["id1", "id2"]
}
```

### Example Request - Delete Vectors by Filter

```json
{
  "collection": "my-ragtune-collection",
  "filter": {
    "key": "value"
  }
}
```

## Response

### 200 OK

| Property | Type | Description |
|----------|------|-------------|
| message | string | Success message |

### Example Response

```json
{
  "message": "Collection or vectors deleted successfully"
}
```

### Error Responses

| Status Code | Description |
|-------------|-------------|
| 400 | Collection name missing from the request |
| 500 | Internal server error |

For more details on RAG tuning and collection management, see the [APIpie documentation](https://apipie.ai/docs).
