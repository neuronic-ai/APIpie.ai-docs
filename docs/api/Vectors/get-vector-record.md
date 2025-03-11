# Get a specific record in a vector collection

## Endpoint: GET /v1/vectors/fetch

[APIpie.ai](https://apipie.ai) provides this endpoint to fetch the content of a specific record in the vector collection by ID.

For more information on vector database capabilities, visit the [APIpie Vector documentation](https://apipie.ai/docs/Features/Pinecone).

## Request

### Query Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| collectionName | string | Yes | Name of the vector collection to fetch from |
| ids | string | Yes | ID of the vector record to retrieve |

### Example Request

```
GET https://api.apipie.ai/v1/vectors/fetch?collectionName=my-collection&ids=vector-id-123
```

## Response

### 200 OK

| Property | Type | Description |
|----------|------|-------------|
| vector | object | Object containing the vector record data |

#### Vector Object Properties

| Property | Type | Description |
|----------|------|-------------|
| id | string | Unique identifier of the vector |
| embedding | array of numbers | The vector embedding values |
| metatag | string | Optional metadata tag associated with the vector |
| data | string | Clear text data associated with the vector |

### Example Response

```json
{
  "vector": {
    "id": "vector-id-123",
    "embedding": [0.1, 0.2, 0.3, ...],
    "metatag": "sampleTag",
    "data": "This is some clear text data associated with the vector"
  }
}
```

### Error Responses

| Status Code | Description |
|-------------|-------------|
| 400 | Bad request |
| 404 | Record or collection not found |
| 500 | Internal server error |

## Notes

- The `embedding` array contains the numerical vector representation of the data
- The `data` field typically contains the original text that was embedded
- The `metatag` can be used for categorization or filtering
- For more details on vector operations and retrieval, see the [APIpie documentation](https://apipie.ai/docs)
