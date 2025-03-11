<div align="center">
<img src="https://apipie.ai/docs/img/Models/Stability_AI.png" alt="Stable Diffusion Models" width="100%" />
</div>

:::info
For detailed information about using models with APIpie, check out our [Models Overview](https://APIpie.ai/docs/Features/Models) and [Completions Guide](https://APIpie.ai/docs/Features/Completions).
:::

### **Model Comparison and Monitoring**

When choosing between Stable Diffusion models, APIpie provides comprehensive monitoring tools to help make informed decisions:

**Performance Monitoring:**
- Real-time availability tracking across providers (Prodia, Bedrock, DeepInfra, Together)
- Latency metrics and historical performance data
- Response time comparisons between different model versions
- Specific performance tracking for SDXL and specialized variants

**Pricing & Cost Analysis:**
- Live pricing updates through our [Models Route](https://APIpie.ai/docs/Features/Models) & [Dashboard](https://apipie.ai/dashboard) 
- Cost comparisons across different providers and model variants
- Usage-based optimization recommendations
- Provider-specific pricing tracking

**Health Metrics:**
- Global AI health dashboard for real-time status
- Provider reliability tracking
- Model uptime statistics
- Performance monitoring across different capabilities (base models, SDXL, specialized variants)

This monitoring system helps users:
- Compare costs and pricing across different Stable Diffusion models and providers
- Track performance metrics to optimize response times
- Make data-driven decisions based on availability and reliability
- Monitor system health and anticipate potential issues
- Choose optimal model based on performance and cost needs

:::tip
Use the [Models Route](https://APIpie.ai/docs/Features/Models) to access real-time pricing and performance data for all Stable Diffusion models.
:::

### **Description**

[Stable Diffusion](https://stability.ai/stable-diffusion), developed by [Stability AI](https://stability.ai/), represents a state-of-the-art collection of image generation models. These models excel at creating high-quality images from text descriptions, offering enterprise-grade reliability through [APIpie's routing system](https://APIpie.ai/docs/Features/Routing). The technology is built on [CompVis's Latent Diffusion](https://github.com/CompVis/latent-diffusion) architecture and has been trained on [LAION's extensive dataset](https://laion.ai/blog/laion-5b/).

For community resources and discussions, visit the [Stable Diffusion subreddit](https://www.reddit.com/r/StableDiffusion/) or join the [official Discord](https://discord.com/invite/stablediffusion). The models have been extensively [benchmarked and compared](https://arxiv.org/abs/2302.04222) in various studies.

#### **Technical Specifications**

- **Model Architecture:** Based on [Latent Diffusion Models](https://arxiv.org/abs/2112.10752)
- **Training Data:** Trained on [LAION-5B](https://laion.ai/blog/laion-5b/) dataset
- **Model Weights:** Available on [HuggingFace](https://huggingface.co/stabilityai)
- **Compute Requirements:** Varies by model size detailed specifications

#### **Performance Metrics**

- **FID Score:** Competitive scores across model versions ([benchmark results](https://arxiv.org/abs/2304.06140))
- **Generation Speed:** From 1-7 seconds depending on hardware and model ([speed comparison](https://huggingface.co/papers/2304.06140))
- **Resolution Support:** Up to 2048x2048 pixels in SDXL models ([resolution study](https://arxiv.org/abs/2307.01952))

#### **Model Families**

**Stable Diffusion Series:**
- **SDXL Models:** Latest generation including animagineXL, dreamshaperXL, and sd_xl_base
- **SD V1-V2 Models:** Classic models including v1-4, v1-5, and v2-1
- **Specialized Models:** 
  - Realistic Vision series for photorealism
  - Anime-focused models like dreamlike-anime
  - Artist-specific models and style variants
  - Children's story models
  - Epic realism series
  - Dreamshaper variants

#### **Key Features**

- **Diverse Generation Capabilities:** Over 100 models for different artistic styles and use cases
- **Provider Options:** Available through multiple providers including Prodia, Bedrock, DeepInfra, and Together
- **Performance Options:** From high-quality SDXL to efficient SD base models
- **Enterprise Focus:** Built for production-grade image generation applications

---

### **Model List**


#### **Model List updates dynamically please see [the Models Route](https://APIpie.ai/docs/Features/Models#fetching-models) for the up to date list of models**


|                                      |                |                     |                                       |                 |
| ------------------------------------ | -------------- | ------------------- | ------------------------------------- | --------------- |
| **Model Name**                       | **Provider**   | **Type**           | **Description**                       | **Best For**    |
| 3Guofeng3_v34                       | Prodia        | Image              | Specialized artistic style            | Artistic        |
| absolutereality_V16                 | Prodia        | Image              | Photorealistic generation             | Realism         |
| absolutereality_v181                | Prodia        | Image              | Enhanced realism                      | Realism         |
| amIReal_V41                         | Prodia        | Image              | Reality simulation                    | Photorealism    |
| analog-diffusion-1.0                | Prodia        | Image              | Analog photo style                    | Vintage         |
| anythingv3_0-pruned                 | Prodia        | Image              | General purpose                       | Versatile       |
| anything-v4.5-pruned                | Prodia        | Image              | Updated general purpose               | Versatile       |
| anythingV5_PrtRE                    | Prodia        | Image              | Latest anything variant               | Versatile       |
| AOM3A3_orangemixs                   | Prodia        | Image              | Style mixing model                    | Creative        |
| blazing_drive_v10g                  | Prodia        | Image              | Dynamic scene generation              | Action scenes   |
| breakdomain_I2428                   | Prodia        | Image              | Domain transfer                       | Style transfer  |
| breakdomain_M2150                   | Prodia        | Image              | Enhanced domain transfer              | Style transfer  |
| cetusMix_Version35                  | Prodia        | Image              | Mixed style generation                | Hybrid styles   |
| childrensStories_v13D              | Prodia        | Image              | Children's book style                 | Kids content    |
| childrensStories_v1SemiReal        | Prodia        | Image              | Semi-realistic children's style       | Kids content    |
| childrensStories_v1ToonAnime       | Prodia        | Image              | Animated children's style             | Kids animation  |
| Counterfeit_v30                     | Prodia        | Image              | Style replication                     | Style matching  |
| cuteyukimixAdorable_midchapter3     | Prodia        | Image              | Cute anime style                      | Anime           |
| cyberrealistic_v33                  | Prodia        | Image              | Cyberpunk realism                     | Sci-fi realism  |
| dalcefo_v4                          | Prodia        | Image              | Artistic style                        | Creative        |
| deliberate_v2                       | Prodia        | Image              | Controlled generation                 | Precise output  |
| deliberate_v3                       | Prodia        | Image              | Enhanced control                      | Precise output  |
| dreamlike-anime-1.0                 | Prodia        | Image              | Anime art generation                  | Anime           |
| dreamlike-diffusion-1.0             | Prodia        | Image              | General purpose                       | Versatile       |
| dreamlike-photoreal-2.0             | Prodia        | Image              | Photorealistic output                 | Photography     |
| dreamshaper_6BakedVae               | Prodia        | Image              | Optimized dreamshaper                 | Performance     |
| dreamshaper_7                       | Prodia        | Image              | Updated dreamshaper                   | Quality         |
| dreamshaper_8                       | Prodia        | Image              | Latest dreamshaper                    | Best quality    |
| edgeOfRealism_eorV20               | Prodia        | Image              | Realistic edge detection              | Detail focus    |
| EimisAnimeDiffusion_V1             | Prodia        | Image              | Specialized anime                     | Anime           |
| elldreths-vivid-mix                 | Prodia        | Image              | Vivid style mixing                    | Vibrant art     |
| epicphotogasm_xPlusPlus            | Prodia        | Image              | Enhanced photography                  | Photography     |
| epicrealism_naturalSinRC1VAE        | Prodia        | Image              | Natural realism                       | Nature scenes   |
| epicrealism_pureEvolutionV3         | Prodia        | Image              | Pure realism                          | Realism         |
| ICantBelieveItsNotPhotography_seco  | Prodia        | Image              | Photorealistic output                 | Photography     |
| indigoFurryMix_v75Hybrid           | Prodia        | Image              | Furry art style                       | Character art   |
| juggernaut_aftermath                | Prodia        | Image              | Post-processing focus                 | Effects         |
| lofi_v4                            | Prodia        | Image              | Lo-fi aesthetic                       | Stylized        |
| lyriel_v16                          | Prodia        | Image              | Artistic style                        | Creative        |
| majicmixRealistic_v4               | Prodia        | Image              | Magic realism                         | Fantasy realism |
| mechamix_v10                        | Prodia        | Image              | Mechanical style                      | Mecha           |
| meinamix_meinaV9                    | Prodia        | Image              | Style mixing                          | Creative        |
| meinamix_meinaV11                   | Prodia        | Image              | Enhanced mixing                       | Creative        |
| neverendingDream_v122              | Prodia        | Image              | Dreamlike quality                     | Surreal         |
| openjourney_V4                      | Prodia        | Image              | Open source variant                   | General use     |
| pastelMixStylizedAnime_pruned_fp16  | Prodia        | Image              | Pastel anime style                    | Anime           |
| portraitplus_V1.0                   | Prodia        | Image              | Portrait generation                   | Portraits       |
| protogenx34                         | Prodia        | Image              | General purpose                       | Versatile       |
| Realistic_Vision_V1.4               | Prodia        | Image              | Realistic generation                  | Realism         |
| Realistic_Vision_V2.0               | Prodia        | Image              | Enhanced realism                      | Realism         |
| Realistic_Vision_V4.0               | Prodia        | Image              | Advanced realism                      | Realism         |
| Realistic_Vision_V5.0               | Prodia        | Image              | Latest realism                        | Realism         |
| Realistic_Vision_V5.1               | Prodia        | Image              | Current realism                       | Realism         |
| redshift_diffusion-V10             | Prodia        | Image              | Color enhancement                     | Color focus     |
| revAnimated_v122                    | Prodia        | Image              | Animated style                        | Animation       |
| rundiffusionFX25D_v10              | Prodia        | Image              | 2.5D effects                          | Dimensional     |
| rundiffusionFX_v10                  | Prodia        | Image              | Special effects                       | Effects         |
| sdv1_4                             | Prodia        | Image              | Base SD v1.4                          | General use     |
| v1-5-pruned-emaonly                | Prodia        | Image              | Optimized v1.5                        | Efficiency      |
| v1-5-inpainting                    | Prodia        | Image              | Inpainting specialist                 | Editing         |
| shoninsBeautiful_v10               | Prodia        | Image              | Beautiful style                       | Aesthetics      |
| theallys-mix-ii-churned            | Prodia        | Image              | Style mixture                         | Creative        |
| timeless-1.0                       | Prodia        | Image              | Timeless aesthetic                    | Classic style   |
| toonyou_beta6                      | Prodia        | Image              | Cartoon style                         | Animation       |
| animagineXLV3_v30                  | Prodia        | Image              | SDXL anime                            | Anime           |
| dreamshaperXL10_alpha2             | Prodia        | Image              | SDXL dreamshaper                      | Quality         |
| dynavisionXL_0411                  | Prodia        | Image              | SDXL dynamic                          | Motion          |
| juggernautXL_v45                   | Prodia        | Image              | SDXL effects                          | Effects         |
| realismEngineSDXL_v10              | Prodia        | Image              | SDXL realism                          | Realism         |
| realvisxlV40                       | Prodia        | Image              | SDXL vision                           | Vision          |
| sd_xl_base_1.0                     | Prodia        | Image              | SDXL base                             | Foundation      |
| sd_xl_base_1.0_inpainting_0.1      | Prodia        | Image              | SDXL inpainting                       | Editing         |
| turbovisionXL_v431                 | Prodia        | Image              | SDXL turbo                            | Speed           |
| aniverse_v30                       | Prodia        | Image              | Anime universe                        | Anime           |
| devlishphotorealism_sdxl15         | Prodia        | Image              | SDXL photorealism                     | Realism         |
| stable-diffusion-xl                | Bedrock       | Image              | AWS SDXL                              | Enterprise      |
| stable-diffusion-xl-v0             | Bedrock       | Image              | AWS SDXL base                         | Enterprise      |
| stable-diffusion-xl-v1             | Bedrock       | Image              | AWS SDXL latest                       | Enterprise      |
| stable-diffusion-v1-4              | DeepInfra     | Image              | SD v1.4                               | General use     |
| stable-diffusion-v1-5              | DeepInfra     | Image              | SD v1.5                               | General use     |
| stable-diffusion-2-1               | DeepInfra     | Image              | SD v2.1                               | General use     |
| stable-diffusion-xl-base-1.0       | Together      | Image              | SDXL base                             | General use     |

---

### Example API Call

Below is an example of how to use the [Image Generation API](https://APIpie.ai/docs/Features/Images) with a Stable Diffusion model:
```bash
curl -L -X POST 'https://apipie.ai/v1/images/generations' \
-H 'Content-Type: application/json' \
-H 'Accept: application/json' \
-H 'Authorization: Bearer <YOUR_API_KEY>' \
--data-raw '{
  "provider": "prodia",
  "model": "sd_xl_base_1.0",
  "prompt": "A serene landscape with mountains reflected in a calm lake at sunset",
  "n": 1,
  "size": "1024x1024"
}'
```

---

### Response Example

The expected response structure for a Stable Diffusion model:

```json
{
  "created": 1729535643,
  "data": [
    {
      "url": "https://example.com/generated-image.png",
      "b64_json": null
    }
  ],
  "usage": {
    "prompt_tokens": 15,
    "total_tokens": 15,
    "cost": 0.008000,
    "latency_ms": 5200
  }
}
```

---

### API Highlights and Integration

- **Model Selection:**
  - Use SDXL variants for highest quality
  - Choose specialized models for specific styles (anime, realistic, artistic)
  - Select provider based on needs (Prodia, Bedrock, DeepInfra, Together)
- **Parameters:** 
  - Customize image size, quality, and generation parameters
  - Support for advanced prompting techniques
- **Response:** Receive generated images as URLs or base64 encoded data

---

### **Applications and Success Stories**


- **Creative Applications:**
  - Digital art creation with tools like [Automatic1111's Web UI](https://github.com/AUTOMATIC1111/stable-diffusion-webui)
  - Anime and illustration using specialized models
  - Character design for games and animation
  - Concept art for production pipelines
  
- **Professional Use:**
  - Product visualization for e-commerce
  - Marketing materials and advertising
  - Stock photo alternatives
  - Content creation for social media
  - Architecture and interior design

- **Specialized Tasks:**
  - Photorealistic imaging
  - Artistic style transfer and remixing
  - Character generation for gaming
  - Scene composition for storyboarding
  - Fashion design and visualization

- **Research and Development:**
  - [AI art research](https://arxiv.org/abs/2112.10752) and experimentation
  - Model fine-tuning and customization
  - Novel image generation techniques
  - Computer vision applications

---

### **Ethical Considerations**

Stable Diffusion models should be used responsibly with appropriate content filtering and bias consideration. For more information, visit [Stability AI's safety Policy](https://stability.ai/safety). 


---

### **Licensing and Resources**

Stable Diffusion models are available under the [CreativeML Open RAIL-M license](https://huggingface.co/spaces/CompVis/stable-diffusion-license).

**Additional Resources:**
- [Official Documentation](https://platform.stability.ai/docs/getting-started)
- [Model Architecture Paper](https://arxiv.org/abs/2112.10752)
- [HuggingFace Model Hub](https://huggingface.co/stabilityai)
- [GitHub Repository](https://github.com/CompVis/stable-diffusion)
- [Community Wiki](https://wiki.installgentoo.com/wiki/Stable_Diffusion)

:::tip
Try out the Stable Diffusion models in APIpie's various [supported integrations.](https://APIpie.ai/docs/Sandbox/Chat)
:::
