---
id: flight-plans
title: Get Flight Plans
meta: Overview of the bulk flight plans endpoint of the Infinite Flight Live API
order: 8

---

# Get Flight Plans (Bulk)

Retrieve the detailed flight plans for up to 25 active flights in a single request. This is more efficient than calling the [Get Flight Plan](/guide/developer-reference/live-api/flight-plan) endpoint individually for each flight.

⚠️

: This API is intended for simulated flight only and must not be used in real-world flight situations.

## Resource

**POST** `https://api.infiniteflight.com/public/v2/sessions/{sessionId}/flights/flightplans`

## Authorization

Include your API key (`<apikey>`) by either:

- Adding the `apikey` query parameter. For example, `?apikey=<apikey>`.
- Sending a bearer authorization header with your API key. For example, `Authorization: Bearer <apikey>`.

## Parameters

| Name        | Located in | Description                                            | Required | Schema        |
| ----------- | ---------- | ------------------------------------------------------ | -------- | ------------- |
| `sessionId` | path       | ID of the session returned from the Sessions endpoint  | Yes      | string (uuid) |

## Body

Send a JSON object with an array of flight IDs to look up.

```json
{
  "flightIds": [
    "0b8cc273-d97d-4223-afac-907d09d8ca8b",
    "1c9dd384-e8e8-5334-bgbd-018e1e9db9bc"
  ]
}
```

| Name        | Type         | Description                                                                       | Required |
| ----------- | ------------ | --------------------------------------------------------------------------------- | -------- |
| `flightIds` | [string (uuid)] | Array of flight IDs to retrieve flight plans for. Maximum **10** IDs per request. | Yes      |

## Response

Results are returned in the same order as the requested `flightIds`. An entry is `null` if the corresponding flight has no filed flight plan or the flight ID was not found.

#### Sample Response

```json
{
  "errorCode": 0,
  "result": [
    {
      "flightPlanId": "4a57de08-a3b1-48ba-a081-adeff0a5b503",
      "flightId": "0b8cc273-d97d-4223-afac-907d09d8ca8b",
      "waypoints": [
        "AMAHE",
        "L12R"
      ],
      "lastUpdate": "2021-01-06 15:35:04Z",
      "flightPlanItems": [
        {
          "name": "AMAHE",
          "type": 0,
          "children": null,
          "identifier": null,
          "altitude": -1,
          "location": {
            "latitude": 26.92723722,
            "longitude": -77.47139889,
            "altitude": 0
          }
        }
      ],
      "flightPlanType": 1
    },
    null
  ]
}
```

#### LiveAPIResponse

*Response Type:* `application/json`

| Name        | Type                  | Description                                                  |
| ----------- | --------------------- | ------------------------------------------------------------ |
| `errorCode` | integer               | _Enum:_ `"Ok = 0"`, `"UserNotFound = 1"`, `"MissingRequestParameters = 2"`, `"EndpointError = 3"`, `"NotAuthorized = 4"`, `"ServerNotFound = 5"`, `"FlightNotFound = 6"`, `"NoAtisAvailable = 7"`, `"AirportNotFound = 8"`, `"ExceededMaximumRequestSize = 9"` |
| `result`    | [FlightPlanInfo\|null] | Array of FlightPlanInfo objects in the same order as requested. `null` for flights with no filed flight plan. |

#### FlightPlanInfo

| Name              | Type             | Description                                                  |
| ----------------- | ---------------- | ------------------------------------------------------------ |
| `flightPlanId`    | string (uuid)    | Unique identifier for the flight plan                        |
| `flightId`        | string (uuid)    | Unique identifier for the flight. Associate with the response from the Get Flights endpoint |
| `waypoints`       | [string]         | **Deprecated**. An array of waypoint names. You can correlate these with data from the [Airport Editing Project](https://github.com/infiniteflightairportediting/) |
| `lastUpdate`      | string           | Last report time of the flight plan in the following format: `YYYY-MM-DD HH:mm:ssZ` |
| `flightPlanItems` | [FlightPlanItem] | An array of FlightPlanItems which contain waypoint and procedure data for points in a flight plan. |
| `flightPlanType`  | integer          | Type of flight plan. *Enum:* `VFR = 0`, `IFR = 1`           |

#### FlightPlanItem

| Name         | Type             | Description                                                  |
| ------------ | ---------------- | ------------------------------------------------------------ |
| `name`       | string           | Name of the waypoint or the procedure. In the `children` array, this is the name of a waypoint inside a procedure. |
| `type`       | integer          | Type of procedure for this item. Only use this if the FlightPlanItem's `children` field is populated and not null. *Enum:* `"Sid = 0"`, `"STAR = 1"`, `"Approach = 2"`, `"Track = 3"`, `"Unknown = 5"` |
| `children`   | [FlightPlanItem] | An array of FlightPlanItems containing waypoint information about a procedure. Only present if this item defines a procedure (SID/STAR/Approach/Track). If not, assume this is a Fix/VOR/Custom User Waypoint. |
| `identifier` | string           | Identifier for the waypoint or the procedure. This is not unique. |
| `altitude`   | integer          | The altitude in feet for this waypoint. This is optionally defined by the user and defaults to `-1` if not set. |
| `location`   | Coordinate       | A Coordinate object defining the position of this waypoint.  |

#### Coordinate

| Name        | Type   | Description                               |
| ----------- | ------ | ----------------------------------------- |
| `latitude`  | double | Current decimal latitude of the aircraft  |
| `longitude` | double | Current decimal longitude of the aircraft |
| `altitude`  | double | Current decimal altitude of the aircraft  |
