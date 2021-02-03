---
id: all-flightplans
title: Get All Flight Plans (deprecated)
meta: Overview of the flight plans endpoint of the Infinite Flight Live API
order: 5
---

# Get All Flight Plans (deprecated)

Deprecated

: This API endpoint is deprecated and will be disabled soon. Please use the [Individual Flight Plan endpoint](/guide/developer-reference/live-api/all-flightplans)

Retrieve all active flight plans for a session.

## Response

#### Sample Response

```json
{
  "errorCode": 0,
  "result": [
    {
      "flightPlanId": "4efe9236-7ecd-4f2f-b061-22ff9f9de165",
      "flightId": "f90c4af7-218d-4b07-b4cc-6f4968b9b998",
      "waypoints": [
        "MERIT6",
        "ENE",
        "SCARS",
        "SEAER",
        "EBONY",
        "NEEKO",
        "Track Z",
        "SHA",
        "TOMTO",
        "TORLU",
        "SUTEX",
        "BUNED",
        "BEPAN",
        "BAKUR",
        "STU",
        "NUMPO",
        "OKESI",
        "BEDEK",
        "NIGIT",
        "VAPID",
        "MID",
        "SFD",
        "WAFFU",
        "HARDY",
        "XIDIL",
        "PETAX",
        "DPE",
        "LFPG"
      ],
      "lastUpdate": "2020-10-02 15:21:52Z"
    }
  ]
}
```

#### LiveAPIResponse

*Response Type:* `application/json`

| Name        | Type             | Description                                                  |
| ----------- | ---------------- | ------------------------------------------------------------ |
| `errorCode` | integer          | _Enum:_ `"Ok = 0"`, `"UserNotFound = 1"`, `"MissingRequestParameters = 2"`, `"EndpointError = 3"`, `"NotAuthorized = 4"`, `"ServerNotFound = 5"`, `"FlightNotFound = 6"`, `"NoAtisAvailable = 7"` |
| `result`    | [FlightPlanInfo] | Array of FlightPlanInfo objects                              |

#### FlightPlanInfo

| Name           | Type          | Description                                                  |
| -------------- | ------------- | ------------------------------------------------------------ |
| `flightPlanId` | string (uuid) | Unique identifier for the flight plan                        |
| `flightId`     | string (uuid) | Unique identifier for the flight. Associate with the response from the Get Flights endpoint |
| `waypoints`    | [string]      | An array of waypoint names. You can correlate these with data from the [Airport Editing Project](https://github.com/infiniteflightairportediting/) |
| `lastUpdate`   | string        | Last report time of the flight plan in the following format: `YYYY-MM-DD HH:mm:ssZ` |