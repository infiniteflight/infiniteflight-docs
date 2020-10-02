---
id: get-atc
title: Get Active ATC Frequencies
meta: Overview of the ATC endpoint of the Infinite Flight Live API
order: 5

---

# Get Active ATC Frequencies

Retrieve active Air Traffic Control frequencies for a session



## Resource

**GET** `https://api.infiniteflight.com/public/v2/atc/{sessionId}`



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

*Response Type:* `application/json`

| Name        | Type                | Description                                                  |
| ----------- | ------------------- | ------------------------------------------------------------ |
| `errorCode` | integer             | _Enum:_ `"Ok = 0"`, `"UserNotFound = 1"`, `"MissingRequestParameters = 2"`, `"EndpointError = 3"`, `"NotAuthorized = 4"`, `"ServerNotFound = 5"` |
| `result`    | [ActiveATCFacility] | Array of ActiveATCFacility objects                           |



#### ActiveATCFacility

| Name                  | Type          | Description                                                  |
| --------------------- | ------------- | ------------------------------------------------------------ |
| `frequencyId`         | string (uuid) | Unique identifier for the open frequency                     |
| `userId`              | string (uuid) | Unique identifier for the user controlling the frequency     |
| `username`            | string        | The user's forum username if the account is linked. If the account isn't linked, this will be null |
| `virtualOrganization` | string        | *(not currently in use)*                                     |
| `airportName`         | string        | The 4-character ICAO identifier for the airport              |
| `type`                | integer       | The type of frequency opened - not all of these are in use. *Enum:* `"Unknown = 0"`, `"Unused = 1"`, `"Recorded = 2"`, `"Unicom = 3"`, `"ClearanceDelivery = 4"`, `"Ground = 5"`, `"Tower = 6"`, `"Approach = 7"`, `"Departure = 8"`, `"Nav = 9"`, `"Ndb = 10"`, `"Center = 11"` |
| `latitude`            | float         | Decimal latitude of the airport                              |
| `longitude`           | float         | Decimal longitude of the airport                             |
| `startTime `          | string        | Time at which the frequency was opened, in the following format: `YYYY-MM-DD HH:mm:ssZ` |