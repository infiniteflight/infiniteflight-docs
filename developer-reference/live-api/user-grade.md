---
id: user-grade
title: Get User Grade
meta: Overview of the user grade endpoint of the Infinite Flight Live API
order: 9
contributor: KaiM,sqeezelemon,Ethan_C
---

# Get User Grade

Retrieve the full grade table and detailed statistics for a user.

## Resource

**GET** `https://api.infiniteflight.com/public/v2/users/{userId}`

## Authorization

Include your API key (`<apikey>`) by either:

-   Adding the `apikey` query parameter. For example, `?apikey=<apikey>`.
-   Sending a bearer authorization header with your API key. For example, `Authorization: Bearer <apikey>`.

## Parameters

| Name     | Located in | Description    | Required | Schema        |
| -------- | ---------- | -------------- | -------- | ------------- |
| `userId` | path       | ID of the User | Yes      | string (uuid) |

## Response

#### Sample Response

```json
{
  "errorCode": 0,
  "result": {
    "totalXP": 217242,
    "total12MonthsViolations": 4,
    "gradeDetails": {
        "grades": [...],
        "gradeIndex": 2,
        "ruleDefinitions": [...]
    },
    "atcOperations": 14641,
    "atcRank": 3,
    "lastLevel1ViolationDate": "2020-12-16T03:20:10.283484",
    "lastLevel2ViolationDate": "0001-01-01T00:00:00",
    "lastLevel3ViolationDate": "2018-07-01T17:44:05.345678",
    "lastReportViolationDate": "2018-07-01T17:44:05.345678",
    "violationCountByLevel": {
      "level1": 9,
      "level2": 0,
      "level3": 0
    },
    "roles": [
      41,
      43,
      53,
      61,
      64,
      68
    ],
    "userId": "b0018209-e010-40a0-afe1-00ecd5856c5e",
    "virtualOrganization": "IFATC [IFATC]",
    "discourseUsername": "KaiM",
    "groups": [
      "df0f6341-5f6a-40ef-8b73-087a0ec255b5"
    ],
    "errorCode": 0
  }
}
```

#### LiveAPIResponse

_Response Type:_ `application/json`

| Name        | Type      | Description                                                                                                                                                                                       |
| ----------- | --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `errorCode` | integer   | _Enum:_ `"Ok = 0"`, `"UserNotFound = 1"`, `"MissingRequestParameters = 2"`, `"EndpointError = 3"`, `"NotAuthorized = 4"`, `"ServerNotFound = 5"`, `"FlightNotFound = 6"`, `"NoAtisAvailable = 7"` |
| `result`    | GradeInfo | GradeInfo Object                                                                                                                                                                                  |

#### GradeInfo

| Name                      | Type               | Description                                                                                                                       |
| ------------------------- | ------------------ | --------------------------------------------------------------------------------------------------------------------------------- |
| `userId`                  | string (uuid)      | Unique identifier for the user                                                                                                    |
| `virtualOrganization`     | string             | The virtual organization of the user's forum account if linked. Can be null if not set                                            |
| `discourseUsername`       | string             | The user's forum username if the account is linked. If the account isn't linked, this will be null                                |
| `groups`                  | [string (uuid)]    | **Deprecated - will be removed soon.** A list of groups the user can be a part of.                                                |
| `roles`                   | [integer]          | A list of roles a user has been assigned. See below for a list of main roles.                                                     |
| `errorCode`               | integer            | Status code of user query. Not in use for this endpoint.                                                                          |
| `gradeDetails`            | GradeConfiguration | Full Grade Table                                                                                                                  |
| `violationCountByLevel`   | dict               | A dictionary with a count of violations issued to the user, split up by levels (Level 1/2/3).                                     |
| `totalXP`                 | double             | Total XP obtained in multiplayer                                                                                                  |
| `atcOperations`           | integer            | Total number of ATC Operations.                                                                                                   |
| `atcRank`                 | integer            | ATC Rank on the Expert Server. See below for the ranks. Can be null if user isn't an IFATC controller.                            |
| `total12MonthsViolations` | integer            | Total amount of Level 1, 2, and 3 violations received in the last 12 months                                                       |
| `lastLevel1ViolationDate` | string (datetime)  | Date of the user's last Level 1 violation. Defaults to `0001-01-01T00:00:00` if the user does not have any Level 1 violations. |                                                                                         |
| `lastLevel2ViolationDate` | string (datetime)  | Date of the user's last Level 2 violation. Defaults to `0001-01-01T00:00:00` if the user does not have any Level 2 violations. |                                                                                        |
| `lastLevel3ViolationDate` | string (datetime)  | Date of the user's last Level 3 violation (report). Defaults to `0001-01-01T00:00:00` if the user does not have any Level 3 violations (reports). |                                                                                        |
| `lastReportViolationDate` | string (datetime)  | Date of the user's last Level 2 or 3 violation (report). Defaults to `0001-01-01T00:00:00` if the user does not have any reports. |

#### Roles

The main roles are as follows.

| ID  | Name                  |
| --- | --------------------- |
| 1   | Infinite Flight Staff |
| 2   | Moderators            |
| 64  | IFATC Members         |

#### Groups

The main groups are as follows.

| ID                                   | Name          |
| ------------------------------------ | ------------- |
| d07afad8-79df-4363-b1c7-a5a1dde6e3c8 | Staff         |
| 8c93a113-0c6c-491f-926d-1361e43a5833 | Moderators    |
| df0f6341-5f6a-40ef-8b73-087a0ec255b5 | IFATC Members |

#### GradeConfiguration

| Name              | Type                  | Description                                            |
| ----------------- | --------------------- | ------------------------------------------------------ |
| `grades`          | [Grade]               | Array containing all grades                            |
| `gradeIndex`      | integer               | The Index of the `grades` property that the user holds |
| `ruleDefinitions` | [GradeRuleDefinition] | Definiton for the rules required for each grade        |

#### Grade

| Name    | Type        | Description                                                                    |
| ------- | ----------- | ------------------------------------------------------------------------------ |
| `rules` | [GradeRule] | Rules to be met to obtain the grade                                            |
| `index` | integer     | Index of the Grade in the `grades` property of the `GradeConfiguration` object |
| `name`  | string      | Name of the Grade                                                              |
| `state` | integer     | _Enum:_ `"Fail = 0"`, `"OK = 1"`, `"Warning = 2"`                              |

#### GradeRule

| Name                   | Type                | Description                                                     |
| ---------------------- | ------------------- | --------------------------------------------------------------- |
| `ruleIndex`            | integer             | Index of the rule in the `rules` property of the `Grade` object |
| `referenceValue`       | double              | The requirement value                                           |
| `userValue`            | double              | The value of the user for this property                         |
| `state`                | integer             | _Enum:_ `"Fail = 0"`, `"OK = 1"`, `"Warning = 2"`               |
| `userValueString`      | string              | The value of the user, nicely formatted                         |
| `referenceValueString` | string              | The requirement value, nicely formatted                         |
| `definition`           | GradeRuleDefinition | Definition of the rule                                          |

#### GradeRuleDefinition

| Name          | Type    | Description                                                                                                                                  |
| ------------- | ------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| `name`        | string  | Name of the rule                                                                                                                             |
| `description` | string  | Description of the rule                                                                                                                      |
| `property`    | string  | The property of the `GradeInfo` object the rule relates to                                                                                   |
| `operator`    | integer | _Enum:_ `"GreaterThan = 0"`, `"LesserThan = 1"`, `"GreaterThanOrEqual = 2"`, `"LesserThanOrEqual = 3"`, `"Equal = 4"`, `"DifferentThan = 5"` |
| `period`      | double  | Time period in which the rule must be met                                                                                                    |
| `order`       | integer | Order of the Rule within the `rules` property of the `Grade` object                                                                          |
| `group`       | integer | Not in use for this endpoint.                                                                                                                |

#### ViolationEntry

| Name   | Type   | Description                     |
| ------ | ------ | ------------------------------- |
| `type` | double | Type of Violation               |
| `date` | string | Date the Violation was Received |

#### ReportEntry

| Name           | Type          | Description                                 |
| -------------- | ------------- | ------------------------------------------- |
| `type`         | integer       | Type of Report                              |
| `creationTime` | string        | Time the Report was Created                 |
| `creatorId`    | string (uuid) | User ID of the Report Issuer                |
| `description`  | string        | Reason for the Report                       |
| `flightId`     | string (uuid) | ID of the Flight the Report was received in |
