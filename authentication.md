# Authentication

The Sendee API uses an API Key to authenticate requests. You can view and manage your API keys in the [Sendee API Settings](https://gosendee.com/settings/api/keys).

Your API keys are how you authenticate into the Sendee API.  Be sure to keep your API keys secure!  Do not share your secret API keys in publicly accessible areas such as GitHub, client-side code, and so forth.

Your API key is sent on a per-request basis. You must supply your API key as an Authorization Bearer token with each request.

Below is an example of using an Authorization Bearer token.

{% tabs %}
{% tab title="Curl" %}
```
curl https://gosendee.com/api/sms/send
   -H "Accept: application/json"
   -H "Authorization: Bearer {token}"
```
{% endtab %}
{% endtabs %}
