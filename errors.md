# Errors

Sendee uses HTTP response codes to indicate the success or failure of an API request.  Codes in the `2xx` range indicate success, whereas codes in the `4xx` or `5xx` range typically indicate an error.

#### HTTP Status Codes

| **200 - OK**                           | Everything worked as expected                                |
| -------------------------------------- | ------------------------------------------------------------ |
| **403 - Forbidden**                    | The API key doesn't have permissions to perform the request. |
| **404 - Not Found**                    | The requested resource doesn't exist.                        |
| **429 - Too Many Requests**            | Too many request hit the API too quickly.                    |
| **500, 502, 503, 504 - Server Errors** | Something went wrong on Sendee's end. (These are rare.)      |
