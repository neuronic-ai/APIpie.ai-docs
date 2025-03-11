<div align="center">
    <img src="https://apipie.ai/docs/img/Features/pinecone-banner.png" alt="Pinecone Integration Banner" width="100%" />
</div>

Our Pinecone integration provides advanced control for users who want to manage their vector database directly. Unlike traditional RAG Tuning, which abstracts much of the complexity, the Pinecone integration allows for full control over the RAG process, including indexing and querying vectors with your own configurations.

## Why Use Pinecone Integration?

Pinecone Integration gives businesses the ability to:
- **Control Vector Storage**: Manage and query your vectors directly with flexible indexing and namespace options.
- **Full RAG Process Control**: Instead of automatic handling, users can manage their vector collection and tuning process entirely.
- **Scalability**: Perfect for larger applications that require fine-tuned control over vectors and their associated metadata.

With our system, collections act as a combination of Pinecone's **index** and **namespace**, and users can specify the vector size during collection creation, making it highly customizable and scalable for any AI application.

## Creating a Vector Collection

Creating a vector collection in our system combines the concepts of **index** and **namespace** from Pinecone. Here's how to create a collection:

```bash
curl -L -X POST 'https://apipie.ai/v1/vectors' \
-H 'Content-Type: application/json' \
-H 'Accept: application/json' \
-H 'Authorization: <API_KEY_VALUE>' \
--data-raw '{
  "collectionName": "my-collection",
  "dimension": 512
}'
```

This request creates a new vector collection with a specific dimension. You can define the size of your vectors by setting the `dimension` parameter.

## Listing Vector Collections

To retrieve a list of all vector collections under your account:

```bash
curl -L -X POST 'https://apipie.ai/v1/vectors/listcollections' \
-H 'Accept: application/json' \
-H 'Authorization: <API_KEY_VALUE>' \
--data-raw '{}'
```

This returns an array of vector collections that have been created. Remember, our **collection** refers to both the index and namespace.

## Deleting a Collection or Vectors

You can delete an entire collection or specific vectors within it. Here’s how to do it:

```bash
curl -L -X POST 'https://apipie.ai/v1/vectors/delete' \
-H 'Content-Type: application/json' \
-H 'Accept: application/json' \
-H 'Authorization: <API_KEY_VALUE>' \
--data-raw '{
  "collection": "my-ragtune-collection",
  "collectionName": "my-collection",
  "deleteAll": false,
  "ids": [
    "id1",
    "id2"
  ],
  "filter": {
    "key": "value"
  }
}'
```

Use this request to delete specific vectors by ID or delete the entire collection if needed.

## Upserting a Vector

You can insert or update (upsert) vectors in your collection with metadata and embeddings:

```bash
curl -L -X PUT 'https://apipie.ai/v1/vectors/upsert' \
-H 'Content-Type: application/json' \
-H 'Authorization: <API_KEY_VALUE>' \
--data-raw '{
  "collectionName": "my-collection",
  "vectorId": "vector-id-123",
  "metatag": "sampleTag",
  "data": "This is some clear text data associated with the vector",
  "embedding": [
    0.1,
    0.2,
    0.3
  ]
}'
```

This upserts a vector into the collection, allowing you to include both metadata and embeddings for future querying.

## Listing Vector IDs in a Collection

To list vector IDs from a collection:

```bash
curl -L -X POST 'https://apipie.ai/v1/vectors/list' \
-H 'Content-Type: application/json' \
-H 'Accept: application/json' \
-H 'Authorization: <API_KEY_VALUE>' \
--data-raw '{
  "collectionName": "my-collection",
  "limit": 100,
  "prefix": "prefix",
  "paginationToken": "token123"
}'
```

You can paginate through results using the `paginationToken` and set a limit on how many vector IDs to return.

## Fetching a Specific Record

To fetch the contents of a specific vector by its ID:

```bash
curl -L -X GET 'https://apipie.ai/v1/vectors/fetch' \
-H 'Accept: application/json' \
-H 'Authorization: <API_KEY_VALUE>' \
--data-raw '{
  "collectionName": "my-collection",
  "ids": "vector-id-123"
}'
```

This request retrieves the specified vector's content and metadata from your collection.

## Querying Vectors

You can query the vectors in your collection to find the most relevant ones:

```bash
curl -L -X POST 'https://apipie.ai/v1/vectors/query' \
-H 'Content-Type: application/json' \
-H 'Authorization: <API_KEY_VALUE>' \
--data-raw '{
  "collectionName": "my-collection",
  "vector": [
    0.1,
    0.2,
    0.3
  ],
  "topK": 10,
  "includeValues": true,
  "includeMetadata": false,
  "filter": {
    "key": "value"
  },
  "metatag": "tag123"
}'
```

This request allows you to query vectors based on their embeddings, metadata, or additional filters.

## Using Vector Collections with a Query

Once you’ve created a collection and upserted vectors, you can integrate this vector collection into any query using the `rag_tune` parameter. This approach allows you to augment your AI model with your custom vector data for enhanced responses:

```bash
curl -L -X POST 'https://apipie.ai/v1/chat/completions' \
-H 'Content-Type: application/json' \
-H 'Accept: application/json' \
-H 'Authorization: Bearer <TOKEN>' \
--data-raw '{
  "messages": [
    {
      "role": "user",
      "content": "Why is the sky blue?"
    }
  ],
  "model": "gpt-3.5-turbo",
  "provider": "openai",
  "rag_tune": "my-collection"
}'
```

This adds the vector-based augmentation from your specified collection into the AI model’s query.

## Benefits of Pinecone Integration

- **Direct Control Over Vectors**: Full flexibility to create, upsert, query, and delete vectors on your terms.
- **Seamless Integration**: Use any model we support with RAG via the `rag_tune` parameter, empowering users to manage custom embeddings effectively.
- **Optimized Costs**: With efficient read/write units and affordable storage fees, users can manage large-scale vector databases without breaking the bank.
- **Scalability**: The ability to handle high-dimensional vector spaces and large datasets, making it ideal for enterprise-level applications.

## Pinecone Integration Fees

Keep in mind that Pinecone Integration incurs the following costs:
- **Read/Write Operations**: Fees apply when you perform read or write operations on vector data.
- **Storage Fees**: Daily storage fees accumulate based on the size of your vector collections, offering affordable rates even for large collections.

## FAQs

1. **How do I create an index in Pinecone Integration?**
   - You don't need to create an index separately. Our system handles this by combining the concepts of **index** and **namespace** into what we call a "collection." When you create a collection using the `collectionName` and `dimension` parameters, you effectively create both the index and namespace in one step.

2. **Can I specify different dimensions for each collection?**
   - Yes, when creating a collection, you can specify the vector dimension that suits your needs. This allows for flexibility based on the data you're working with.

3. **What happens if I delete a vector collection?**
   - Deleting a vector collection removes all the vectors and data associated with it. If you need more control, you can choose to delete specific vectors within a collection instead of the entire collection.

4. **Is there a limit on the number of vectors I can store in a collection?**
   - There is no hard limit on the number of vectors you can store, but keep in mind that storage costs accumulate daily based on the size of the data. The system is designed to scale with your needs.

5. **Can I use my vector collection with any model?**
   - Yes, once you've created and populated a vector collection, you can use the `rag_tune` parameter to augment any model we support, providing more contextually accurate responses based on your custom data.

## Conclusion

Our Pinecone Integration empowers businesses to fully control their vector databases and fine-tune AI responses with custom data. This feature ensures scalability, flexibility, and affordability, allowing users to manage and query vectors directly for advanced RAG capabilities.

## Links

- [Pinecone API Documentation](https://apipie.ai/docs/api/vectors)
- [Chat Completions API](https://apipie.ai/docs/api/chatcompletions)
- [URL Share -Upload a file, get a URL](https://apipie.ai/docs/api/upload-file)
  
