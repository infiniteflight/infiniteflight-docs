---
id: index
title: Introduction
meta: Reference for the Infinite Flight Live and Connect APIs
---

# Developer Reference

Infinite Flight offers two APIs for developers to interact with our platform and this section provides documentation and reference guides for these APIs.



## Infinite Flight Live API

The Live API is our HTTP API used for requesting data from Infinite Flight. Current features include:

- List available servers for pilots and ATC in-game.
- List active flights for each server.
- List active ATC for each server.
- Retrieve flight plans for each flight.
- Retrieve stats for each user.

An API key is required.

See [the overview](/guide/developer-reference/live-api/overview) for documentation.



## Connect API

The Connect API is our local TCP API used for interacting with Infinite Flight devices running on the local network.

- Send commands to control aircraft systems or the simulator.
- Retrieve data about the simulation, including aircraft state, ATC instructions and more.

No API key is required. Documentation is available on [GitHub](https://github.com/flyingdevelopmentstudio/infiniteflight-api).



## Which one should I use?

**If you're building a tool to view data from Live across a server**, use the Live API. Example uses include:

- Flight trackers.
- VA tools to report flights by pilots.
- Showing user stats (grade, violations, etc).
- Viewing a flight plan.

**If you're building a tool to interact with the simulator**, use the Connect API. Example uses include:

- Moving Map (like ForeFlight)
- Navigation Aid (helper for Top of Descent, weather, etc…)
- TCAS
- Traffic Viewer
- Sound engine (for callouts, audible warnings)
- Alternate Control Panel (Altimeter, Airspeed Indicator, etc…)
- Physical Cockpit Elements (with a Raspberry Pi, or any other device that can handle buttons, displays…)
- Joystick Controller Adapter (with a Raspberry Pi that forwards joystick inputs to IFC)
- Auto Checklist (which could automatically extend gear when on final, or turn on strobes when take off clearance is received)
- Auto Heading/Altitude updater when an ATC instruction is received
- Virtual Airlines reporting system (Blackbox, etc…)
- Flight Recorder