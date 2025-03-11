# Process a document for RAG tuning

## Endpoint: POST /ragtune

[APIpie.ai](https://apipie.ai) provides this endpoint to process a document by extracting its content and generating embeddings to be used for RAG tuning.

Supported file types: **PDF**, **DOC**, **DOCX**, **TXT**, **CSV**, **XLS**, **XLSX**.

For more information on RAG tuning capabilities, visit the [APIpie RAG documentation](https://apipie.ai/docs/Features/Ragtune).

## Request

### Body Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| collection | string | Yes | Name of the RAG tune collection to add the document to |
| url | string | Yes | URL of the document to process |
| metatag | string | No | Optional metadata tag to associate with the document |

### Example Request

```json
{
  "collection": "my-ragtune-collection",
  "url": "https://example.com/mydocument.pdf",
  "metatag": "important-document"
}
```

## Response

### 200 OK

| Property | Type | Description |
|----------|------|-------------|
| message | string | Success message |
| result | object | Additional result information |

### Example Response

```json
{
  "message": "Document added to rag_tuning named: my-ragtune-collection",
  "result": {
    // Additional properties
  }
}
```

### Error Responses

| Status Code | Description |
|-------------|-------------|
| 400 | Collection or URL missing from the request |
| 500 | Internal server error |

For more details on RAG tuning and document processing, see the [APIpie documentation](https://apipie.ai/docs).
