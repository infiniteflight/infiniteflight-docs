---
id: index
title: Introduction
meta: Learn how to use the Infinite Flight Scenario Editor with our online documentation.
---

# Welcome to the Scenario Editor overview!

This document aims to walk you through the basics of the Infinite Flight Scenario Editor.

Important
: This tool is still under development, and we highly welcome your feedback as you use it! Please reach out to Cameron or Laura if you have specific feedback or any doubts.

## What is a scenario?

A scenario is a session in Infinite Flight with a specific goal or set of goals. This could be:

 - A flight training lesson (e.g. how to land an aircraft)
 - A challenge (e.g. land the Space Shuttle)
 - A mission (e.g. fly a specific route)

The Scenario Editor has been created to help you build interactive experiences inside Infinite Flight. You have access to all the simulator states in Infinite Flight to build scenarios that can prompt users to perform a specific action, and then carry out more actions based on their inputs.

## Accessing The Scenario Editor

To use the Scenario Editor, you must be registered by a member of the Infinite Flight team. This is currently invite-only. Please reach out to your contact at Infinite Flight if you cannot access it.


Step 1

: Find your device's IP address. On iOS and Android, this is done in Settings -> WiFi and is under your local WiFi network.

Step 2

: Open the latest version of the Infinite Flight beta that you have been sent via TestFlight.

Step 3

: Keep Infinite Flight open on your phone or tablet, and on another PC, open the following address in the browser: `http://[DEVICE IP]:4090`. For example, if your device IP is `192.168.0.5`, you should open `http://192.168.0.5:4090`.

Step 4

: The Scenario Editor should be open on your web browser and the left sidebar should show a `Connected` symbol

#### Troubleshooting

If you can't open the Editor, check the following:

 - Are you logged in on your Infinite Flight device?
 - Are both devices on the same WiFi network?
 - Are you definitely using the Infinite Flight beta?

Any doubts, please reach out to Cameron for more help.

## Scenario Editor Overview

The Scenario Editor is comprised of a top toolbar with common actions and a main editor window. There are 3 main tabs - check out each subpage for more specific information:

 - **Configure Scenario**: Metadata and configuration
 - **Steps**: Define actions and completion conditions
 - **Failure Conitions**: Scenario-wide actions that would cause the scenario to fail.
