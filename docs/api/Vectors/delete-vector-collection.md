# Delete a vector collection or specific vectors

## Endpoint: POST /v1/vectors/delete

[APIpie.ai](https://apipie.ai) provides this endpoint to delete the entire collection or specified vector IDs from the collection.

For more information on vector database capabilities, visit the [APIpie Vector documentation](https://apipie.ai/docs/Features/Pinecone).

## Request

### Body Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| collection | string | Yes* | Name of the vector collection to delete |
| collectionName | string | Yes* | Alternative name parameter for the collection |
| deleteAll | boolean | No | Whether to delete all vectors in the collection |
| ids | array of strings | No | Specific vector IDs to delete |
| filter | object | No | Filter criteria for vectors to delete |

*Either `collection` or `collectionName` must be provided.

### Example Request - Delete Entire Collection

```json
{
  "collection": "my-collection",
  "deleteAll": true
}
```

### Example Request - Delete Specific Vectors

```json
{
  "collection": "my-collection",
  "ids": ["id1", "id2"]
}
```

### Example Request - Delete Vectors by Filter

```json
{
  "collection": "my-collection",
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
| 400 | Bad request |
| 404 | Collection not found |
| 500 | Internal server error |

## Notes

- To delete an entire collection, set `deleteAll` to `true`
- To delete specific vectors, provide their IDs in the `ids` array
- To delete vectors matching certain criteria, use the `filter` object
- Be cautious when using `deleteAll` as it will permanently remove all vectors in the collection
- For more details on vector operations and management, see the [APIpie documentation](https://apipie.ai/docs)
