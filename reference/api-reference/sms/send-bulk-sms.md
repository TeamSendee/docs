# Send Bulk SMS

## Sending Bulk SMS

{% swagger method="post" path="/sms/bulk/send" baseUrl="https://gosendee.com/api" summary="Send Multiple SMS messages" %}
{% swagger-description %}
Send multiple SMS messages via the Sendee queue with one request
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
A comma separated array of phone numbers. The destination phone numbers must be in 

[E.164](https://www.twilio.com/docs/glossary/what-e164)

 format for SMS/MMS
{% endswagger-parameter %}

{% swagger-parameter in="body" name="body" required="true" %}
The text of the message you want to send. Can be up to 1,600 characters in length.
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    "success": "true",
    "data": {
        "bulk_message_id": "409e3444-ca88-4f69-9ffc-2ddf3abf6740"
    }
}
```
{% endswagger-response %}

{% swagger-response status="401: Unauthorized" description="" %}
```javascript
{
    "success": false,
    "message": "Unauthenticated."
}
```
{% endswagger-response %}
{% endswagger %}

## Example Request

Requests can be send via a form body or JSON string

```json
{
    "from": "+15555558108",
    "to": [
        "+15555559411", 
        "+15555559412", 
        "+15555559413", 
        "+15555559414", 
        "+15555559415", 
        "+15555559416", 
        "+15555559417", 
        "+15555559418"
    ],
    "body": "A new test message  13857"
}
```
