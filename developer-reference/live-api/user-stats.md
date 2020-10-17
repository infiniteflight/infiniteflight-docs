---
id: user-stats
title: Get User Stats
meta: Overview of the user stats endpoint of the Infinite Flight Live API
order: 6

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

| Name      | Located in        | Description                                                  | Required | Schema          |
| --------- | ----------------- | ------------------------------------------------------------ | -------- | --------------- |
| `userIds` | POST request body | An array of user ID strings retrieved from the Get Flights endpoint | Yes      | [string (uuid)] |

#### Sample Body

```json
{
  "userIds": [
    "3f8b28bf-bbb1-4024-80ae-2a0ea9b30685",
    "66e362c0-894b-495b-93a6-75f9befa502d"
  ]
}
```



## Response

#### Sample Response

```json
{
  "errorCode": 0,
  "result": [
    {
      "onlineFlights": 1116,
      "violations": 104,
      "xp": 564155,
      "landingCount": 890,
      "flightTime": 45304,
      "atcOperations": 0,
      "atcRank": null,
      "grade": 5,
      "hash": "5F0973A9",
      "userId": "3f8b28bf-bbb1-4024-80ae-2a0ea9b30685",
      "virtualOrganization": "IFATC [IFATC]",
      "discourseUsername": "Cameron",
      "groups": [
        "d07afad8-79df-4363-b1c7-a5a1dde6e3c8",
        "fcf6f0ea-4bf4-4ca6-81b8-c1c357d8f089",
        "8c93a113-0c6c-491f-926d-1361e43a5833",
        "df0f6341-5f6a-40ef-8b73-087a0ec255b5",
        "1e6599f9-8fcf-49a1-a0c7-e1c205826b65"
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
| `errorCode` | integer     | _Enum:_ `"Ok = 0"`, `"UserNotFound = 1"`, `"MissingRequestParameters = 2"`, `"EndpointError = 3"`, `"NotAuthorized = 4"`, `"ServerNotFound = 5"` |
| `result`    | [UserStats] | Array of UserStats objects                                   |



#### UserStats

| Name                  | Type            | Description                                                  |
| --------------------- | --------------- | ------------------------------------------------------------ |
| `userId`              | string (uuid)   | Unique identifier for the user                               |
| `virtualOrganization` | string          | The virtual organization of the user's forum account if linked. Can be null if not set |
| `discourseUsername`   | string          | The user's forum username if the account is linked. If the account isn't linked, this will be null |
| `groups`              | [string (uuid)] | A list of groups the user can be a part of. See below for the main groups. |
| `errorCode`           | integer         | Status code of user query. Not in use for this endpoint      |
| `onlineFlights`       | integer         | Number of flights carried out in multiplayer                 |
| `violations`          | integer         | Number of Level 1, 2 and 3 violations the user received in multiplayer |
| `xp`                  | double          | Total XP obtained in multiplayer                             |
| `landingCount`        | integer         | Total landings carried out in multiplayer                    |
| `flightTime`          | double          | Total flight time in minutes in multiplayer                  |
| `atcOperations`       | integer         | Total number of ATC Operations.                              |
| `atcRank`             | integer         | ATC Rank on the Expert Server. See below for the ranks. Can be null if user isn't an IFATC controller. |
| `grade`               | integer         | The grade of the user, from 1 to 5.                          |
| `hash`                | string          | A short-form user identifier, shown in the app to identify anonymous users. |

#### Groups

The main groups are as follows.

| ID                                   | Name          |
| ------------------------------------ | ------------- |
| d07afad8-79df-4363-b1c7-a5a1dde6e3c8 | Staff         |
| 8c93a113-0c6c-491f-926d-1361e43a5833 | Moderators    |
| df0f6341-5f6a-40ef-8b73-087a0ec255b5 | IFATC Members |

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