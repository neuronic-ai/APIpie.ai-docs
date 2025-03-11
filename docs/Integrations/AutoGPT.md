
<div align="center">
    <img src="https://apipie.ai/docs/img/apipie-logo.png" alt="APIpie" width="125" height="125" style={{ marginRight: '20px' }} />
    <img src="https://apipie.ai/docs/img/autogpt.png" alt="AutoGPT" width="276" height="125" />

</div>


This guide will walk you through the process of setting up your environment to work with APIpie and integrate AutoGPT functionalities effectively.

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

### 4 Configure Your .env File
- Find the `.env` file in your project's directory: `autogpts/autogpt/`. If the file doesn't exist, rename `.env.template` to `.env`.
- Open the `.env` file in your preferred text editor.

### 5. Set Your API Key
- Add or edit the following line with your new API key: `OPENAI_API_KEY=your_new_api_key_here`
  
### 6. Update the Base URL
- On line 68, remove the `#` to uncomment the line and update the base URL to `OPENAI_API_BASE_URL=https://apipie.ai/v1`

### 7. Save and Close the File
- Save the changes and close your text editor.

## Additional Resources
- **AutoGPT User Guide**: Learn more about how to use AutoGPT effectively with their detailed guide. [View the guide here](https://docs.agpt.co/classic/usage/).
- **In-depth AutoGPT Documentation**: Dive deeper into the functionalities and configurations of AutoGPT with their comprehensive documentation. [Access the docs here](https://autogptdocs.com/).
- **AutoGPT News**: Keep up to date with the latest updates and features from AutoGPT. [Visit the news site](https://news.agpt.co/).
- **AutoGPT GitHub Repository**: Explore the source code and contribute to the AutoGPT project on GitHub. [Visit GitHub](https://github.com/Significant-Gravitas/AutoGPT/tree/master).

## Connect with AutoGPT
- [Twitter](https://twitter.com/Auto_GPT)
- [Discord](https://discord.gg/autogpt)

### Additional Support
If this documentation is outdated, or if you encounter any issues, please get in touch with us on [Discord](https://discord.gg/hs82THc9Tw).
