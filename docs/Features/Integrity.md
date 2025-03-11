
<div align="center">
    <img src="https://apipie.ai/docs/img/Features/integrity-banner.png" alt="Integrity Feature Banner" width="100%" />
</div>

Discover the power of our Integrity feature, specifically designed to enhance AI accuracy and reliability by minimizing hallucinations— a prevalent concern for businesses using AI technology. Integrity is ideal for applications where accuracy and dependability are paramount.

## Why Use Integrity?

Integrity significantly reduces the likelihood of AI-generated errors, known as hallucinations, by implementing a robust validation process. This feature leverages the AI's ability to cross-verify answers to ensure you receive the most accurate response possible, making it invaluable for businesses requiring consistent and reliable AI responses.

## Understanding Integrity Settings

### Integrity Levels

- **Integrity 11**: Default query with no additional checks.
- **Integrity 12**: Queries the specified model twice, allowing AI to vote 5 times on the best answer.
- **Integrity 13**: Queries the model thrice, selecting the best answer from three options.

In both Integrity 12 and 13, the `gpt-4o` model is used by default for integrity checks, taking advantage of OpenAI's capability to provide `n` factor benefits for rapid cross-verification.

### How to Use Integrity

Integrating Integrity into your AI projects is straightforward. Below is a typical API call focusing on the essential parameters for Integrity configuration:

NOTE: Other than adding the integrity setting and the optional integrity model, there is no perceivable difference in the API call or its response, except for the response time. All the processes outlined in this document happen in the background.

## Example:  Query Cohere Command on Openrouter using Open AI gpt-3.5 for Integrity

```bash
curl -L -X POST 'https://apipie.ai/v1/chat/completions' \
-H 'Content-Type: application/json' \
-H 'Accept: application/json' \
-H 'Authorization: Bearer <TOKEN>' \
--data-raw '{
  "messages": [
    {
      "role": "system",
      "content": "Why is the sky blue?"
    }
  ],
  "model": "command",
  "provider": "openrouter",
  "max_tokens": 300,
  "integrity": 12,
  "integrity_model": "gpt-3.5-turbo",
}'
```

This code snippet demonstrates an API call utilizing Integrity to ensure the most reliable answer. Note that the `integrity_model` setting is optional and defaults to `gpt-4o`, but users may set it to any supported OpenAI model. The Response returned is an Open AI styled standard response.

## Benefits of Integrity for Businesses

By mitigating potential hallucinations, the Integrity feature ensures that AI integrations remain dependable and accurate. This is particularly beneficial for business processes where data accuracy is crucial, such as report generation, customer query handling, and automated decision-making systems.

**Note:** Integrity settings incur additional API costs due to repeated queries and voting mechanisms, but remain affordable and worthwhile, especially for high-stakes applications.

## Setting Up Integrity

To effectively use Integrity in your AI workflows, follow these steps:

1. **Configure Your API Call:**
   - Set the `integrity` parameter to 12 or 13 depending on your accuracy needs.
   - Select the `integrity_model` only if deviating from the default `gpt-4o`.

2. **Understand the Cost and Time Implications:**  
   - Ensure your application is suited to handle slight delays in response time due to the voting process.

3. **Test and Validate Results:**  
   - Continuously monitor results to optimize the use of Integrity for your specific requirements.

## Tips & Tricks

- **Leverage Integrity for Complex Queries:** Use Integrity for questions where accuracy is non-negotiable.
- **Balance Cost and Accuracy:** Assess whether Integrity's additional cost aligns with your accuracy needs.
- **Experiment with Different Models:** Although `gpt-4o` is the recommended starting point, trying other OpenAI models in many cases can yield similar results at a lower cost.

## FAQs

1. **What is the main purpose of the Integrity feature?**
   - To reduce hallucinations in AI responses, providing more reliable outputs.

2. **Why does Integrity cost more?**
   - The additional accuracy processes (i.e., multiple queries and voting) incur extra usage costs.

3. **Is Integrity suitable for all AI applications?**
   - It's best used for non-real-time applications where accuracy is prioritized over response speed.

4. **Can other AI models besides OpenAI be used for integrity checks?**
   - Currently, Integrity primarily supports OpenAI models due to specific feature support.

5. **How does Integrity affect response time?**
   - The response time is slightly longer due to added processing, so it is recommended for applications where this delay is acceptable.


## Links

- [Chat Completions API](https://apipie.ai/docs/api/chatcompletions)
- [Fetch Models API](https://apipie.ai/docs/api/fetchmodels)

## Conclusion

With the completion of this guide, you now possess a comprehensive understanding of how to implement and benefit from the Integrity feature in your AI projects. We appreciate your commitment to leveraging Neuronic AI's tools and look forward to seeing how Integrity enhances your AI endeavors.
