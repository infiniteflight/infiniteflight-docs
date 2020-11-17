---
id: camera-position
title: Set Camera Position
meta: Set the Camera Position with the Infinite Flight OpenTrack API
order: 2
contributor: KaiM,epaga
---

# Set Camera Position

To set the Camera Position using the OpenTrack API, send just one chunk with 6 `double` values in the following order.

* X-Axis
* Y-Axis
* Z-Axis
* Yaw
* Pitch
* Roll

The chunk should be sent over UDP to the device running IF on port `4242`.