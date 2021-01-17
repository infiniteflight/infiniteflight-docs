---
id: oceanic-tracks
title: Get Oceanic Tracks
meta: Overview of the Oceanic Tracks endpoint of the Infinite Flight Live API
order: 10
---

# Get Oceanic Tracks

Retrieves a list of Oceanic Tracks active in Infinite Flight multiplayer sessions.

## Resource

**GET** `https://api.infiniteflight.com/public/v2/airport/{airportIcao}/atis/{serverId}`

## Authorization

Include your API key (`<apikey>`) by either:

- Adding the `apikey` query parameter. For example, `?apikey=<apikey>`.
- Sending a bearer authorization header with your API key. For example, `Authorization: Bearer <apikey>`.

## Parameters

*No parameters required.*

## Response

#### Sample Response

```json
{
  "errorCode": 0,
  "result": [
    {
      "name": "A",
      "path": [
        "DINIM",
        "51/20",
        "51/30",
        "50/40",
        "49/50",
        "JOOPY"
      ],
      "eastLevels": null,
      "westLevels": [
        350,
        370,
        390
      ],
      "type": "North Atlantic Tracks",
      "lastSeen": "2021-01-06T18:49:33.6300772Z"
    }
  ]
}
```

#### LiveAPIResponse

*Response Type:* `application/json`

| Name        | Type           | Description                                                  |
| ----------- | -------------- | ------------------------------------------------------------ |
| `errorCode` | integer        | _Enum:_ `"Ok = 0"`, `"UserNotFound = 1"`, `"MissingRequestParameters = 2"`, `"EndpointError = 3"`, `"NotAuthorized = 4"`, `"ServerNotFound = 5"`, `"FlightNotFound = 6"`, `"NoAtisAvailable = 7"` |
| `result`    | [OceanicTrack] | An array of tracks that are active in Infinite Flight.       |

#### OceanicTrack

| Name         | Type      | Description                                                  |
| ------------ | --------- | ------------------------------------------------------------ |
| `name`       | string    | Name of the track. This is normally represented by letters.  |
| `path`       | [string]  | You can correlate these with data from the [Airport Editing Project](https://github.com/infiniteflightairportediting/) |
| `eastLevels` | [integer] | An array of Flight Level altitudes that aircraft can fly eastbound on using this track. |
| `westLevels` | [integer] | An array of Flight Level altitudes that aircraft can fly westbound on using this track. |
| `type`       | string    | Type of Oceanic Track. Infinite Flight supports `North Atlantic Tracks` in addition to custom tracks defined for events. |
| `lastSeen`   | string    | Last date and time at which the Oceanic Tracks were updated, in the following format: `YYYY-MM-DDTHH:mm:ssZ` |

