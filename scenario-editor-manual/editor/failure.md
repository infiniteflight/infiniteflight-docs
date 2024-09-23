---
id: failure
title: Failure Conditions
meta: Quick overview of the Scenario Editor tool
order: 2
---

# Failure Conditions

Failure conditions are designed to fail the scenario if the user leaves certain parameters. For example, you can fail if:

 - The user dives the nose towards the ground in a straight-and-level flight tutorial.
 - The user stalls the aircraft
 - etc

You can add as many failure conditions as you want, and each can have their own specific message to show to the user.

## Example

As an example, let's fail the scenario if the user stalls.

Step 1

: Tap on Add Failure Condition

Step 2

: Inside the `States` list, search for the `Is Stalling` state. Set this to `equals` & `true` to enable it.

Step 3

: Set a message to show the user, for example, "You stalled the aircraft"

Step 3

: Tap the checkmark for each state to save the changes.

