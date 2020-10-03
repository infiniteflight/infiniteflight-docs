---
id: overview
title: Overview
meta: Overview of the Infinite Flight Connect API
---

# Infinite Flight Connect API Overview

The Connect API is our local TCP API used for getting specific data and performing actions in-flight. Examples of this include:

- Turning Lights on/off
- Controlling Autopilot
- Controlling Network Joysticks

## How to use the API

The Connect API comes in two versions - v1 and v2 - available on ports `10111` and `10112` respectively. Version 1 uses JSON objects as strings, whereas Version 2 uses a range of formats and has more functions.

To be able to use the Connect API, users must have it enabled. To do this, follow these steps.

Step 1
: Open Infinite Flight

Step 2
: Go into Settings > General

Step 3
: Scroll towards the bottom and look for 'Enable Infinite Flight Connect'

Step 4
: Check the box if it is not checked alread

Keep in mind the Connect API is disabled be default.

## API Keys

No API Key is required for the Connect API.