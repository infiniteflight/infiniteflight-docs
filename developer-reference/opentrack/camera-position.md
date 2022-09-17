---
id: camera-position
title: Set Camera Position
meta: Set the Camera Position with the Infinite Flight OpenTrack API
order: 2
contributor: KaiM,epaga
---

# Set Camera Position

NOT AVAILABLE IN 22.6

: Due to a bug, this API is not available in Infinite Flight 22.6. We'll re-add this in a future app update. Apologies for any inconvenience

To set the Camera Position using the OpenTrack API, send just one chunk with 6 `double` values in [Little-Endian](/guide/developer-reference/connect-api/version-2#little-endian) format in the following order.

* X-Axis
* Y-Axis
* Z-Axis
* Yaw
* Pitch
* Roll

The chunk should be sent over UDP to the device running IF on port `4242`.
