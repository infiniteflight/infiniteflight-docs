---
id: airport-information
title: Get Airport Information
meta: Overview of the Airport Information endpoint of the Infinite Flight Live API
order: 22
---

# Get Airport Information

Get specific information about an airport, including location data and scenery editing metadata.

⚠️

: This API is intended for simulated flight only and must not be used in real-world flight situations.

## Resource

**GET** `https://api.infiniteflight.com/public/v2/airports/{airportIcao}`

## Authorization

Include your API key (`<apikey>`) by either:

- Adding the `apikey` query parameter. For example, `?apikey=<apikey>`.
- Sending a bearer authorization header with your API key. For example, `Authorization: Bearer <apikey>`.

## Parameters

| Name          | Located in | Description                               | Required | Schema        |
| ------------- | ---------- | ----------------------------------------- | -------- | ------------- |
| `airportIcao` | query      | ICAO of the airport to get                | Yes      | string        |

## Response

#### Sample Response

```json
{
    "errorCode": 0,
    "result": {
        "icao": "KLAX",
        "iata": "LAX",
        "name": "Los Angeles Intl",
        "city": "Los Angeles",
        "state": "California",
        "country": {
            "id": 243,
            "name": "United States",
            "isoCode": "US"
        },
        "class": 3,
        "frequenciesCount": 16,
        "elevation": 125,
        "latitude": 33.9431209564209,
        "longitude": -118.40881633758545,
        "timezone": "UTC-08:00 America",
        "has3dBuildings": true,
        "hasJetbridges": true,
        "hasSafedockUnits": true,
        "hasTaxiwayRouting": true
    }
}
```

#### LiveAPIResponse

*Response Type:* `application/json`

| Name        | Type          | Description                                                  |
| ----------- | ------------- | ------------------------------------------------------------ |
| `errorCode` | integer       | _Enum:_ `"Ok = 0"`, `"UserNotFound = 1"`, `"MissingRequestParameters = 2"`, `"EndpointError = 3"`, `"NotAuthorized = 4"`, `"ServerNotFound = 5"`, `"FlightNotFound = 6"`, `"NoAtisAvailable = 7"` |
| `result`    | AirportInfo | Information about the airport                               |

#### AirportInfo

| Name                | Type    | Description                                                  |
| ------------------- | ------- | ------------------------------------------------------------ |
| `icao`              | string  | The ICAO code of the airport                                 |
| `iata`              | string  | The IATA code of the airport                                 |
| `name`              | string  | The official name of the airport                             |
| `city`              | string  | The city where the airport is located                        |
| `state`             | string  | The state where the airport is located                       |
| `country`           | Country | Information about the country where the airport is located  |
| `class`             | integer | Classification of the airport based on its features and traffic |
| `frequenciesCount`  | integer | The number of available communication frequencies at the airport |
| `elevation`         | integer | The elevation of the airport above sea level (in feet)       |
| `latitude`          | float   | The geographical latitude of the airport                     |
| `longitude`         | float   | The geographical longitude of the airport                    |
| `timezone`          | string  | The timezone of the airport                                  |
| `has3dBuildings`    | boolean | Indicates whether the airport has 3D buildings               |
| `hasJetbridges`     | boolean | Indicates whether the airport has jet bridges                |
| `hasSafedockUnits`  | boolean | Indicates whether the airport has Safedock units             |
| `hasTaxiwayRouting` | boolean | Indicates whether the airport has taxiway routing capabilities |

#### Country

| Name       | Type   | Description                                |
| ---------- | ------ | ------------------------------------------ |
| `id`       | integer| (please ignore, this will be removed soon)     |
| `name`     | string | The name of the country                    |
| `isoCode`  | string | The ISO code of the country                |
