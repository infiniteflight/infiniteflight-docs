---
id: atc
title: Get Active ATC Frequencies
meta: Overview of the ATC endpoint of the Infinite Flight Live API
order: 7
contributor: KaiM
---

# Get Active ATC Frequencies

Retrieve active Air Traffic Control frequencies for a session

## Resource

**GET** `https://api.infiniteflight.com/public/v2/atc/{sessionId}`

## Authorization

Include your API key (`<apikey>`) by either:

-   Adding the `apikey` query parameter. For example, `?apikey=<apikey>`.
-   Sending a bearer authorization header with your API key. For example, `Authorization: Bearer <apikey>`.

## Parameters

| Name        | Located in | Description                                           | Required | Schema        |
| ----------- | ---------- | ----------------------------------------------------- | -------- | ------------- |
| `sessionId` | path       | ID of the session returned from the Sessions endpoint | Yes      | string (uuid) |

## Response

#### Sample Response

```json
{
    "errorCode": 0,
    "result": [
        {
            "frequencyId": "c2d7decc-2803-c905-5d88-81bc07626b1f",
            "userId": "3f8b28bf-bbb1-4024-80ae-2a0ea9b30685",
            "username": "Cameron",
            "virtualOrganization": null,
            "airportName": "LEPA",
            "type": 1,
            "latitude": 39.551575,
            "longitude": 2.736811,
            "startTime": "2020-10-02 15:47:25Z"
        }
    ]
}
```

#### LiveAPIResponse

_Response Type:_ `application/json`

| Name        | Type                | Description                                                                                                                                                                                       |
| ----------- | ------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `errorCode` | integer             | _Enum:_ `"Ok = 0"`, `"UserNotFound = 1"`, `"MissingRequestParameters = 2"`, `"EndpointError = 3"`, `"NotAuthorized = 4"`, `"ServerNotFound = 5"`, `"FlightNotFound = 6"`, `"NoAtisAvailable = 7"` |
| `result`    | [ActiveATCFacility] | Array of ActiveATCFacility objects                                                                                                                                                                |

#### ActiveATCFacility

| Name                  | Type          | Description                                                                                                                                                                                                                                                                    |
| --------------------- | ------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `frequencyId`         | string (uuid) | Unique identifier for the open frequency                                                                                                                                                                                                                                       |
| `userId`              | string (uuid) | Unique identifier for the user controlling the frequency                                                                                                                                                                                                                       |
| `username`            | string        | The user's forum username if the account is linked. If the account isn't linked, this will be null                                                                                                                                                                             |
| `virtualOrganization` | string        | _(not currently in use)_                                                                                                                                                                                                                                                       |
| `airportName`         | string        | The 4-character ICAO identifier for the airport                                                                                                                                                                                                                                |
| `type`                | integer       | The type of frequency opened - not all of these are in use. _Enum:_ `"Ground = 0"`, `"Tower = 1"`, `"Unicom = 2"`, `"Clearance = 3"`, `"Approach = 4"`, `"Departure = 5"`, `"Center = 6"`, `"ATIS = 7"`, `"Aircraft = 8"`, `"Recorded = 9"`, `"Unknown = 10"`, `"Unused = 11"` |
| `latitude`            | float         | Decimal latitude of the airport                                                                                                                                                                                                                                                |
| `longitude`           | float         | Decimal longitude of the airport                                                                                                                                                                                                                                               |
| `startTime `          | string        | Time at which the frequency was opened, in the following format: `YYYY-MM-DD HH:mm:ssZ`                                                                                                                                                                                        |
