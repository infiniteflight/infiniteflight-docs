---
id: flight-plan
title: Get Flight Plan
meta: Overview of the flight plan endpoint of the Infinite Flight Live API
order: 5

---

# Get Detailed Flight Plan

Retrieve the flight plan for a specific active flight.

## Resource

**GET** `https://api.infiniteflight.com/public/v2/flight/{flightId}/flightplan`

## Authorization

Include your API key (`<apikey>`) by either:

- Adding the `apikey` query parameter. For example, `?apikey=<apikey>`.
- Sending a bearer authorization header with your API key. For example, `Authorization: Bearer <apikey>`.

## Parameters

| Name       | Located in | Description                                                  | Required | Schema        |
| ---------- | ---------- | ------------------------------------------------------------ | -------- | ------------- |
| `flightId` | path       | ID of the flight. The flight must be in an active session and have a filed flight plan. | Yes      | string (uuid) |

## Response

#### Sample Response

```json
{
  "errorCode": 0,
  "result": {
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
            "longitude": -77.47139889
          }
        },
        {
          "name": "L12R",
          "type": 2,
          "children": [
            {
              "name": "ZESTY",
              "type": 0,
              "children": null,
              "identifier": "ZESTY",
              "altitude": 4000,
              "location": {
                "latitude": 44.97196917,
                "longitude": -93.429735
              }
            },
            {
              "name": "RW12R",
              "type": 0,
              "children": null,
              "identifier": "RW12R",
              "altitude": -1,
              "location": {
                "latitude": 44.887794494628906,
                "longitude": -93.23413848876953
              }
            }
          ],
          "identifier": "L12R",
          "altitude": 0,
          "location": {
            "latitude": 0,
            "longitude": 0
          }
        }
      ]
    }
}
```

#### LiveAPIResponse

*Response Type:* `application/json`

| Name        | Type             | Description                                                  |
| ----------- | ---------------- | ------------------------------------------------------------ |
| `errorCode` | integer          | _Enum:_ `"Ok = 0"`, `"UserNotFound = 1"`, `"MissingRequestParameters = 2"`, `"EndpointError = 3"`, `"NotAuthorized = 4"`, `"ServerNotFound = 5"`, `"FlightNotFound = 6"`, `"NoAtisAvailable = 7"` |
| `result`    | [FlightPlanInfo] | Array of FlightPlanInfo objects                              |

#### FlightPlanInfo

| Name              | Type             | Description                                                  |
| ----------------- | ---------------- | ------------------------------------------------------------ |
| `flightPlanId`    | string (uuid)    | Unique identifier for the flight plan                        |
| `flightId`        | string (uuid)    | Unique identifier for the flight. Associate with the response from the Get Flights endpoint |
| `waypoints`       | [string]         | **Deprecated**. An array of waypoint names. You can correlate these with data from the [Airport Editing Project](https://github.com/infiniteflightairportediting/) |
| `lastUpdate`      | string           | Last report time of the flight plan in the following format: `YYYY-MM-DD HH:mm:ssZ` |
| `flightPlanItems` | [FlightPlanItem] | An array of FlightPlanItems which contain waypoint and procedure data for points in a flight plan. |

#### FlightPlanItem

| Name         | Type             | Description                                                  |
| ------------ | ---------------- | ------------------------------------------------------------ |
| `name`       | string           | Name of the waypoint or the procedure. In the `children` array, this is the name of a waypoint inside a procedure. |
| `type`       | integer          | Type of procedure for this item., Only use this if the FlightPlanItem's `children` field is populated and not null. *Enum:* `"Sid = 0"`, `"STAR = 1"`,  `"Approach = 2"`, `"Track = 3"`, `"Unknown = 5"` |
| `children`   | [FlightPlanItem] | An array of FlightPlanItems containing waypoint information about a procedure. Only present if this item defines a procedure (SID/STAR/Approach/Track). If not, assume this is a Fix/VOR/Custom User Waypoint. |
| `identifier` | string           | Identifier for the waypoint or the procedure. This is not unique. |
| `altitude`   | integer          | The altitude in feet for this waypoint. This is optionally defined by the user and defaults to `-1` if not set. |
| `location`   | Coordinate       | A Coordinate object defining the position of this waypoint.  |

#### Coordinate

| Name        | Type   | Description                               |
| ----------- | ------ | ----------------------------------------- |
| `latitude`  | double | Current decimal latitude of the aircraft  |
| `longitude` | double | Current decimal longitude of the aircraft |