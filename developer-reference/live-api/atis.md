---
id: atis
title: Get ATIS
meta: Overview of the ATIS endpoint of the Infinite Flight Live API
order: 11
contributor: KaiM
---

# Get Airport ATIS

Retrieve the ATIS for an airport on a specific server if it is active.

⚠️

: This API is intended for simulated flight only and must not be used in real-world flight situations.

## Resource

**GET** `https://api.infiniteflight.com/public/v2/sessions/{sessionId}/airport/{airportIcao}/atis`

## Authorization

Include your API key (`<apikey>`) by either:

- Adding the `apikey` query parameter. For example, `?apikey=<apikey>`.
- Sending a bearer authorization header with your API key. For example, `Authorization: Bearer <apikey>`.

## Parameters

| Name          | Located in | Description                             | Required | Schema        |
| ------------- | ---------- | --------------------------------------- | -------- | ------------- |
| `airportIcao` | query      | ICAO of the airport to get the ATIS for | Yes      | string        |
| `sessionId`   | query      | Session (Server) ID of the Live Server  | Yes      | string (uuid) |

## Response

#### Sample Response

```json
{
    "errorCode":0,
    "result":"Manchester Airport, ATIS information DELTA, time 2355 ZULU, Wind 350 at 6 Visibility 21, Temperature 2, Dew Point 0, QNH 1024. Remarks, no pattern work allowed, no light aircraft accepted at this time. Landing Runways 05L and 05R, Departing Runways 05L and 05R. Advise on initial contact, you have information DELTA."
}
```

#### LiveAPIResponse

*Response Type:* `application/json`

| Name        | Type    | Description                                                  |
| ----------- | ------- | ------------------------------------------------------------ |
| `errorCode` | integer | _Enum:_ `"Ok = 0"`, `"UserNotFound = 1"`, `"MissingRequestParameters = 2"`, `"EndpointError = 3"`, `"NotAuthorized = 4"`, `"ServerNotFound = 5"`, `"FlightNotFound = 6"`, `"NoAtisAvailable = 7"` |
| `result`    | string  | The ATIS, or `null` if it is not available                   |