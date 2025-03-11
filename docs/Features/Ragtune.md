
<div align="center">
    <img src="https://apipie.ai/docs/img/Features/ragtune-banner.png" alt="RAG Tuning Feature Banner" width="100%" />
</div>

Unlock the full potential of AI with **RAG Tuning**—a revolutionary feature designed to simplify the process of tuning and optimizing AI responses using your custom data. By augmenting model queries with your own data, RAG Tuning ensures more accurate and context-aware responses, providing a cost-effective alternative to traditional training or fine-tuning.

## Why Use RAG Tuning?

RAG Tuning allows you to bypass expensive and time-consuming model training by augmenting prompts with specific data from your own collection of documents. This enables any AI model to become highly specialized in responding to queries that relate to your content, making it ideal for businesses looking to integrate their own knowledge base without needing to retrain or fine-tune models.

## How RAG Tuning Works

RAG Tuning is built around a few simple steps:

1. **Upload Your Document**: Upload any supported document type (PDF, DOC, DOCX, TXT, CSV, XLS, XLSX) to create a collection.
2. **RAG Tune Query**: Use the `rag_tune` parameter to specify the collection, enhancing the model's ability to provide answers based on your data.
3. **Tailored Responses**: The model retrieves relevant information from your documents and incorporates it into its response, providing answers that are informed by your data.

## Uploading a Document for RAG Tuning

To start using RAG Tuning, upload a document and associate it with a collection. Here’s an API call that demonstrates how to do this:

```bash
curl -L -X POST 'https://apipie.ai/ragtune' \
-H 'Content-Type: application/json' \
-H 'Accept: application/json' \
-H 'Authorization: <API_KEY_VALUE>' \
--data-raw '{
  "collection": "my-ragtune-collection",
  "url": "https://example.com/mydocument.pdf",
  "metatag": "important-document"
}'
```

This request processes the document and adds it to your specified collection. The `metatag` is optional but can be useful for categorizing your documents.

## Listing RAG Collections

To see all collections you’ve created for RAG Tuning, you can use the following API request:

```bash
curl -L -X POST 'https://apipie.ai/ragtune/listCollections' \
-H 'Accept: application/json' \
-H 'Authorization: <API_KEY_VALUE>'
```

This call returns an array of collections currently associated with your account.

## Deleting a RAG Collection

If you need to remove a collection from RAG Tuning, use this API call:

```bash
curl -L -X POST 'https://apipie.ai/ragtune/deleteCollection' \
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

This will delete specific documents from the collection based on the provided filters, or you can delete the entire collection if needed.

## Using RAG Tuning in Your Query

Once you’ve uploaded documents and created a collection, you can augment your queries with RAG Tuning. Here’s an example of how to use the `rag_tune` parameter in an API query:

```bash
curl -L -X POST 'https://apipie.ai/v1/chat/completions' \
-H 'Content-Type: application/json' \
-H 'Accept: application/json' \
-H 'Authorization: Bearer <TOKEN>' \
--data-raw '{
  "messages": [
    {
      "role": "user",
      "content": "Why the sky is blue?"
    }
  ],
  "model": "gpt-3.5-turbo",
  "provider": "openai",
  "rag_tune": "my-ragtune-collection"
}'
```

In this example, the `rag_tune` parameter ensures that the query pulls relevant data from the specified RAG collection to generate a more accurate response.

## Benefits of RAG Tuning for Businesses

- **Cost-Effective**: Unlike traditional model training, RAG Tuning is less expensive, as it involves augmenting prompts rather than retraining the model.
- **Flexible**: Use any supported model for RAG Tuning, including OpenAI models, while incorporating your own data into the responses.
- **Efficient**: The process is quick and straightforward, making it accessible to businesses looking for tailored AI responses without the complexity of fine-tuning.
- **Simple Vector-Based Approach**: Our RAG Tuning simplifies the use of vector-based search, providing a more user-friendly alternative to direct vector databases like Pinecone.

## RAG Tuning Fees

Keep in mind that RAG Tuning incurs the following costs:
- **Document Upload**: Each document uploaded to a RAG collection is charged.
- **Querying Documents**: Additional fees apply when fetching relevant data from the uploaded documents.
- **Storage**: Daily fees apply for storing documents and maintaining collections.

## Tips & Tricks

- **Selective Use of Collections**: Only apply RAG Tuning to specific queries where augmenting the model with your data is beneficial.
- **Experiment with Models**: While `gpt-4o` is a great default, experiment with different models to find the most cost-effective solution for your needs.
- **Manage Costs**: Keep track of the number of documents and collections to balance costs with the accuracy gains from RAG Tuning.

## FAQs

1. **How do I create an index for RAG Tuning?**
   - You don’t need to manually create an index or namespace. When you upload a document and assign it to a `collectionName`, it automatically handles both the index and namespace for you.

2. **Can I use RAG Tuning with any AI model?**
   - Yes, RAG Tuning works with any AI model we support, allowing you to augment your queries with your own data regardless of the model used.

3. **Is there a limit to the number of documents I can upload to a collection?**
   - There is no hard limit, but additional charges apply based on the number of documents uploaded and stored. Monitor your usage to manage costs effectively.

4. **How does RAG Tuning affect the model’s response time?**
   - RAG Tuning may increase response times slightly as the system fetches relevant data from your documents to augment the model’s answer. However, this trade-off usually results in more accurate and context-aware responses.

5. **What happens to my data after I delete a collection?**
   - Once a collection is deleted, all associated documents and embeddings are permanently removed from the system, ensuring your data remains secure and private.


## Links

- [RAG Tuning API Documentation](https://apipie.ai/docs/api/ragtune)
- [Chat Completions API](https://apipie.ai/docs/api/chatcompletions)


## Conclusion

RAG Tuning empowers businesses to enhance their AI models without the cost and complexity of retraining. By augmenting model queries with your own data, RAG Tuning enables any model to provide more accurate and contextually relevant answers. Explore the power of RAG Tuning today and make your AI integrations smarter, faster, and more reliable.

