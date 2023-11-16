# Characters

Characters are the AI representations of a user. They can represent a user's looks, voice, memories, and personality.&#x20;

### Get a Specific Character

{% swagger method="get" path="/characters/:character-id" baseUrl="https://api.vana.com/api/v0" summary="" %}
{% swagger-description %}
Get the details of a specific character, given its character ID. The character ID that belongs to a user's account can be found in the [/accounts](../accounts.md#retreive-account-details-for-a-specific-user) endpoint.
{% endswagger-description %}

{% swagger-parameter in="path" name="character-id" required="true" type="uuid" %}

{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```json
{
    "id": "6320a05b-548f-4c8a-aaf9-15c38e46dbbd",
    "name": "Kahtaf",
    "description": "This character is a patient Southeast Asian software engineer who was born in Bangladesh and now resides in Toronto, Canada. They find fulfillment in their work with AI tools at a company called Vana and appreciate the kindness of the people in their community. They have a love for their cultural heritage, particularly the delicious food. In their free time, they enjoy the freedom of riding bikes.",
    "is_public": true,
    "account_id": "130d0585-f940-4084-8527-31b14ab9a783",
    "avatar_url": "https://storage.googleapis.com/vana-gotchi-data-development/6320a05b-548f-4c8a-aaf9-15c38e46dbbd/generated/avatar_20231110235445.png?Expires=1700152779&GoogleAccessId=vana-app-user%40corsali-development.iam.gserviceaccount.com&Signature=Juvq5aoLii19qfWk%2FtTqd04fSJYSWNUAgWNNPwqZLy8l3I1aHooEKknHmiqFsg6sZgPZKjkm%2BkOYf2J2nk%2BjHzm8BYqo2rHnB%2FtboSi1IkPGMZ4fQKWydXCbfwEcPvuFvoRdiRNENEfyu3DMysSUpU56wk4DD833nFW%2BMN2%2FcqPvT1V7J4VZgGCl5xRS%2FTesWpoJMIzbdsbkEdQ4JGWGXRCJC69gx5LKZ2CoSvXQ85284qube0qQuYIdlUns93iNyFmozNSzkyZJ1ceuOAsVzdxbXLqwT8O79nv0UAEEnX5hx1MlOq2ej4UC2fwdmW4TTvJ%2BzGvD5EwF6F1bD8xIlA%3D%3D",
    "personality_summary": "The Balanced Scholar: Curious, diligent, introverted, kind-hearted, and emotionally even-keeled.",
    "elevenlabs_voice_id": "EfzzdJYh25dcd69JQjFp",
    "created": "2023-11-03T16:18:02.271035Z",
    "updated": "2023-11-10T23:54:46.357001Z"
}
```
{% endswagger-response %}
{% endswagger %}
