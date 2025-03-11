

<div align="center">
    <img src="https://apipie.ai/docs/img/apipie-logo.png" alt="APIpie" width="125" height="125"style={{ marginRight: '20px' }} />
    <img src="https://apipie.ai/docs/img/OpenWebUI.png" alt="OpenWebUI" width="125" height="125" />

</div>


This guide will walk you through the process of integrating OpenWebUI with APIpie to leverage the power of multiple AI models and enhance your chatbot experience.

## Steps

### 1. Create an Account
- **Link**: [Register here](https://apipie.ai/profile/auth/register)
- Follow the link and fill out the form to create your account.

### 2. Add Credit
- **Link**: [Add Credit](https://apipie.ai/profile/subscribe)
- Access the subscription section after logging in to add credits to your account.

### 3. Generate an API Key
- **Link**: [Generate API Key](https://apipie.ai/profile/api-keys)
- Navigate to the API keys section and create a new key. This key is necessary for API requests.

### 4. Install OpenWebUI
- Follow the [OpenWebUI Installation Guide](https://docs.openwebui.com/getting-started/) to install either manually or via Docker

### 5. Access the OpenWebUI Settings

#### Configure  APIpie API:
- Open the Settings within OpenWebUI and navigate to the Connections Tab
- Enable OpenAI API 
- Set the "API Base URL" to https://apipie.ai/v1/
- Paste your generated API key into the designated field.
- Verify the connection is successful
- Save the settings.


<div align="center">
    <img src="https://apipie.ai/docs/img/Integrations/OpenWebUI/API-config.png" alt="Configure API"/>
</div>


#### Set Default LLM:
- Navigate to the Users Tab
- Set the Default Model with your preferred LLM
- Save the settings.


<div align="center">
    <img src="https://apipie.ai/docs/img/Integrations/OpenWebUI/Set-LLM.png" alt="Set LLM"/>
</div>


### 6. Start Chatting
- With the integration complete, you can now enjoy AI-powered conversations in OpenWebUI.

<div align="center">
    <img src="https://apipie.ai/docs/img/Integrations/OpenWebUI/OpenWebUI.png" alt="Desktop" width="867" height="453" style={{ marginRight: '20px' }} />
</div>

## Caveats 
- Currently OpenWebUI is yet to support APIpie TTS, STT, Image, & Embedding. 
- If this changes or if assistance is required to onboard more APIpie features please reach out on our [Discord](https://discord.gg/hs82THc9Tw)

## Additional Resources
- **OpenWebUI Website**: Explore more features and capabilities of OpenWebUI. [Visit the website](https://openwebui.com/)
- **OpenWebUI GitHub**: Access the source code and contribute to the OpenWebUI project. [Visit GitHub](https://github.com/open-webui/open-webui)
- **OpenWebUI Documentation**: Dive deeper into OpenWebUI's functionalities and configurations. [Access the docs](https://docs.openwebui.com/)

## Connect with OpenWebUI
- [LinkedIn](https://www.linkedin.com/company/open-webui/)
- [Twitter](https://twitter.com/OpenWebUI)
- [Discord](https://discord.com/invite/5rJgQTnV4s)

### Additional Support
If you encounter any issues during the integration process, please reach out to us on [Discord](https://discord.gg/hs82THc9Tw) for assistance.
