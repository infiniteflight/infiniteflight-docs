---
id: aircraft-liveries
title: Get Aircraft Liveries
meta: Overview of the Aircraft Liveries endpoint of the Infinite Flight Live API
order: 20
---

# Get Aircraft

Retrieve a list of all liveries for an aircraft model.

⚠️

: This API is intended for simulated flight only and must not be used in real-world flight situations.


## Resource

**GET** `https://api.infiniteflight.com/public/v2/aircraft/{aircraftId}/liveries`

## Authorization

Include your API key (`<apikey>`) by either:

- Adding the `apikey` query parameter. For example, `?apikey=<apikey>`.
- Sending a bearer authorization header with your API key. For example, `Authorization: Bearer <apikey>`.

## Parameters

| Name         | Located in | Description                                                  | Required | Schema        |
| ------------ | ---------- | ------------------------------------------------------------ | -------- | ------------- |
| `aircraftId` | path       | ID of the aircraft model returned from the aircraft endpoint | Yes      | string (uuid) |

## Response

#### Sample Response

```json
{
  "errorCode": 0,
  "result": [
    {
      "id": "701c826b-a160-4b1a-a89f-08d0afb4af1b",
      "aircraftID": "710c84ae-6fdc-4c4a-ac3b-4031c3036e98",
      "aircraftName": "Airbus A220-300",
      "liveryName": "airBaltic"
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