---
id: version-1
title: Connect API v1
meta: Reference for the Infinite Flight Connect API Version 1
order: 2
contributor: KaiM,nicolas
---

# Connect API v1

This documentation is for Version 1 of the Connect API. Using this API is no longer recommended due to it's slow speed and limited features. See the [Version 2 Documentation](/guide/developer-reference/connect-api/version-2) for more information.

> **The Connect API v1 is being sunsetted and will be removed in update 23.1. See [here](https://community.infiniteflight.com/t/important-sunsetting-connect-api-v1/753771) for further details.**{.red}

## Connection

 1. To enable Infinite Flight command server, check **Enable Infinite Flight Connect** in **Settings > General**
 2. Infinite Flight will broadcast UDP packets on port `15000` containing its own IP address and Port. Example message: `{ "Address": "192.168.0.11", "Port": 10111 }`

 3. You must then establish a TCP connection on this given host and port

## Get Airplane State

This special command will request the airplane state from Infinite Flight. Response will be received on the same socket: `{ "Command": "Airplane.GetState", "Parameters": []}`

## Command Messages

A command message is a object of the following form :


There are two types of command messages:
 - Commands: `{ "Command": "Commands.{CommandName}", "Parameters": []}`
 - Axis: `{ "Command": "NetworkJoystick.{AxisCommandName}", "Parameters": []}`


## List of commands

#### Joystick

Joystick axis use the `NetworkJoystick.SetAxisValue` command with two parameters:

 - Axis Name: `0` for Roll, `1` for Pitch
 - Value: a value between `-1024` and `1024`

Example :
```json
{
  "Command": "NetworkJoystick.SetAxisValue",
  "Parameters": [ { "Name": 0, "Value": -340 } ]
}
```


#### Plane Systems

Commands to control various systems of the plane. For example, to lower flaps down:
```json
{
  "Command": "Commands.FlapsDown",
  "Parameters": []
}
```

| Command  | Description  |
|---|---|
| `Brakes` | Toggle brakes on/off |
| `ParkingBrakes` | Toggle parking brakes |
| `FlapsDown` | Decrement flaps |
| `FlapsUp` | Increment flaps |
| `FlapsFullDown` | Set flaps full |
| `FlapsFullUp` | Set flaps clean |
| `Aircraft.SetFlapState` | Set the flaps to a given state |
| `Spoilers` | Switch between spoilers states (Off, Flight, Armed) |
| `LandingGear` | Toggle landing gear  |
| `Pushback` | Toggle Pushback (on/off) |
| `RollLeft` | Roll the aircraft left |
| `RollRight` | Roll the aircraft right |
| `PitchUp` | Pitch the aircraft up |
| `PitchDown` | Pitch the aircraft down |
| `ElevatorTrimUp` | Trim elevator up |
| `ElevatorTrimDown` | Trim elevator down |
| `ThrottleUpCommand` | Throttle up by 2 or 3% (alternates) |
| `ThrottleDownCommand` | Throttle down by 2 or 3% (alternates) |

#### Lights

Following commands toggle the state of a light. For example:
```json
{
  "Command": "Commands.LandingLights",
  "Parameters": []
}
```

| Command  | Description  |
|---|---|
| `LandingLights` | Toggle landing lights |
| `StrobeLights` | Toggle strobe lights |
| `BeaconLights` | Toggle beacon lights |
| `NavLights` | Toggle navigation lights |

#### Camera
**Camera Commands**

Following commands can be used to control cameras. For example:
```json
{
  "Command": "Commands.NextCamera",
  "Parameters": []
}
```

*For camera moves, see Axis commands below*

| Command  | Description  |
|---|---|
| `ToggleHUD` | Switch between HUD states (Full, Minimal, Map, Disabled) |
| `NextCamera`| Switch to next camera |
| `PrevCamera` | Switch to previous camera |
| `CameraMoveLeft` | Pan the camera left |
| `CameraMoveRight` | Pan the camera right |
| `CameraMoveDown` | Pan the camera down |
| `CameraMoveUp` | Pan the camera up |
| `CameraMoveHorizontal` | Move the camera horizontally |
| `CameraMoveVertical` | Move the camera vertically |
| `CameraZoomIn` | Zoom the camera in |
| `CameraZoomOut` | Zoom the camera out |
| `SetCockpitCamera` | Switch to the cockpit camera |

**Camera Axis**

Camera POV movements can be controlled via the following command:
```json
{
  "Command": "NetworkJoystick.SetPOVState",
  "Parameters": [
    { "Name": "X", "Value": 0 },
    { "Name": "Y", "Value": 0 }
  ]
}
```

X and Y values can be either `-1`, `0` or `1`: they determine if the camera will move on each axis, either negatively or positively (or stay still on the given axis with the `0` value). For example, to move the POV to the left only horizontally, use the following command :

```json
{
  "Command": "NetworkJoystick.SetPOVState",
  "Parameters": [
    { "Name": "X", "Value": -1 },
    { "Name": "Y", "Value": 0 }
  ]
}
```

#### ATC (Live Mode Only)

Allows you to send messages to ATC according to the options available on the ATC window. Example, call the ATC command #3 (as shown on the ATC window) :

```json
{
  "Command": "Commands.ATCEntry3",
  "Parameters": []
}
```

| Command  | Description  |
|---|---|
| `ShowATCWindowCommand` | Show / Hide the ATC window |
| `ATCEntry1` | Choose option #1 (often back) |
| `ATCEntry2` | Choose option #2 |
| `ATCEntry3` | Choose option #3 |
| `ATCEntry4` | Choose option #4 |
| `ATCEntry5` | Choose option #5 |
| `ATCEntry6` | Choose option #6 |
| `ATCEntry7` | Choose option #7 |
| `ATCEntry8` | Choose option #8 |
| `ATCEntry9` | Choose option #9 |
| `ATCEntry10` | Choose option #10 |

#### Autopilot and Flight Plan

Commands to set the value of an Autopilot param, or to toggle its state.

| Command  | Description  |
|---|---|
| `Autopilot.Toggle` | Toggle autopilot |
| `Autopilot.SetState` | Set autopilot on/off |
| `Autopilot.SetHeading` | Set autopilot Heading |
| `Autopilot.SetAltitude` | Set autopilot Altitude |
| `Autopilot.SetVS` | Set autopilot Vertical Speed |
| `Autopilot.SetSpeed` | Set autopilot Speed |
| `Autopilot.SetHeadingState` | Set autopilot Heading On/Off |
| `Autopilot.SetAltitudeState` | Set autopilot Altitude On/Off |
| `Autopilot.SetVSState` | Set autopilot Vertical Speed On/Off |
| `Autopilot.SetSpeedState` | Set autopilot Speed On/Off |
| `Autopilot.SetApproachModeState` | Set autopilot APPR On/Off |
| `FlightPlan.AddWaypoints` | Add waypoints to Flight Plan |
| `FlightPlan.Clear` | Clear Flight Plan |
| `FlightPlan.ActivateLeg` | Activate a given leg of the Flight Plan |

**Examples**

*Set HDG to 270*

```json
{
  "Command": "Commands.Autopilot.SetHeading",
  "Parameters": [{ "Value": 270 }]
}
```

*Enable HDG*

```json
{
  "Command": "Commands.Autopilot.SetHeadingState",
  "Parameters": [{ "Value": true }]
}
```

*Toggle AP*

```json
{
  "Command": "Commands.Autopilot.Toggle",
  "Parameters": []
}
```

#### Simulator Commands

Control on simulator. Example, toggle play/pause.
```json
{
  "Command": "Commands.TogglePause",
  "Parameters": []
}
```

| Command  | Description  |
|---|---|
| `TogglePause` | Toggle the pause screen |
| `ToggleTime` | Sets the simulator time |
