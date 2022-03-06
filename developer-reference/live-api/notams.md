---
id: notams
title: Get NOTAMs
meta: Overview of the NOTAMs endpoint of the Infinite Flight Live API
order: 18
---

# Get NOTAMs

Retrieve a list of all NOTAMs for a session.

## Resource

**GET** `https://api.infiniteflight.com/public/v2/sessions/{sessionId}/notams`

## Authorization

Include your API key (`<apikey>`) by either:

- Adding the `apikey` query parameter. For example, `?apikey=<apikey>`.
- Sending a bearer authorization header with your API key. For example, `Authorization: Bearer <apikey>`.

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
      "id": "53671e16-f937-47ca-a5db-c13b6a882851",
      "title": "Special Airport Procedures",
      "author": "Infinite Flight",
      "type": 0,
      "sessionId": "7e5dcd44-1fb5-49cc-bc2c-a9aab1f6a856",
      "radius": 3,
      "message": "Special Airport Procedures in Effect:\n\nNo straight in approached allowed RWY 13\n\nCC NDB 4500ft - 040° HDG Descending to SC NDB - Visual Right Turn Abeam Checkerboard to RWY 13\n\nPublished Approach Procedures (Found Online) Recommended",
      "longitude": 114.20680199460077,
      "latitude": 22.31646633312086,
      "icao": "VHHX",
      "floor": 0,
      "ceiling": 10000,
      "startTime": "2022-02-14T16:34:14.916",
      "endTime": "2100-01-01T16:34:00"
    },
    ...
  ]
}
```

#### LiveAPIResponse

*Response Type:* `application/json`

| Name        | Type          | Description                                                  |
| ----------- | ------------- | ------------------------------------------------------------ |
| `errorCode` | integer       | _Enum:_ `"Ok = 0"`, `"UserNotFound = 1"`, `"MissingRequestParameters = 2"`, `"EndpointError = 3"`, `"NotAuthorized = 4"`, `"ServerNotFound = 5"`, `"FlightNotFound = 6"`, `"NoAtisAvailable = 7"` |
| `result`    | [NotamResult] | Array of FlightEntry objects                                 |

#### NotamResult

| Name                  | Type          | Description                                                  |
| --------------------- | ------------- | ------------------------------------------------------------ |
| `id`            | string (uuid) | Unique identifier for the NOTAM                             |
| `title`              | string | Short title for NOTAM                               |
| `author`          | string | Name of NOTAM author                      |
| `type`            | NotamType | Type of NOTAM. _Enum:_ `"NOTAM" = 0, "TFR" = 1`    |
| `sessionId`            | string (uuid)        | The ID of the session on which the NOTAM is published. `null` for all sessions. |
| `radius` | float        | The radius of the radius in NM |
| `message`            | string        | Main message for NOTAM                                      |
| `latitude`            | double        | Decimal latitude of the center of the NOTAM                     |
| `longitude`           | double        | Decimal longitude of the center of the NOTAM                    |
| `icao`            | string        | ICAO of the nearest airport to the NOTAM                     |
| `floor`               | integer        | Lowest altitude of NOTAM in feet                 |
| `ceiling`       | integer        | Highest altitude of NOTAM in feet             |
| `startTime`               | string (datetime)        | Time at which the NOTAM comes into effect                             |
| `endTime`             | string (datetime)         | Time at which the NOTAM expires                           |