---
id: liveries
title: Get All Liveries
meta: Overview of the All Liveries endpoint of the Infinite Flight Live API
order: 21
---

# Get All Liveries

Retrieve a list of all aircraft liveries.

## Resource

**GET** `https://api.infiniteflight.com/public/v2/aircraft/liveries`

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
      "id": "1d7dff42-46a5-4c47-a46c-bd39ab9cea8d",
      "aircraftID": "982dd974-5be7-4369-90c6-bd92863632ba",
      "aircraftName": "Airbus A318",
      "liveryName": "Generic"
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
| `result`    | [LiveryData] | Array of LiveryData objects                                 |

#### LiveryData

| Name           | Type          | Description                      |
| -------------- | ------------- | -------------------------------- |
| `id`           | string (uuid) | Unique identifier for the livery |
| `aircraftID`   | string (uuid) | ID of the aircraft model         |
| `aircraftName` | string        | Name of the aircraft model       |
| `liveryName`   | string        | Name of the livery               |