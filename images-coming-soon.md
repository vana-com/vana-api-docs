# Images (Coming Soon)

Use [SDXL](https://stability.ai/stable-diffusion) to generate images of a character, the world around you, and anything in between using a single text prompt.

### Generate an image

Once an image generation request is sent, a job is created and the corresponding job ID is sent back.

{% swagger method="post" path="/images" baseUrl="https://api.vana.com/v0/api" summary="Generate an image based on a prompt" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="prompt" required="true" %}
Description of the characters and things you want in the generated image. To reference a character, use `<character-id>` in the prompt.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="negativePrompt" %}
Description of the things you don't want in the generated image
{% endswagger-parameter %}

{% swagger-parameter in="body" name="width" type="Number" %}
Width in pixels of the generated image. Maximum 1024
{% endswagger-parameter %}

{% swagger-parameter in="body" name="height" type="Number" %}
Height in pixels of the generated image. Maximum 1024
{% endswagger-parameter %}

{% swagger-parameter in="body" name="samples" type="Number" %}
Number of images to be returned in the response, maximum 4
{% endswagger-parameter %}

{% swagger-parameter in="body" name="seed" type="Number" %}
Used to reproduce results, same seed will give you same image again
{% endswagger-parameter %}

{% swagger-parameter in="body" name="guidanceScale" type="Number" %}
A lower number incorporates more creativity while a higher number indicates that the image is closely tied to the text prompt (minimum: 1; maximum: 20)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="webhookUrl" %}
Set an URL to get a `POST` request with the details of the image once the generation is complete
{% endswagger-parameter %}

{% swagger-parameter in="body" name="webhookId" %}
ID that's returned in the response to the webhook API call, used to identify the webhook request
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
Sample Request Body

```json
{
    "prompt": "a painting of <6320a05b-548f-4c8a-aaf9-15c38e46dbbd> with a green apple in their mouth, surrealism aesthetic"
}
```

Sample Response Body

```json
{
    "success": true,
    "jobId": "f2c95e57-c831-40e0-b108-f86d2cdc3cbd",
    "transactionId": "50f5f981-76fe-4713-8f87-0b606a4270ec"
}
```
{% endswagger-response %}
{% endswagger %}

### Get generated image

To retreive the images from a generation request, a job can be queried, and the `outputFiles` of the job will contain the list of images once the job is complete.&#x20;

{% swagger method="get" path="/jobs/:job-id" baseUrl="https://api.vana.com/v0/api" summary="Retreives the outputs from a job" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="job-id" type="uuid" %}
ID of the job to retreive
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
Sample Response Body

```json
{
    "success": true,
    "job": {
        "id": "6897f754-61eb-44bd-8bc0-827b45254c09",
        "accountId": "a32a4595-5c97-4cb3-9d90-e03630d9bdda",
        "clientId": "990cb984-f315-4dcb-a9e0-ed47ae37a034",
        "created": 1690923546550,
        "type": "IMAGE_INFERENCE",
        "payload": {
            "seed": -1,
            "loras": [
                {
                    "url": "https://storage.googleapis.com/vana-jobs-output/1c853587-9c0f-40a2-b341-9a1d3a40937e/ae4b5c76-da68-4c5a-a625-dd060fd4abd9.safetensors?X-Goog-Algorithm=GOOG4-RSA-SHA256&X-Goog-Credential=vana-app-user%40corsali-production.iam.gserviceaccount.com%2F20230801%2Fauto%2Fstorage%2Fgoog4_request&X-Goog-Date=20230801T205902Z&X-Goog-Expires=86401&X-Goog-SignedHeaders=host&X-Goog-Signature=732e1db1b14ff53ea60a010dd572e752a71b8ddb75aad4efc1be6db220665c945cf9081205c9e2a48ae0ba5920ccb0f8dd8eb9cfcd31f63cec617e25fa19bc4df9bdb2b82a72a8f1c47a49ee042c764951f1355ef8a8747d31ae9a15da77a38c6388c392afa621b4d3409865f7aed3dadbf152df849fe83a134f5e042d69f4526ede273d4e2bf0d08f3f7d513e47ebc4ee6c2137db78a0f6052c4533155d318e63ccbe9bb74241caa4435e058bd95c345185d0893601b4fb1a5a481ee89ec7bc7fb66575e9dab4991913701afa238e714d8d98465d543946b9df9ed3903d893dedf4bcdc271d4084820bb7b0587403434aa8db39bb433ceef7e851cd456ae2d5",
                    "meta": {
                        "class": "person"
                    }
                }
            ],
            "width": 640,
            "height": 640,
            "prompt": "<1> behind the wheel of a sleek Ferrari, speeding through a winding mountain road, vibrant colors, dynamic composition, adrenaline rush, professional photography, sharp focus, capturing the thrill of the drive, automotive art, trending on Instagram, by Greg Rutkowski, Beeple, and Tony Sart.",
            "atomIds": [
                "c5690ab6-4d61-4367-8ac0-bc6b5980b483"
            ],
            "referer": "https://app.vana.com/",
            "exhibitId": -1,
            "lora_urls": [
                "https://storage.googleapis.com/vana-jobs-output/1c853587-9c0f-40a2-b341-9a1d3a40937e/ae4b5c76-da68-4c5a-a625-dd060fd4abd9.safetensors?X-Goog-Algorithm=GOOG4-RSA-SHA256&X-Goog-Credential=vana-app-user%40corsali-production.iam.gserviceaccount.com%2F20230801%2Fauto%2Fstorage%2Fgoog4_request&X-Goog-Date=20230801T205902Z&X-Goog-Expires=86401&X-Goog-SignedHeaders=host&X-Goog-Signature=732e1db1b14ff53ea60a010dd572e752a71b8ddb75aad4efc1be6db220665c945cf9081205c9e2a48ae0ba5920ccb0f8dd8eb9cfcd31f63cec617e25fa19bc4df9bdb2b82a72a8f1c47a49ee042c764951f1355ef8a8747d31ae9a15da77a38c6388c392afa621b4d3409865f7aed3dadbf152df849fe83a134f5e042d69f4526ede273d4e2bf0d08f3f7d513e47ebc4ee6c2137db78a0f6052c4533155d318e63ccbe9bb74241caa4435e058bd95c345185d0893601b4fb1a5a481ee89ec7bc7fb66575e9dab4991913701afa238e714d8d98465d543946b9df9ed3903d893dedf4bcdc271d4084820bb7b0587403434aa8db39bb433ceef7e851cd456ae2d5"
            ],
            "exhibitName": "Text to Image",
            "num_outputs": 4,
            "guidance_scale": 4.5,
            "safety_checker": true,
            "negative_prompt": "(deformed iris, deformed pupils, semi-realistic, shirtless), text, close up, cropped, out of frame, worst quality, low quality, jpeg artifacts, ugly, duplicate, morbid, mutilated, extra fingers, mutated hands, poorly drawn hands, poorly drawn face, mutation, deformed, blurry, dehydrated, bad anatomy, bad proportions, extra limbs, cloned face, disfigured, gross proportions, malformed limbs, missing arms, missing legs, extra arms, extra legs, fused fingers, too many fingers, long neck",
            "conditionedPrompt": "\"<1>\" person behind the wheel of a sleek Ferrari, speeding through a winding mountain road, vibrant colors, dynamic composition, adrenaline rush, professional photography, sharp focus, capturing the thrill of the drive, automotive art, trending on Instagram, by Greg Rutkowski, Beeple, and Tony Sart.",
            "num_inference_steps": 25
        },
        "outputFiles": [
            {
                "name": "c0693d17-17c4-41f1-af21-d45beef41d7e.png",
                "path": "6897f754-61eb-44bd-8bc0-827b45254c09/c0693d17-17c4-41f1-af21-d45beef41d7e.png",
                "created": 1690923561612,
                "size": 646169,
                "url": "https://storage.googleapis.com/vana-jobs-output/6897f754-61eb-44bd-8bc0-827b45254c09%2Fc0693d17-17c4-41f1-af21-d45beef41d7e.png",
                "feedback": {
                    "like": null,
                    "feedback": null
                }
            },
            {
                "name": "9a880356-7920-48ee-a8ab-05b7c2b44a93.png",
                "path": "6897f754-61eb-44bd-8bc0-827b45254c09/9a880356-7920-48ee-a8ab-05b7c2b44a93.png",
                "created": 1690923561596,
                "size": 717694,
                "url": "https://storage.googleapis.com/vana-jobs-output/6897f754-61eb-44bd-8bc0-827b45254c09%2F9a880356-7920-48ee-a8ab-05b7c2b44a93.png",
                "feedback": {
                    "like": null,
                    "feedback": null
                }
            },
            {
                "name": "54e5a65a-8108-4b66-a6ea-8a54cfa0ad92.png",
                "path": "6897f754-61eb-44bd-8bc0-827b45254c09/54e5a65a-8108-4b66-a6ea-8a54cfa0ad92.png",
                "created": 1690923561547,
                "size": 716065,
                "url": "https://storage.googleapis.com/vana-jobs-output/6897f754-61eb-44bd-8bc0-827b45254c09%2F54e5a65a-8108-4b66-a6ea-8a54cfa0ad92.png",
                "feedback": {
                    "like": null,
                    "feedback": null
                }
            },
            {
                "name": "0e796a86-f89d-45d9-ac00-d8a97e8ef691.png",
                "path": "6897f754-61eb-44bd-8bc0-827b45254c09/0e796a86-f89d-45d9-ac00-d8a97e8ef691.png",
                "created": 1690923561511,
                "size": 634137,
                "url": "https://storage.googleapis.com/vana-jobs-output/6897f754-61eb-44bd-8bc0-827b45254c09%2F0e796a86-f89d-45d9-ac00-d8a97e8ef691.png",
                "feedback": {
                    "like": null,
                    "feedback": null
                }
            }
        ],
        "status": "SUCCESS",
        "statuses": [
            {
                "id": "a7f5f8d4-0858-4cfe-887c-5be208b21f12",
                "status": "SUCCESS",
                "created": 1690923562241
            },
            {
                "id": "326de86b-ebb6-43b9-b084-50848e21e746",
                "status": "IN_PROGRESS",
                "created": 1690923547098
            },
            {
                "id": "0bbecfe9-4573-41cc-85c4-31b7fb6b98d0",
                "status": "CREATED",
                "created": 1690923546805
            }
        ]
    }
}
```
{% endswagger-response %}
{% endswagger %}
