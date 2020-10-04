---
id: get-flights
title: Get Flights
meta: Overview of the flights endpoint of the Infinite Flight Live API
order: 3
---

# Get Flights

Retrieve a list of all flights for a session.



## Resource

**GET** `https://api.infiniteflight.com/public/v2/flights/{sessionId}`



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
      "username": "Cameron",
      "callsign": "EC-CAM",
      "latitude": 30.123479009207056,
      "longitude": 31.413340256981044,
      "altitude": 597.8003749797689,
      "speed": 185.3844049009562,
      "verticalSpeed": 2167.31591796875,
      "track": 162.13836669921875,
      "lastReport": "2020-10-02 00:46:19Z",
      "flightId": "348d1ba8-1e60-48ca-8278-42f019147de8",
      "userId": "3f8b28bf-bbb1-4024-80ae-2a0ea9b30685",
      "aircraftId": "de510d3d-04f8-46e0-8d65-55b888f33129",
      "liveryId": "c875c0e9-19c2-420d-8fb4-32c151bd797c",
      "heading": 159.33542,
      "virtualOrganization": "IFATC [IFATC]"
    }
  ]
}
```



#### LiveAPIResponse

*Response Type:* `application/json`

| Name        | Type          | Description                                                  |
| ----------- | ------------- | ------------------------------------------------------------ |
| `errorCode` | integer       | _Enum:_ `"Ok = 0"`, `"UserNotFound = 1"`, `"MissingRequestParameters = 2"`, `"EndpointError = 3"`, `"NotAuthorized = 4"`, `"ServerNotFound = 5"` |
| `result`    | [FlightEntry] | Array of FlightEntry objects                                 |



#### FlightEntry

| Name                  | Type          | Description                                                  |
| --------------------- | ------------- | ------------------------------------------------------------ |
| `flightId`            | string (uuid) | Unique identifier for the flight                             |
| `userId`              | string (uuid) | Unique identifier for the user                               |
| `aircraftId`          | string (uuid) | Unique identifier for the aircraft type                      |
| `liveryId`            | string (uuid) | Unique identifier for the livery and aircraft combination    |
| `username`            | string        | The user's forum username if the account is linked. If the account isn't linked, this will be null |
| `virtualOrganization` | string        | The virtual organization of the user's forum account if linked. Can be null if not set |
| `callsign`            | string        | Callsign for the flight                                      |
| `latitude`            | double        | Current decimal latitude of the aircraft                     |
| `longitude`           | double        | Current decimal longitude of the aircraft                    |
| `altitude`            | double        | Current altitude of the aircraft in feet                     |
| `speed`               | double        | Current groundspeed of the aircraft in knots                 |
| `verticalSpeed`       | double        | Current vertical speed of the aircraft in ft/min             |
| `track`               | double        | Track of the aircraft in degrees                             |
| `heading`             | float         | Heading of the aircraft in degrees                           |
| `lastReport`          | string        | Last position report time of the flight in the following format: `YYYY-MM-DD HH:mm:ssZ` |