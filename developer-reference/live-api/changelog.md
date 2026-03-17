---
id: changelog
title: Changelog
meta: Track changes to the Infinite Flight Live API
order: 2
---

# Changelog

This document tracks changes to the Infinite Flight Live API

## 2026-03-17
- Lowered the default Live API rate limit to 30 requests per minute per API key.
- Added a higher default rate limit of 100 requests per minute for API keys linked to users with an active paid Pro subscription.
- Added [usage and polling best practices](/guide/developer-reference/live-api/best-practices), including temporary-cache-only storage rules and an explicit prohibition on AI training use of Live API data.

## 2024-04-12
- Added `pilotState` field to the [Flights endpoint](/guide/developer-reference/live-api/flights)
  - New enum field indicating pilot status: `Active = 0`, `AwayInFlight = 1`, `AwayParked = 2`, `InBackground = 3`
- Fixed missing `airportLatitude` and `airportLongitude` in the [ATC endpoint](/guide/developer-reference/live-api/atc).
