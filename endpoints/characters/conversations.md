# Conversations

A conversation is a series of text, audio, and image exchanges between a user and a character.&#x20;

### Create a new conversation

{% swagger method="post" path="/conversations" baseUrl="https://api.vana.com/api/v0" summary="Create a new conversation between a user and a character" %}
{% swagger-description %}
Returns the ID of the newly created conversation
{% endswagger-description %}

{% swagger-parameter in="body" name="characterId" type="uuid" required="true" %}

{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
Sample Response Body

<pre class="language-json"><code class="lang-json"><strong>{
</strong>    "success": true,
    "id": "d9e6d843-9fcc-4426-aafa-bfb92146019d"
}
</code></pre>
{% endswagger-response %}
{% endswagger %}

### List existing conversations

{% swagger method="get" path="/conversations" baseUrl="https://api.vana.com/api/v0" summary="Lists conversations between a user and other characters" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-response status="200: OK" description="" %}
Sample Response Body

```json
{
    "success": true,
    "conversations": [
        {
            "id": "be1ee506-bc45-4ec3-9795-13629d9cf1e2",
            "speakers": [
                {
                    "id": "130d0585-f940-4084-8527-31b14ab9a783",
                    "name": "kahtaf_dev",
                    "type": "account",
                    "avatarUrl": null
                },
                {
                    "id": "088473d6-e972-426a-b2bc-f74e2a374dd1",
                    "name": "annakaz",
                    "type": "character",
                    "avatarUrl": "https://storage.googleapis.com/vana-gotchi-data-development/088473d6-e972-426a-b2bc-f74e2a374dd1/generated/20231108193735_avatar.png?Expires=1700155546&GoogleAccessId=vana-app-user%40corsali-development.iam.gserviceaccount.com&Signature=gkTy53REs%2Fi9X4aOfPPBjauu9jckzp8N5OVrjngA%2F1uD3RVjuVaqIcEE5WwwCxHhzl5%2Bk0NvdktDEg8HAdyYPsFgaqDdNRm%2BhIiZvK6sG6zxkcHG4LPACaCbyYINLvJyStIOBF%2FyN%2FXZKUWvzu9OExKuCgOn46XNiNbi7bhi%2Bwv2gQwnTJDtKs6Ek0JVsFPjvq8itnmgsEar72yNYKBkTL66sby0aeL0XcgrrPCJAIP5RT98abUHVv7QQX%2BYnGJ0tWZ%2BhZ5Sv1%2BCw%2BHrrHuaxPgMpVtwW%2B9VvIoFqSrk%2BGp90HmfQiHuOOCj38ep2wlfF27Az6WRC9Qg40Hv3tg0fQ%3D%3D"
                }
            ],
            "created": "2023-11-10T23:58:09.055753Z",
            "updated": "2023-11-10T23:58:09.055753Z"
        }
    ]
}
```
{% endswagger-response %}
{% endswagger %}

### List messages from a conversation

{% swagger method="get" path="/conversations/:conversation-id" baseUrl="https://api.vana.com/api/v0" summary="Lists messages for a given conversation" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="conversation-id" required="true" type="uuid" %}

{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
Sample Response Body

<pre class="language-json"><code class="lang-json"><strong>{
</strong>    "id": "be1ee506-bc45-4ec3-9795-13629d9cf1e2",
    "speakers": [
        {
            "id": "130d0585-f940-4084-8527-31b14ab9a783",
            "name": "kahtaf_dev",
            "type": "account",
            "avatarUrl": null
        },
        {
            "id": "088473d6-e972-426a-b2bc-f74e2a374dd1",
            "name": "annakaz",
            "type": "character",
            "avatarUrl": "https://storage.googleapis.com/vana-gotchi-data-development/088473d6-e972-426a-b2bc-f74e2a374dd1/generated/20231108193735_avatar.png?Expires=1700156023&#x26;GoogleAccessId=vana-app-user%40corsali-development.iam.gserviceaccount.com&#x26;Signature=SXjNyvURqfnEW4sAYZ%2FBUcCoBSemblpfjy1XwsTkuTaV8ouzPE7OMQCV06TJTh1oP%2FTKhDmBTKx%2F5QyhjeMPFrDyeozyoL502Mlpk014s1%2B%2FJAKwCVSY2Pg%2Fsd98bqXxgbMha%2B%2FiqAclX9CEKVUGaOmpzLoKWR9S2AZY%2FVtrlTMmUDgiVDIx1IkyxCQNPEVbH4I7Q9XPL5UpixQJRxv0ChHUlr2sWjyTDh7qcm8Ch0GRP%2Bs6RztMFNub47nik7M9jG7Os7O%2BpgVPVaAP3VCs99c5VklcWlBx0rMekLCMewjio1TSjqVjH6qvYt9Hvn65r642f21lyzHVGNVQ3eiD7g%3D%3D"
        }
    ],
    "created": "2023-11-10T23:58:09.055753Z",
    "updated": "2023-11-10T23:58:09.055753Z",
    "messages": [
        {
            "id": "602a2229-daa4-4a68-8c1a-88b46feee26d",
            "content": "Hi! Tell me about yourself",
            "mimetype": "text/plain",
            "participant_id": "130d0585-f940-4084-8527-31b14ab9a783",
            "participant_type": "account",
            "created": "2023-11-10T23:58:25.322663Z"
        },
        {
            "id": "be65f5d6-c9d7-4e52-94b7-389976b6e5e2",
            "content": " Well, I'm an AI version of a person named Anna. My purpose is to be her amplified digital representation! 😄\nMy creators designed me with all the knowledge and experiences that Anna has accumulated throughout her life. So yeah, you can say I know quite a lot about various topics - but don't worry, if there are some gaps in my memory banks (which sometimes happens), just ask away and we will explore it together! After all learning never ends right?✨",
            "mimetype": "text/plain",
            "participant_id": "088473d6-e972-426a-b2bc-f74e2a374dd1",
            "participant_type": "character",
            "created": "2023-11-10T23:58:35.164647Z"
        }
    ]
}
</code></pre>
{% endswagger-response %}
{% endswagger %}

### Send a message (Coming Soon)

{% swagger method="get" path="/conversations/:conversation-id/chat" baseUrl="https://api.vana.com/api/v0" summary="Send a new message in a conversation" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="conversation-id" required="true" type="uuid" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" required="true" name="data" %}
The content of the message
{% endswagger-parameter %}

{% swagger-parameter in="body" name="mimeType" %}
Represents the mimeType of the data field (ex: text/plain, image/png)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="allow" type="String Array" %}
The allowed mimetypes of the response from the character
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
Sample Request Body

```json
{
    "data": "Hi there", 
    "mimeType": "text/plain",
    "allow": ["text/plain"]
}
```

Sample Response Body

```json
{
    "data": "Hi, how are you?", 
    "mimeType": "text/plain",
    "timestamp": "2023-09-22T19:04:29.615Z",
    "chunkId": 1,
    "isLastChunk": false,
}
```
{% endswagger-response %}
{% endswagger %}
