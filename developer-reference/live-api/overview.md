---
id: overview
title: Overview
meta: Overview of the Infinite Flight Live API
order: 1
---

# Infinite Flight Live API Overview

The Live API is our HTTP API used for requesting data from Infinite Flight. Current features include:

- List available servers for pilots and ATC in-game.
- List active flights for each server.
- List active ATC for each server.
- Retrieve flight plans for each flight.
- Retrieve stats for users.



## Obtaining an API key

An API key is required to use the Live API. Contact [hello@infiniteflight.com](mailto:hello@infiniteflight.com) to let us know what you plan on building and to request a key.



## How to use the API

The Live API uses HTTP and the endpoints require you to make a GET or POST request to the endpoint URL (see individual endpoint documentation for specifics).



## Conditions of use

- All apps are required to have a timeout feature if the app isn’t being used. We don’t want users to have the app running for hours if no-one is looking. If no action is taken for 15 minutes, have your apps stop downloading new content unless the user presses a button (FlightRadar24 does this on their site).

- No permanent storing of data retrieved via the API is permitted. (You cannot keep the data in your own database).

  If you need additional functionality from the API, please contact us.

## Prerequisites

This documentation is aimed at people with experience in the following areas

- HTTP
- JSON
- Infinite Flight System (Grades, Servers, etc.)

If you are not knowledgeable in these areas, you are of course welcome to browse the documentation. You can also check out the following resources to help you learn these skills.

- [W3Schools - What is HTTP?](https://www.w3schools.com/whatis/whatis_http.asp)
- [W3Schools - JSON Introduction](https://www.w3schools.com/js/js_json_intro.asp)
- [Infinite Flight Flying Guide](/guide/getting-started/home-user-interface/user-profile#the-grade-table)