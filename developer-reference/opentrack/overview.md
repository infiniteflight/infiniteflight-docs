---
id: overview
title: Overview
meta: Overview of the Infinite Flight OpenTrack API
order: 1
contributor: KaiM,sqeezelemon
---

# Infinite Flight OpenTrack API

NOT AVAILABLE IN 22.6

: Due to a bug, this API is not available in Infinite Flight 22.6. We'll re-add this in a future app update. Apologies for any inconvenience

The OpenTrack API is an extremely simple UDP API used to control the camera in-game. This function was added in Infinite Flight version 20.2.

## How to use the API

The OpenTrack API is available on port `4242`.

To be able to use the OpenTrack API, users must have it enabled. To do this, users can follow these steps.

Step 1
: Open Infinite Flight

Step 2
: Go into Settings > General

Step 3
: Scroll towards the bottom and look for 'Enable Infinite Flight Connect'

Step 4
: Check the box if it is not checked already

Keep in mind this API is disabled by default.

## API Keys

No API Key is required for the OpenTrack API.

## Prerequisites

This documentation is aimed at someone with knowledge of:

- User Datagram Protocol (UDP)
- Data Types
- Camera Axis

## Samples

- [ConnectKit](https://github.com/sqeezelemon/ConnectKit) - Swift client