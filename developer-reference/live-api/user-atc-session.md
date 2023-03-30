---
id: user-atc-session
title: Get User ATC Session
meta: Overview of the User ATC Session endpoint of the Infinite Flight Live API
order: 17
contributor: sqeezelemon
---

# Get User ATC Session

Retrieves an ATC session from the log of a given user.

⚠️ Important Notice

: This API is intended for simulated flight only and must not be used in real-world flight situations.

## Resource

**GET** `https://api.infiniteflight.com/public/v2/users/{userId}/atc/{atcSessionId}`

## Authorization

Include your API key (`<apikey>`) by either:

- Adding the `apikey` query parameter. For example, `?apikey=<apikey>`.
- Sending a bearer authorization header with your API key. For example, `Authorization: Bearer <apikey>`.

## Parameters

| Name     | Located in | Description    | Required | Schema        |
| -------- | ---------- | -------------- | -------- | ------------- |
| `userId` | path       | ID of the User | Yes      | string (uuid) |
| `atcSessionId` | path | ID of the ATC Session | Yes | string (uuid) |

## Response

#### Sample Response

```json
{
  "errorCode": 0,
  "result": {
    "id": "857b1686-455d-481a-8bdf-c46cd7711691",
    "atcSessionGroupId": "1fcff4cb-48e6-46dc-8c87-4202bcdd7cc0",
    "facility": {
        "id": "4fda33c2-91b9-1a57-98f2-a765abd4c019",
        "airportIcao": "VRMM",
        "latitude": 4.191753387451172,
        "longitude": 73.52915954589844,
        "frequencyType": 4
    },
    "created": "2020-07-03T10:27:08.021137",
    "updated": "2020-07-03T10:37:49.026714",
    "operations": 9,
    "totalTime": 86.15142588333333
  }
}
```

#### LiveAPIResponse

*Response Type:* `application/json`

| Name | Type | Description |
| -- | -- | -- |
| `errorCode` | integer | _Enum:_ `"Ok = 0"`, `"UserNotFound = 1"`, `"MissingRequestParameters = 2"`, `"EndpointError = 3"`, `"NotAuthorized = 4"`, `"ServerNotFound = 5"`, `"FlightNotFound = 6"`, `"NoAtisAvailable = 7"` |
| `result` | UserAtcSession | An ATC session from the logbook. |

#### UserAtcSession

| Name | Type | Description |
| -- | -- | -- |
| `id` | string (uuid) | The ID of the session |
| `atcSessionGroupId` | string (uuid) | Identifies a group of sessions (for when a controller opens multiple frequencies at the same airport) |
| `facility` | ATCFacility | Details of the facility that was opened |
| `created` | string (datetime) | The time at which the frequency was first opened |
| `updated` | string (datetime) | The time at which last report was received |
| `operations` | integer | The number of operations earned during the session |
| `totalTime` | double | The duration of the session in minutes |

#### ATCFacility

| Name | Type | Description |
| -- | -- | -- |
| `id` | string (uuid) | ID of the ATC Facility |
| `airportIcao` | string | The ICAO of the airport at which the facility is located |
| `latitude` | double | Latitude of the ATC Facility |
| `longitude` | double | Longitude of the ATC Facility |
| `frequencyType` | ATCEntityType | Type of ATC Facility. _Enum:_ `"Ground = 0"`, `"Tower = 1"`, `"Unicom = 2"`, `"Clearance = 3"`, `"Approach = 4"`, `"Departure = 5"`, `"Center = 6"`, `"ATIS = 7"`, `"Aircraft = 8"`, `"Recorded = 9"`, `"Unknown = 10"`, `"Unused = 11"` |