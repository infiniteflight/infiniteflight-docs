---
id: best-practices
title: Usage and Polling Best Practices
meta: Rate limits, polling cadence, caching, and prohibited storage and AI training rules for the Infinite Flight Live API
order: 2
---

# Usage and Polling Best Practices

Follow these rules before deploying a Live API integration.

## Rate Limits

- Default limit: 30 requests per minute per API key.
- Higher default limit: 100 requests per minute when the API key is linked to a user account with an active paid Pro subscription.
- If a linked Pro subscription lapses, the key returns to the free-tier default.
- If you are unable to keep to the rate limit due to app popularity (congrats!), please contact hello@infiniteflight.com and we can look into increasing your rate limit.
- Exceeding the limit returns HTTP `429 Too Many Requests`.

## Polling Guidance

Do not poll the Live API as if it were a streaming feed. Use the slowest cadence that still meets your product's needs.

| Endpoint | Recommended minimum interval | Notes |
| --- | --- | --- |
| `GET /sessions` | 10 minutes | This data is server-cached for 10 minutes and changes infrequently. |
| `GET /sessions/{sessionId}` | 10 minutes | Treat session metadata the same as the session list unless the user explicitly refreshes. |
| `GET /sessions/{sessionId}/flights` | 15 seconds | Flight lists are short-lived cached data and do not need sub-15-second polling. |
| `GET /sessions/{sessionId}/flights/{flightId}` | 15 seconds | Reuse the list response where possible instead of repeatedly fetching individual flights. |
| `GET /sessions/{sessionId}/atc` | 15 seconds | Poll conservatively and only while the user is actively viewing the data. |
| `GET /sessions/{sessionId}/airport/{icao}/status` | 15 seconds | Avoid polling multiple airport views in parallel unless the UI is visible. |
| User history endpoints | 5 minutes or longer | Historical and profile-style data should be cached aggressively. |

## Caching Expectations

- Temporary caching is permitted and expected.
- Cache session data for at least 10 minutes.
- Cache flight and ATC data for at least 15 seconds.
- Stop polling when the app is idle. If no user action is taken for 15 minutes, stop downloading new content until the user resumes interaction.

## Prohibited Data Use

- Do not persist Live API data outside short-lived operational caches.
- Do not copy Live API data into your own long-term database, analytics warehouse, or training corpus.
- Do not use Live API data to train, fine-tune, evaluate, distill, ground, or otherwise improve AI or machine learning models.
- Infinite Flight retains ownership of the data returned by the Live API.

If we detect prohibited storage, scraping, or AI-training use, the API key and associated accounts may be banned from the API.

## LLM Integrations

If you provide Live API data to an LLM at runtime:

- Send only the minimum data needed to answer the current user request.
- Respect the polling intervals above before fetching fresh data.
- Do not retain Live API responses for later model training, tuning, evaluation, or dataset creation.
- Prefer summarizing current results for the user instead of repeatedly re-fetching the same endpoint.

You can also provide a single llms.txt of the Live API reference to your LLM as context: [Download the Live API llms.txt](/llms.txt).