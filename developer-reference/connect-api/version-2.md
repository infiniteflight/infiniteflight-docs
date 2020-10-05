---
id: version-2
title: Connect API v2
meta: Reference for the Infinite Flight Connect API Version 2
contributor: KaiM
---

# Connect API v2

This version of the API was first included in Infinite Flight version 19.4.
## Connection
Step 1
: Enable Infinite Flight command server - check `Enable Infinite Flight Connect` in `Settings > General` is checked

Step 2
: Infinite Flight will broadcast UDP packets on port `15000` containing its own IP address and Port, as well as other information. Example message: `["State": Playing, "Port": 10111, "DeviceID": iPad7, "Aircraft": Cessna 172, "Version": 19.4.7354.25209, "DeviceName": Thomas’s iPad, "Addresses":("fe80::1c79:baf4:f9f1:dd59%3", "192.168.1.26"), "Livery": Civil Air Patrol]`

Step 3
: You must then establish a TCP connection on this given host and port (note that version 2 uses port `10112`, not port `10111` - that's from v1).

## Interacting with the API

#### Data Formats

All data must be sent as it's type. For instance, if you're trying to send boolean `true` you must encode it as a boolean, not an integer or string. 

### Obtaining the Manifest

The Connect API exposes different states for every aircraft, and as such the applicable states and their IDs change depending on what aircraft you are operating. You can obtain a manifest of available states by sending integer `-1` followed by boolean `false` to the API. This will return the `ID` you sent (`-1`), and the `length` of the data you are about to receive in bytes as an integer. All information received from the API begins this way. Following the `ID` and `length`, the manifest is represented as a (very long) string. The API represents strings by sending their length in bytes as an integer followed by the actual string. The string will have the format `511,2,aircraft/0/systems/nav_sources/adf/2/distance_to_glide_path\n851,3,infiniteflight/cameras/4/x_angle\n81,4,api_joystick/buttons/8/name...`. This string can be split on `\n` and then generalizes to `ID, Type, Path` for each state.

The API defines data types according to the following integers:

| Integer | Type             |
| ------- | ---------------- |
| 0       | Boolean          |
| 1       | Integer (32-bit) |
| 2       | Float            |
| 3       | Double           |
| 4       | String           |
| 5       | Long             |

### Sending Data

Sending data is done by sending information to the API in one of the following ways.

#### Get State

A `GetState` command is sent by sending:

1. The integer value of the `ID` of the state you would like to get.
2. A `false` boolean value.

The state you request will be returned via the API on the same socket. 

**Example:** Sending `635`, then  `false` will result in Infinite Flight sending you `635`, then `1`, then `1` if your strobe lights are on.

#### Set State

A `SetState` command is sent by sending:

1. The integer value of the `ID` of the state you would like to get.
2. A `true` boolean value.
3. The value, as the applicable data type, you would like to set the state to. 

**Example:** Sending `635`, then `true`, then `0` will turn your strobe lights off.

#### Run Command

A `RunCommand` is sent by sending:

1. The integer value of the `ID` of the command you would like to send.
2. A `false` boolean value

**Example:** Sending `1048634` then `false` will toggle the autopilot.

### Receiving Data

All states begin with two integer values:  `ID` and `Length` of the data.

Following these values, all states are returned as their data type (so a state with an integer data type will be returned as an integer, a float as a float, etc.) with the exception of strings. Strings contain one additional integer specifying the length of bytes as an integer, followed by the string.

You can receive states after sending a `GetState` command, described above.
