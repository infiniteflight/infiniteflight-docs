---
id: user-flights
title: Get User Flights
meta: Overview of the User Flights endpoint of the Infinite Flight Live API
order: 14
---

# Get User Flights

Retrieves the online flight logbook for a given user.

## Resource

**GET** `https://api.infiniteflight.com/public/v2/users/{userId}/flights`

## Authorization

Include your API key (`<apikey>`) by either:

- Adding the `apikey` query parameter. For example, `?apikey=<apikey>`.
- Sending a bearer authorization header with your API key. For example, `Authorization: Bearer <apikey>`.

## Parameters

| Name     | Located in | Description    | Required | Schema        |
| -------- | ---------- | -------------- | -------- | ------------- |
| `userId` | path       | ID of the User | Yes      | string (uuid) |
| `page`   | query      | Index of the page to retrieve | No, default `1` | integer |

## Response

#### Sample Response

```json
{
  "errorCode": 0,
  "result": {
    "pageIndex": 1,
    "totalPages": 80,
    "totalCount": 799,
    "hasPreviousPage": false,
    "hasNextPage": true,
    "data": [
      {
        "id": "9aeb16a3-ac69-41d3-9dd4-d62be72b1525",
        "created": "2022-01-10T10:37:41.965626",
        "userId": "b0018209-e010-40a0-afe1-00ecd5856c5e",
        "aircraftId": "849366e1-cb11-4d72-9034-78b11cd026b0",
        "liveryId": "a071518d-995a-4b3c-b65b-656da0d6ed86",
        "callsign": "VH-KAI",
        "server": "Casual Server",
        "dayTime": 2.5355167,
        "nightTime": 0,
        "totalTime": 2.5355167,
        "landingCount": 0,
        "originAirport": "YTYA",
        "destinationAirport": "YTYA",
        "xp": 25
      },
      ...
    ]
  }
}
```

#### LiveAPIResponse

*Response Type:* `application/json`

| Name | Type | Description |
| -- | -- | -- |
| `errorCode` | integer | _Enum:_ `"Ok = 0"`, `"UserNotFound = 1"`, `"MissingRequestParameters = 2"`, `"EndpointError = 3"`, `"NotAuthorized = 4"`, `"ServerNotFound = 5"`, `"FlightNotFound = 6"`, `"NoAtisAvailable = 7"` |
| `result` | PaginatedList | An array of tracks that are active in Infinite Flight. |

#### Paginated List

| Name | Type | Description |
| -- | -- | -- |
| `pageIndex` | integer | The index of the current page |
| `totalPages` | integer | The total number of pages available |
| `totalCount` | integer | The total amount of entries for this dataset |
| `hasPreviousPage` | boolean | Whether there is a page before this one |
| `hasNextPage` | boolean | Whether there is a page after this one |
| `data` | [UserFlight] | The entries in the current page |

#### UserFlight

| Name | Type | Description |
| -- | -- | -- |
| `id` | string (uuid) | The ID of the flight |
| `created` | string (datetime) | The time the flight was created |
| `userId` | string (uuid) | The ID of the user who flew the flight |
| `aircraftId` | string (uuid) | The ID of the aircraft flown |
| `liveryId` | string (uuid) | The ID of the livery flown. **This is currently only supported on the Casual server** |
| `callsign` | string | The callsign of the user during this flight |
| `server` | string | The name of the server the flight was flown on |
| `dayTime` | float | The flight time during the day, in minutes |
| `nightTime` | float | The flight time during the night, in minutes |
| `totalTime` | float | The total flight time of the flight, in minutes |
| `landingCount` | integer | The number of landings conducted during the flight |
| `originAirport` | string | The ICAO code of the departure airport |
| `destinationAirport` | string | The ICAO code of the arrival airport |
| `xp` | integer | The number of XP earned during the flight |
