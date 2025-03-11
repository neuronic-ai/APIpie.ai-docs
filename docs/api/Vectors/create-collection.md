# Create a new vector collection

## Endpoint: POST /v1/vectors

[APIpie.ai](https://apipie.ai) provides this endpoint to create a new vector collection with the specified name and dimension. (equivalent to creating an index and namespace on pinecone)

For more information on vector database capabilities, visit the [APIpie Vector documentation](https://apipie.ai/docs/Features/Pinecone).

## Request

### Body Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| collectionName | string | Yes | Name of the vector collection to create |
| dimension | integer | Yes | Dimension of the vectors to be stored in the collection |

### Example Request

```json
{
  "collectionName": "my-collection",
  "dimension": 512
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
  "message": "Vector collection created successfully"
}
```

### Error Responses

| Status Code | Description |
|-------------|-------------|
| 400 | Bad request |
| 404 | Collection not found |
| 500 | Internal server error |

## Notes

- Vector collections are used for storing and managing embeddings
- Essential for building semantic search and AI-powered retrieval systems
- The dimension parameter should match the dimension of the embeddings you plan to store
- Common embedding dimensions include 384, 512, 768, 1024, and 1536, depending on the model used
- For more details on vector operations and capabilities, see the [APIpie documentation](https://apipie.ai/docs)
