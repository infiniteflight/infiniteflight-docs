---
id: index
title: Introduction
meta: Reference for the Infinite Flight Live and Connect APIs
---

# Developer Reference



## Guide Version: 23.4.0



Infinite Flight offers two APIs for developers to interact with our platform and this section provides documentation and reference guides for these APIs.



## Infinite Flight Live API

The Live API is our HTTP API used for requesting data from Infinite Flight. Current features include:

- List available servers for pilots and ATC in-game.
- List active flights for each server.
- List active ATC for each server.
- Retrieve flight plans for each flight.
- Retrieve stats for each user.

An API key is required and can be requested via email to [hello@infiniteflight.com](mailto:hello@infiniteflight.com). See [the overview](/guide/developer-reference/live-api/overview) for documentation.

## Infinite Flight Connect API

The Connect API is our local TCP API used for interacting with Infinite Flight devices running on the local network.

- Send commands to control aircraft systems or the simulator.
- Retrieve data about the simulation, including aircraft state, ATC instructions and more.

No API key is required. Documentation is available [here](/guide/developer-reference/connect-api/overview).

## OpenTrack API

[OpenTrack](https://github.com/opentrack/opentrack) is an application dedicated to tracking user's head movements and relaying the information to games and flight simulation software. Infinite Flight implements a simple API to support OpenTrack, with documentation available [here](/guide/developer-reference/opentrack/overview).

## Which one should I use?

**If you're building a tool to view data from Live across a server**, use the Live API. Example uses include:

- Flight Trackers
- ATC Status Websites
- Showing user stats (grade, violations, etc.)
- Viewing a Flight Plan

**If you're building a tool to interact with the simulator**, use the Connect API. Example uses include:

- Moving Map (like ForeFlight)
- Local Traffic Viewer
- Auto Checklist
- Auto Heading/Altitude updater when an ATC instruction is received

**If you're building a head-tracking or other camera application,** use the OpenTrack API. Example uses include:

- Head tracking to move camera
- Auto-align camera for different stages of flight
- Other camera-central applications