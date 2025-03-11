
<div align="center">
    <img src="https://apipie.ai/docs/img/apipie-logo.png" alt="APIpie" width="125" height="125"style={{ marginRight: '20px' }} />
    <img src="https://apipie.ai/docs/img/AnythingLLM.png" alt="AnythingLLM" width="497" height="125" />

</div>


This guide will walk you through the process of integrating AnythingLLM with APIpie to leverage the power of multiple AI models and enhance your chatbot experience.

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

### 4. Install AnythingLLM
- Follow the [AnythingLLM Installation Guide](https://docs.useanything.com/installation-desktop/overview) to install either locally or via Docker

### 5. Access the AnythingLLM Settings
- Configure the LLM Preference either on initial setup or by changing the settings after configured.
- Find your prefered LLM on the [APIpie.ai Dashboard](https://apipie.ai/dashboard/) and take note of the Name, MAxTokens, and MaxResponse.
- Set the "Base URL" to https://apipie.ai/v1/
- Paste your generated API key into the designated field.
- Configure the appropite model name.
- Set the "Token Context Window" to the "MaxResponse".
- Set the "Max Tokens" and save the settings.

#### Initial Setup:
<div align="center">
    <img src="https://apipie.ai/docs/img/Integrations/AnythingLLM/Initial-Settings.png" alt="Initial Setup"/>
</div>

#### Changing Settings:
<div align="center">
    <img src="https://apipie.ai/docs/img/Integrations/AnythingLLM/Settings.png" alt="Settings"/>
</div>

### 6. Set the AnythingLLM Agent LLM
#### Agent Setup:
- From the main screen select the settings option on the configured workplace
- Change to the "Agent Configuration" tab.
- Select "Local AI" as the provider

<div align="center">
    <img src="https://apipie.ai/docs/img/Integrations/AnythingLLM/Workplace-Agent.png" alt="Agent Setup"/>
</div>

#### Agent AI Settings:
- Set the "Local AI Base URL" to https://apipie.ai/v1
- Enter your generated API key ( if you want separate activity statements generate a new key identifying the agent)
- Save Settings
<div align="center">
    <img src="https://apipie.ai/docs/img/Integrations/AnythingLLM/Local-AI-Agent.png" alt="Agent AI"/>
</div>

- Select the desired Agent AI model.


### 7. Start Chatting
- With the integration complete, you can now enjoy AI-powered conversations in AnythingLLM.

<div align="center">
    <img src="https://apipie.ai/docs/img/Integrations/AnythingLLM/AnythingLLM.png" alt="Desktop" width="845" height="502" style={{ marginRight: '20px' }} />
</div>


## Caveats 
- Currently AnythingLLM is yet support APIpie TTS, STT, or Embedding. 
- If this changes or if assistance is required to onboard more APIpie features please reach out on our [Discord](https://discord.gg/hs82THc9Tw)

## Additional Resources
- **AnythingLLM Website**: Explore more features and capabilities of AnythingLLM. [Visit the website](https://useanything.com/)
- **AnythingLLM GitHub**: Access the source code and contribute to the AnythingLLM project. [Visit GitHub](https://github.com/Mintplex-Labs/anything-llm)
- **AnythingLLM Documentation**: Dive deeper into AnythingLLM's functionalities and configurations. [Access the docs](https://docs.useanything.com/)
- **Mintplex Labs**: Explore Mintplex Labs the team that brings us AnythingLLM [Mintplex Labs](https://mintplexlabs.com/)

## Connect with AnythingLLM
- [LinkedIn](https://www.linkedin.com/company/mintplex-labs)
- [YouTube](https://www.youtube.com/@mintplexlabs)
- [Twitter/X](https://x.com/AnythingLLM)
- [Discord](https://discord.gg/Dh4zSZCdsC)

### Additional Support
If you encounter any issues during the integration process, please reach out to us on [Discord](https://discord.gg/hs82THc9Tw) for assistance.
