---
id: sessions
title: Get Sessions
meta: Overview of the sessions endpoint of the Infinite Flight Live API
order: 2
---

# Get Sessions

Retrieve active sessions (servers) in Infinite Flight.

⚠️

: This API is intended for simulated flight only and must not be used in real-world flight situations.

## Resource

**GET** `https://api.infiniteflight.com/public/v2/sessions`

## Authorization

Include your API key (`<apikey>`) by either:

- Adding the `apikey` query parameter. For example, `?apikey=<apikey>`.
- Sending a bearer authorization header with your API key. For example, `Authorization: Bearer <apikey>`.

## Response

#### Sample Response

```json
{
  "errorCode": 0,
  "result": [
    {
      "maxUsers": 1000,
      "id": "89573c7f-d398-4281-bcc0-3e9b7f6b8492",
      "name": "Sample Server",
      "userCount": 187,
      "type": 0,
      "worldType": 0,
      "minimumGradeLevel": 2,
      "minimumAppVersion": "24.3",
      "maximumAppVersion": null
    }
  ]
}
```

#### LiveAPIResponse

*Response Type:* `application/json`

| Name        | Type          | Description                                                  |
| ----------- | ------------- | ------------------------------------------------------------ |
| `errorCode` | integer       | _Enum:_ `"Ok = 0"`, `"UserNotFound = 1"`, `"MissingRequestParameters = 2"`, `"EndpointError = 3"`, `"NotAuthorized = 4"`, `"ServerNotFound = 5"`, `"FlightNotFound = 6"`, `"NoAtisAvailable = 7"` |
| `result`    | [SessionInfo] | Array of SessionInfo objects                                 |

#### SessionInfo

| Name                | Type    | Description                                                  |
| ------------------- | ------- | ------------------------------------------------------------ |
| `id`                | string  | The unique identifier for the server. Use this to request flights and ATC data |
| `name`              | string  | Name of the server                                           |
| `maxUsers`          | integer | Maximum number of users the server can accept                |
| `userCount`         | integer | Connected users to the server                                |
| `type`              | integer | _Enum:_ `"Unrestricted = 0"`, `"Restricted = 1"`             |
| `worldType`         | integer | _Enum:_ `"Solo = 0"`, `"Casual = 1"`, `"Training = 2"`, `"Expert = 3"`, `"Private = 4"` |
| `minimumGradeLevel` | integer | Minimum grade index to access server. Add 1 to get grade name (i.e. index 0 is grade 1) |
| `minimumAppVersion` | string  | Minimum version of Infinite Flight able to connect to this server                       |
| `maximumAppVersion` | string  | Minimum version of Infinite Flight able to connect to this server                       |