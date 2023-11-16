# Accounts

### List User Accounts

{% swagger method="get" path="/accounts" baseUrl="https://api.vana.com/api/v0" summary="Retreive a list of user accounts" expanded="false" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="username" %}

{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```json
{
    "success": true,
    "accounts": [
        {
            "id": "bc6cbe52-168e-47d2-92bf-a3691be68939",
            "created": 1700030558389,
            "username": "Dimi5552",
            "isVerified": false,
            "isDisabled": false,
            "isSubscribed": false,
            "meta": {
                "dateOfBirth": "1996-07-05",
                "referredByAccountId": "402ff531-eb7c-4cbb-8605-f3448f2d9e58"
            },
            "tags": [],
            "characterId": "15f9edaa-5a2b-4414-9ab4-d75b8e0b4882",
            "profilePictureUrl": null,
        }
    ]
}
```
{% endswagger-response %}
{% endswagger %}

### Get User Account

{% swagger method="get" path="/accounts/:account-id" baseUrl="https://api.vana.com/api/v0" summary="Retreive account details for a specific user" expanded="false" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="account-id" type="uuid" required="true" %}
User's account ID
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```json
{
    "success": true,
    "account": {
        "id": "bc6cbe52-168e-47d2-92bf-a3691be68939",
        "created": 1700030558389,
        "username": "Dimi5552",
        "isVerified": false,
        "isDisabled": false,
        "isSubscribed": false,
        "meta": {
            "dateOfBirth": "1996-07-05",
            "referredByAccountId": "402ff531-eb7c-4cbb-8605-f3448f2d9e58"
        },
        "tags": [],
        "characterId": "15f9edaa-5a2b-4414-9ab4-d75b8e0b4882",
        "profilePictureUrl": null,
    }
}
```
{% endswagger-response %}
{% endswagger %}

### Get a user's balance

{% swagger method="get" path="/accounts/:account-id/balance" baseUrl="https://api.vana.com/api/v0" summary="Retreive a user's account balance" expanded="false" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="account-id" type="uuid" required="true" %}
User's account ID
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```json
{
    "success": true,
    "balance": 100
}
```
{% endswagger-response %}
{% endswagger %}

