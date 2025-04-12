---
id: flight-route
title: Get Flight Route
meta: Overview of the flight route endpoint of the Infinite Flight Live API
order: 5
---

# Get Flight Route

Retrieve the flown route of a specific flight with position, altitude, speed and track information at different points in time.

Please note, this is currently only supported on the Expert Server and Training Server.

⚠️

: This API is intended for simulated flight only and must not be used in real-world flight situations.

## Resource

**GET** `https://api.infiniteflight.com/public/v2/sessions/{sessionId}/flights/{flightId}/route`

## Authorization

Include your API key (`<apikey>`) by either:

- Adding the `apikey` query parameter. For example, `?apikey=<apikey>`.
- Sending a bearer authorization header with your API key. For example, `Authorization: Bearer <apikey>`.

## Parameters

| Name       | Located in | Description                                                | Required | Schema        |
| ---------- | ---------- | ---------------------------------------------------------- | -------- | ------------- |
| `sessionId` | path       | ID of the session returned from the Sessions endpoint | Yes      | string (uuid) |
| `flightId` | path       | ID of the flight. The flight must be in an active session. | Yes      | string (uuid) |

## Response

#### Sample Response

```json
{
  "errorCode": 0,
  "result": [
    {
      "latitude": 25.52992361245416,
      "longitude": -80.33701239710909,
      "altitude": 18429.91132829714,
      "track": 75.00002,
      "groundSpeed": 194.6716372048416,
      "date": "2021-01-06T16:20:27.3275657Z"
    },
    {
      "latitude": 25.59595843191219,
      "longitude": -79.96882929194611,
      "altitude": 27448.993829140254,
      "track": 77.0936,
      "groundSpeed": 229.58654094765924,
      "date": "2021-01-06T16:23:27.4572883Z"
    },
    {
      "latitude": 25.621774462118506,
      "longitude": -79.56246802075516,
      "altitude": 30999.01751208178,
      "track": 110.30767,
      "groundSpeed": 235.4484678810845,
      "date": "2021-01-06T16:26:27.5268907Z"
    }
  ]
}
```

#### LiveAPIResponse

*Response Type:* `application/json`

| Name        | Type             | Description                                                  |
| ----------- | ---------------- | ------------------------------------------------------------ |
| `errorCode` | integer          | _Enum:_ `"Ok = 0"`, `"UserNotFound = 1"`, `"MissingRequestParameters = 2"`, `"EndpointError = 3"`, `"NotAuthorized = 4"`, `"ServerNotFound = 5"`, `"FlightNotFound = 6"`, `"NoAtisAvailable = 7"` |
| `result`    | [PositionReport] | Array of PositionReport objects                              |

#### PositionReport

| Name          | Type   | Description                                                  |
| ------------- | ------ | ------------------------------------------------------------ |
| `latitude`    | double | Decimal latitude of the aircraft at this position.           |
| `longitude`   | double | Decimal longitude of the aircraft at this position.          |
| `altitude`    | double | Altitude of the aircraft in feet.                            |
| `track`       | double | Track / Course of aircraft in degrees                        |
| `groundSpeed` | double | Ground speed of the aircraft in knots                        |
| `date`        | string | Position report time of the flight in the following format: `YYYY-MM-DD HH:mm:ssZ` |