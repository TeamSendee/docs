# SMS

{% hint style="info" %}
Good To Know!\
\
All requests require an Authentication Bearer token to be sent in the header. [Find out more here](../../authentication.md)
{% endhint %}

## Sending an SMS

{% swagger method="post" path="sms/send" baseUrl="https://gosendee.com/api/" summary="Send a single SMS" %}
{% swagger-description %}
Sends a single SMS via the Sendee queue.
{% endswagger-description %}

{% swagger-parameter in="body" name="from" required="true" %}
A Twilio phone number in 

[E.164](https://www.twilio.com/docs/glossary/what-e164)

 format, an 

[alphanumeric sender ID](https://www.twilio.com/docs/sms/send-messages#use-an-alphanumeric-sender-id)

, or a 

[Channel Endpoint address](https://www.twilio.com/docs/sms/channels#channel-addresses)

 that is enabled for the type of message you want to send. Phone numbers or 

[short codes](https://www.twilio.com/docs/sms/api/short-code)

 purchased from Twilio also work here.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="to" required="true" %}
The destination phone number in 

[E.164](https://www.twilio.com/docs/glossary/what-e164)

 format for SMS/MMS
{% endswagger-parameter %}

{% swagger-parameter in="body" name="body" required="true" %}
The text of the message you want to send. Can be up to 1,600 characters in length.
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Example JSON Response" %}
```json
{
    "success": "true",
    "data": {
        "id": "33d2d8a8-c043-4f8d-8b8e-79f36dcc08c2",
        "from": "+15555558108",
        "to": "+15555559410",
        "body": "This is a test",
        "media": null,
        "date_created": "10-24-2022 17:36:33",
        "direction": "outbound",
        "status": "sent"
    }
}
```
{% endswagger-response %}

{% swagger-response status="403: Forbidden" description="" %}
```json
{
    "success": false,
    "message": "Unauthenticated."
}
```
{% endswagger-response %}
{% endswagger %}
