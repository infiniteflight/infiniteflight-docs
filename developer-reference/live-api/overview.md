---
id: overview
title: Overview
meta: Overview of the Infinite Flight Live API
order: 1
---

# Infinite Flight Live API Overview

The Live API is our HTTP API used for requesting data from Infinite Flight Servers. Current features include:

- List available servers for pilots and ATC in-game.
- List active flights for each server.
- List active ATC for each server.
- Retrieve flight plans for each flight.
- Retrieve stats for users.

⚠️

: This API is intended for simulated flight only and must not be used in real-world flight situations.

## Obtaining an API key

An API key is required to use the Live API. Contact [hello@infiniteflight.com](mailto:hello@infiniteflight.com) to let us know what you plan on building and to request a key.

## How to use the API

The Live API uses HTTP and the endpoints require you to make a GET or POST request to the endpoint URL. See individual endpoint documentation for specifics

## Conditions of Use

- All apps are required to have a timeout feature if the app isn't being used. We don't want users to have the app running for hours if no-one is looking. If no action is taken for 15 minutes, have your apps stop downloading new content unless the user presses a button (FlightRadar24 does this on their site).

- Live API data may only be stored in temporary caches needed to power your app. Permanent storage, warehousing, replication, or keeping Live API data in your own database is prohibited.

- Infinite Flight retains ownership of Live API data. You may not use Live API data to train, fine-tune, evaluate, distill, ground, or otherwise improve AI or machine learning models.

- If we detect prohibited storage or AI-training use, the API key and associated user accounts may be banned from the API.

  If you need additional functionality from the API, please contact us.

- Review the [usage and polling best practices](/guide/developer-reference/live-api/best-practices) before deploying your app or integrating the API with an LLM.

## Prerequisites

This documentation is aimed at someone with knowledge of:

- HTTP
- JSON
- Infinite Flight System (Grades, Servers, etc.)

If you are not knowledgeable in these areas, you are of course welcome to browse the documentation. You can also check out these resources to help you learn.

- [W3Schools - What is HTTP?](https://www.w3schools.com/whatis/whatis_http.asp)
- [W3Schools - JSON Introduction](https://www.w3schools.com/js/js_json_intro.asp)
- [Infinite Flight User Guide](/guide/getting-started-guide/home-user-interface/user-profile#the-grade-table)
