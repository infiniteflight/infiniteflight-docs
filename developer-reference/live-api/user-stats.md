---
id: user-stats
title: Get User Stats
meta: Overview of the user stats endpoint of the Infinite Flight Live API
order: 7

---

# Get User Stats

Retrieve user statistics for multiple users, including their grade, flight time and username.

## Resource

**POST** `https://api.infiniteflight.com/public/v2/user/stats`

## Authorization

Include your API key (`<apikey>`) by either:

- Adding the `apikey` query parameter. For example, `?apikey=<apikey>`.
- Sending a bearer authorization header with your API key. For example, `Authorization: Bearer <apikey>`.

## Parameters

*Request Content-Type:* `application/json`

| Name             | Located in        | Description                                                  | Required | Schema          |
| ---------------- | ----------------- | ------------------------------------------------------------ | -------- | --------------- |
| `userIds`        | POST request body | An array of user ID strings retrieved from another endpoint  | No\*     | [string (uuid)] |
| `discourseNames` | POST request body | An array of IFC Usernames. Not case sensitive.               | No\*     | [string]        |
| `userHashes`     | POST request body | An array of user hashes retrieved in-app or from another endpoint. All letters must be upper case. | No\*     | [string]        |

*\*At least one search parameter is required*

#### Sample Body

```json
{
  "userIds": [
    "2a11e620-1cc1-4ac6-90d1-18c4ed9cb913",
    "5917d076-88a5-40e7-95e0-8818748f8e99"
  ],
  "discourseNames": [
      "KaiM",
      "Laura"
  ],
  "userHashes": [
      "F0081CAA",
      "E2087C9F"
  ],
}
```

## Response

#### Sample Response

```json
{
  "errorCode": 0,
  "result": [
    {
      "onlineFlights": 2449,
      "violations": 102,
      "xp": 572128,
      "landingCount": 898,
      "flightTime": 45983,
      "atcOperations": 548,
      "atcRank": 7,
      "grade": 5,
      "hash": "5F0973A9",
      "violationCountByLevel": {
        "level1": 102,
        "level2": 0,
        "level3": 0
      },
      "roles": [
        1,
        2,
        64
      ],
      "userId": "2a11e620-1cc1-4ac6-90d1-18c4ed9cb913",
      "virtualOrganization": null,
      "discourseUsername": "Cameron",
      "groups": [
        "8c93a113-0c6c-491f-926d-1361e43a5833",
        "d07afad8-79df-4363-b1c7-a5a1dde6e3c8",
        "df0f6341-5f6a-40ef-8b73-087a0ec255b5"
      ],
      "errorCode": 0
    },
    {
      "onlineFlights": 21,
      "violations": 0,
      "xp": 29984,
      "landingCount": 24,
      "flightTime": 2717,
      "atcOperations": 0,
      "atcRank": null,
      "grade": 1,
      "hash": "56099EA4",
      "userId": "66e362c0-894b-495b-93a6-75f9befa502d",
      "virtualOrganization": null,
      "discourseUsername": null,
       "violationCountByLevel": {
        "level1": 22,
        "level2": 0,
        "level3": 0
      },
      "roles": [
        64
      ],
      "groups": [],
      "errorCode": 0
    }
  ]
}
```

#### LiveAPIResponse

*Response Type:* `application/json`

| Name        | Type        | Description                                                  |
| ----------- | ----------- | ------------------------------------------------------------ |
| `errorCode` | integer     | _Enum:_ `"Ok = 0"`, `"UserNotFound = 1"`, `"MissingRequestParameters = 2"`, `"EndpointError = 3"`, `"NotAuthorized = 4"`, `"ServerNotFound = 5"`, `"FlightNotFound = 6"`, `"NoAtisAvailable = 7"` |
| `result`    | [UserStats] | Array of UserStats objects                                   |



#### UserStats

| Name                    | Type            | Description                                                  |
| ----------------------- | --------------- | ------------------------------------------------------------ |
| `userId`                | string (uuid)   | Unique identifier for the user                               |
| `virtualOrganization`   | string          | The virtual organization of the user's forum account if linked. Can be null if not set |
| `discourseUsername`     | string          | The user's forum username if the account is linked. If the account isn't linked, this will be null |
| `groups`                | [string (uuid)] | **Deprecated - will be in a future update** A list of groups the user can be a part of. |
| `roles`                 | [integer]       | A list of roles a user has been assigned. See below for a list of main roles. |
| `errorCode`             | integer         | Status code of user query. Not in use for this endpoint      |
| `onlineFlights`         | integer         | Number of flights carried out in multiplayer                 |
| `violations`            | integer         | Number of Level 1, 2 and 3 violations the user received in multiplayer |
| `violationCountByLevel` | dict            | A dictionary with a count of violations issued to the user, split up by levels (Level 1/2/3). |
| `xp`                    | double          | Total XP obtained in multiplayer                             |
| `landingCount`          | integer         | Total landings carried out in multiplayer                    |
| `flightTime`            | double          | Total flight time in minutes in multiplayer                  |
| `atcOperations`         | integer         | Total number of ATC Operations.                              |
| `atcRank`               | integer         | ATC Rank on the Expert Server. See below for the ranks. Can be null if user isn't an IFATC controller. |
| `grade`                 | integer         | The grade of the user, from 1 to 5.                          |
| `hash`                  | string          | A short-form user identifier, shown in the app to identify anonymous users. |

#### Roles

The main roles are as follows.

| ID   | Name                  |
| ---- | --------------------- |
| 1    | Infinite Flight Staff |
| 2    | Moderators            |
| 64   | IFATC Members         |

#### ATC Ranks

The ATC Ranks are as follows.

| ID   | Name           |
| ---- | -------------- |
| 0    | Observer       |
| 1    | ATC Trainee    |
| 2    | ATC Apprentice |
| 3    | ATC Specialist |
| 4    | ATC Officer    |
| 5    | ATC Supervisor |
| 6    | ATC Recruiter  |
| 7    | ATC Manager    |