---
id: airport-status
title: Get Airport Status
meta: Overview of the Airport Status endpoint of the Infinite Flight Live API
order: 11
---

# Get Airport Status

Retrieve the ATIS for an airport on a specific server if it is active.

## Resource

**GET** `https://api.infiniteflight.com/public/v2/airport/{airportIcao}/status/{serverId}`

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
  "errorCode": 0,
  "result": {
    "airportIcao": "VTBS",
    "arrivalAircraftCount": 42,
    "departureAircraftCount": 26,
    "atcFacilities": [
      {
        "frequencyId": "23bea566-20a0-2858-a40e-179d0699afc1",
        "userId": "05328fc4-b651-45e9-8e1f-328095329484",
        "username": "Rhys_V",
        "virtualOrganization": null,
        "airportName": "VTBS",
        "type": 4,
        "latitude": 13.680815,
        "longitude": 100.74768,
        "startTime": "2021-02-08 09:59:58Z"
      }
    ]
  }
}
```

#### LiveAPIResponse

*Response Type:* `application/json`

| Name        | Type    | Description                                                  |
| ----------- | ------- | ------------------------------------------------------------ |
| `errorCode` | integer | _Enum:_ `"Ok = 0"`, `"UserNotFound = 1"`, `"MissingRequestParameters = 2"`, `"EndpointError = 3"`, `"NotAuthorized = 4"`, `"ServerNotFound = 5"`, `"FlightNotFound = 6"`, `"NoAtisAvailable = 7"` |
| `result`    | string  | An `AirportStatus` object                                    |

#### Airport Status

| Name                   | Type                | Description                                                  |
| ---------------------- | ------------------- | ------------------------------------------------------------ |
| `airportIcao`          | string              | ICAO of the airport                                          |
| `arrivalAircraftCount` | integer             | Number of aircraft inbound to this airport (must have final waypoint in flight plan set as the airport ICAO) |
| `username`             | integer             | Number of aircraft departing this airport (must have first waypoint in flight plan set as the airport ICAO) |
| `atcFacilities`        | [ActiveATCFacility] | Array of ActiveATCFacility objects                           |

#### ActiveATCFacility

| Name                  | Type          | Description                                                  |
| --------------------- | ------------- | ------------------------------------------------------------ |
| `frequencyId`         | string (uuid) | Unique identifier for the open frequency                     |
| `userId`              | string (uuid) | Unique identifier for the user controlling the frequency     |
| `username`            | string        | The user's forum username if the account is linked. If the account isn't linked, this will be null |
| `virtualOrganization` | string        | *(not currently in use)*                                     |
| `airportName`         | string        | The 4-character ICAO identifier for the airport              |
| `type`                | integer       | The type of frequency opened - not all of these are in use. *Enum:* `"Ground = 0"`, `"Tower = 1"`, `"Unicom = 2"`, `"Clearance = 3"`, `"Approach = 4"`, `"Departure = 5"`, `"Center = 6"`, `"ATIS = 7"`, `"Aircraft = 8"`, `"Recorded = 9"`, `"Unknown = 10"`, `"Unused = 11"` |
| `latitude`            | float         | Decimal latitude of the airport                              |
| `longitude`           | float         | Decimal longitude of the airport                             |
| `startTime `          | string        | Time at which the frequency was opened, in the following format: `YYYY-MM-DD HH:mm:ssZ` |