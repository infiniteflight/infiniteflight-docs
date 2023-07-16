---
id: aircraft
title: Get Aircraft
meta: Overview of the Aircraft endpoint of the Infinite Flight Live API
order: 19
---

# Get Aircraft

Retrieve a list of all aircraft models.

⚠️

: This API is intended for simulated flight only and must not be used in real-world flight situations.

## Resource

**GET** `https://api.infiniteflight.com/public/v2/aircraft`

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
      "id": "81d9ccd4-9c03-493a-811e-8fad3e57bd05",
      "name": "A-10"
    },
    ...
  ]
}
```

#### LiveAPIResponse

*Response Type:* `application/json`

| Name        | Type          | Description                                                  |
| ----------- | ------------- | ------------------------------------------------------------ |
| `errorCode` | integer       | _Enum:_ `"Ok = 0"`, `"UserNotFound = 1"`, `"MissingRequestParameters = 2"`, `"EndpointError = 3"`, `"NotAuthorized = 4"`, `"ServerNotFound = 5"`, `"FlightNotFound = 6"`, `"NoAtisAvailable = 7"` |
| `result`    | [AircraftPackage] | Array of AircraftPackage objects                                 |

#### AircraftPacakge

| Name   | Type          | Description                     |
| ------ | ------------- | ------------------------------- |
| `id`   | string (uuid) | Unique identifier for the model |
| `name` | string        | Name of the aircraft            |