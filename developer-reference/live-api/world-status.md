---
id: world-status
title: Get World Status
meta: Overview of the World Status endpoint of the Infinite Flight Live API
order: 12
---

# Get World Status

Retrieve active ATC status information and inbound/outbound aircraft information for all airports with activity on a specific server.

## Resource

**GET** `https://api.infiniteflight.com/public/v2/sessions/{sessionId}/world`

## Authorization

Include your API key (`<apikey>`) by either:

- Adding the `apikey` query parameter. For example, `?apikey=<apikey>`.
- Sending a bearer authorization header with your API key. For example, `Authorization: Bearer <apikey>`.

## Parameters

| Name        | Located in | Description                            | Required | Schema        |
| ----------- | ---------- | -------------------------------------- | -------- | ------------- |
| `sessionId` | query      | Session (Server) ID of the Live Server | Yes      | string (uuid) |

## Response

#### Sample Response

```json
{
  "errorCode": 0,
  "result": [
    {
      "airportIcao": "KLAX",
      "inboundFlightsCount": 103,
      "inboundFlights": [
        "e1cf6c27-6f18-43a0-8bf8-cec5406e93a0",
        ...
      ],
      "outboundFlightsCount": 39,
      "outboundFlights": [
        "e2ded8f8-ff70-454a-911b-f193eb47636f",
        ...
      ],
      "atcFacilities": [
        {
          "frequencyId": "ee835f12-6cf5-eaa1-04bf-2018c7c01ae0",
          "userId": "51f94d83-54e8-4674-ae2d-046a42c04f7a",
          "username": "Manav_Suri",
          "virtualOrganization": null,
          "airportName": "KLAX",
          "type": 0,
          "latitude": 33.943123,
          "longitude": -118.40881,
          "startTime": "2021-02-09 09:53:02Z"
        },
        ...
      ]
    },
  ]
}
```

#### LiveAPIResponse

*Response Type:* `application/json`

| Name        | Type            | Description                                                  |
| ----------- | --------------- | ------------------------------------------------------------ |
| `errorCode` | integer         | _Enum:_ `"Ok = 0"`, `"UserNotFound = 1"`, `"MissingRequestParameters = 2"`, `"EndpointError = 3"`, `"NotAuthorized = 4"`, `"ServerNotFound = 5"`, `"FlightNotFound = 6"`, `"NoAtisAvailable = 7"` |
| `result`    | [AirportStatus] | An array of `AirportStatus` objects                          |

#### AirportStatus

| Name                   | Type                | Description                                                  |
| ---------------------- | ------------------- | ------------------------------------------------------------ |
| `airportIcao`          | string              | ICAO of the airport                                          |
| `inboundFlightsCount`  | integer             | Number of aircraft inbound to this airport (must have final waypoint in flight plan set as the airport ICAO) |
| `inboundFlights`       | [string (uuid)]     | A list of flight identifiers inbound to this airport. Use this to get flight plans or flight route information |
| `outboundFlightsCount` | integer             | Number of aircraft departing this airport (must have first waypoint in flight plan set as the airport ICAO) |
| `outboundFlights`      | [string (uuid)]     | A list of flight identifiers outbound from this airport. Use this to get flight plans or flight route information |
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