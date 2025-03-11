# Update or insert a vector into a collection

## Endpoint: PUT /v1/vectors/upsert

[APIpie.ai](https://apipie.ai) provides this endpoint to upsert a vector into the specified collection with metadata and data.

For more information on vector database capabilities, visit the [APIpie Vector documentation](https://apipie.ai/docs/Features/Pinecone).

## Request

### Body Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| collectionName | string | Yes | Name of the vector collection to update |
| vectorId | string | Yes | Unique identifier for the vector |
| metatag | string | No | Optional metadata tag to associate with the vector |
| data | string | No | Clear text data associated with the vector |
| embedding | array of numbers | Yes | The vector embedding values |

### Example Request

```json
{
  "collectionName": "my-collection",
  "vectorId": "vector-id-123",
  "metatag": "sampleTag",
  "data": "This is some clear text data associated with the vector",
  "embedding": [0.1, 0.2, 0.3, ...]
}
```

This request should be sent to: `https://api.apipie.ai/v1/vectors/upsert`

## Response

### 200 OK

A successful response indicates that the vector was upserted successfully.

Example Response:

```json
{
  "message": "Vector upserted successfully"
}
```

### Error Responses

| Status Code | Description |
|-------------|-------------|
| 400 | Bad request |
| 404 | Collection not found |
| 500 | Internal server error |

## Notes

- "Upsert" means the vector will be updated if it already exists, or inserted if it doesn't
- The `vectorId` must be unique within the collection
- The `embedding` array should contain the numerical vector representation of the data
- The `data` field typically contains the original text that was embedded
- The `metatag` can be used for categorization or filtering
- The dimension of the embedding must match the dimension of the collection
- For more details on vector operations and management, see the [APIpie documentation](https://apipie.ai/docs)
