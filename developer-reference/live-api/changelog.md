---
id: changelog
title: Changelog
meta: Track changes to the Infinite Flight Live API
order: 1
---

# Changelog

This document tracks changes to the Infinite Flight Live API

## 2024-04-12
- Added `pilotState` field to the Flights endpoint
  - New enum field indicating pilot status: `Active = 0`, `AwayInFlight = 1`, `AwayParked = 2`, `InBackground = 3`
- Fixed missing `airportLatitude` and `airportLongitude` in the ATC endpoint.
