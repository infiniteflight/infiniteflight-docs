---
id: in-app-tools
title: In App Tools
meta: Quick overview of the Scenario Editor tool
order: 2
---

# In-App Tools

Infinite Flight has several tools which are useful for debugging scenarios.

## Scenario Explorer

Access

: When in a scenario in the flight simulator, open Systems -> SCENARIO CONTROL

This allows you to see **every step**, as well as the current step. Look at the Completion Conditions and it will show you if they are matching, or if the expected and actual values are different.

## State Explorer

Access

: When in a scenario or a free flight in the flight simulator, open Systems -> STATE EXPLORER

You can explore every state in Infinite Flight in real-time. This will also show you:
 - The current value
 - The unit (if available)
 - `r` if the state is only _readable_ (can't be edited)
 - `rw` if the state is readable and _writable_ (can be edited)

You can use the search to find a specific state.

**Note:** States are per-aircraft. Make sure your scenario's aircraft matches the aircraft you are using when exploring states in the State Explorer.