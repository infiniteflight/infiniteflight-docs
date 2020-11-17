---
id: user-grade
title: Get User Grade
meta: Overview of the user grade endpoint of the Infinite Flight Live API
order: 7
contributor: KaiM
---

# Get User Grade

Retrieve the full grade table and detailed statistics for a user.

## Resource

**GET** `https://api.infiniteflight.com/public/v2/user/grade/{userId}`

## Authorization

Include your API key (`<apikey>`) by either:

- Adding the `apikey` query parameter. For example, `?apikey=<apikey>`.
- Sending a bearer authorization header with your API key. For example, `Authorization: Bearer <apikey>`.

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
    "pilotStats": {
      "gradeDetails": {
        "grades": "Omitted for Brevity",
        "gradeIndex": 3
      },
      "reports": [],
      "violations": [
        {
          "type": 0,
          "date": "2020-06-17T07:00:48.112+00:00"
        },
        {
          "type": 0,
          "date": "2020-06-17T07:00:26.631+00:00"
        },
        {
          "type": 0,
          "date": "2020-06-17T07:00:06.722+00:00"
        },
        {
          "type": 0,
          "date": "2020-05-22T22:41:18.025+00:00"
        },
        {
          "type": 0,
          "date": "2020-04-03T08:10:47.736+00:00"
        }
      ],
      "totalXP": 180769,
      "atcOperations": 10641,
      "atcRank": 3
    },
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

*Response Type:* `application/json`

| Name        | Type              | Description                                                  |
| ----------- | ----------------- | ------------------------------------------------------------ |
| `errorCode` | integer           | *_Enum:_* `"Ok = 0"`, `"UserNotFound = 1"`, `"MissingRequestParameters = 2"`, `"EndpointError = 3"`, `"NotAuthorized = 4"`, `"ServerNotFound = 5"` |
| `result`    | GradeInfoResponse | GradeInfoResponse Object                                     |

#### GradeInfoResponse

| Name | Type | Description |
| ---- | ---- | ----------- |
| userId | string (uuid) | Unique identifier for the user |
| virtualOrganization | string | The virtual organization of the user's forum account if linked. Can be null if not set |
| discourseUsername | string | The user's forum username if the account is linked. If the account isn't linked, this will be null |
| groups | [string (uuid)] | A list of groups the user can be a part of. See below for a list of the main groups. |
| errorCode | integer | Status code of user query. Not in use for this endpoint. |
| pilotStats | GradeInfo | GradeInfo Object |

#### Groups

The main groups are as follows.

| ID                                   | Name          |
| ------------------------------------ | ------------- |
| d07afad8-79df-4363-b1c7-a5a1dde6e3c8 | Staff         |
| 8c93a113-0c6c-491f-926d-1361e43a5833 | Moderators    |
| df0f6341-5f6a-40ef-8b73-087a0ec255b5 | IFATC Members |



#### GradeInfo

| Name | Type | Description |
| ---- | ---- | ----------- |
| gradeDetails | GradeConfiguration | Full Grade Table |
| reports | [ReportEntry] | Array of Level 2 and 3 violations the user received in multiplayer |
| violations | [ViolationEntry] | Array of Level 1 violations the user received in multiplayer |
| totalXP | double | Total XP obtained in multiplayer |
| atcOperations | integer | Total number of ATC Operations. |
| atcRank | integer | ATC Rank on the Expert Server. See below for the ranks. Can be null if user isn't an IFATC controller. |

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

#### GradeConfiguration

| Name | Type | Description |
| ---- | ---- | ----------- |
| grades | [Grade] | Array containing all grades |
| gradeIndex | integer | The Index of the `grades` property that the user holds |

#### Grade

| Name | Type | Description |
| ---- | ---- | ----------- |
| rules | [GradeRule] | Rules to be met to obtain the grade |
| index | integer | Index of the Grade in the `grades` property of the `GradeConfiguration` object |
| name | string | Name of the Grade |
| state | integer | _Enum:_ `"Fail = 0"`, `"OK = 1"`, `"Warning = 2"` |

#### GradeRule

| Name | Type | Description |
| ---- | ---- | ----------- |
| ruleIndex | integer | Index of the rule in the `rules` property of the `Grade` object |
| referenceValue | double | The requirement value |
| userValue | double | The value of the user for this property |
| state | integer | _Enum:_ `"Fail = 0"`, `"OK = 1"`, `"Warning = 2"` |
| userValueString | string | The value of the user, nicely formatted |
| referenceValueString | string | The requirement value, nicely formatted |
| definition | GradeRuleDefinition | Definition of the rule |

#### GradeRuleDefinition

| Name | Type | Description |
| ---- | ---- | ----------- |
| name | string | Name of the rule |
| description | string | Description of the rule |
| property | string | The property of the `GradeInfo` object the rule relates to |
| operator | integer | _Enum:_ `"GreaterThan = 0"`, `"LesserThan = 1"`, `"GreaterThanOrEqual = 2"`, `"LesserThanOrEqual = 3"`, `"Equal = 4"`, `"DifferentThan = 5"` |
| period | double | Time period in which the rule must be met |
| order | integer | Order of the Rule within the `rules` property of the `Grade` object |
| group | integer | Not in use for this endpoint. |

#### ViolationEntry

| Name | Type   | Description                     |
| ---- | ------ | ------------------------------- |
| type | double | Type of Violation               |
| date | string | Date the Violation was Received |

#### ReportEntry

| Name         | Type          | Description                                 |
| ------------ | ------------- | ------------------------------------------- |
| type         | integer       | Type of Report                              |
| creationTime | string        | Time the Report was Created                 |
| creatorId    | string (uuid) | User ID of the Report Issuer                |
| description  | string        | Reason for the Report                       |
| flightId     | string (uuid) | ID of the Flight the Report was received in |

