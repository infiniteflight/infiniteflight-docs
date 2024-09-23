---
id: steps
title: Steps
meta: Quick overview of the Scenario Editor tool
order: 2
---

# Steps

The Steps tab is where the majority of the scenario is configured.

Each step represents a point in the scenario in which an action is carried out. An action could be:

 - Show a message to the user (with text to speech audio)
 - Configure the Autopilot
 - Show a UI helper to flash a specific button on the user's screen.

## The Timeline

The timeline is the section at the top of the Steps tab. This will show you **all your existing steps** and allows you to add new steps easily. Here are the actions you can carry out:

 - **Selecting a step:** simply tap on the step in the timeline
 - **Adding a new step:** either press `Add Step` to add at the end, or right click to insert a step between other steps.
 - **Delete step:** right click and press Delete.
 - **Duplicate step:** right click and press Duplicate. This copies all messages, completion conditions, etc.
 - **Reorder steps:** press and hold on any step to enter "jiggle mode" like on the iPhone. Re-arrange, and press `Stop Ordering` when complete.

## When does a step advance to the next one?

There are 3 main ways:
 
  - When the Briefing Message has finished being read out by the Text to Speech system
  - When a Completion Condition is met
  - When a Timeout is set in the Step Configuration

## Step Configuration

Inside each step, you'll find the following tabs and configuration options:

#### State

Use this to configure the state of the simulator or of the aircraft. As an example, let's enable the HDG autopilot at a heading of 90 degrees.

Step 1

: Tap on Add Action

Step 2

: Inside the `States` list, search for the `Systems → Autopilot → Hdg → On` state. Set this to `true` to enable it.

Step 3

: Inside the `States` list, search for the `Systems → Autopilot → Hdg → Target` state. Set this to `1.5708` to set the heading. NOTE: headings are currently in radians and we are working on improving this.

Step 4

: Tap the checkmark for each state to save the changes.


#### Briefing Message

This is the message that will be shown to the user when they reach this step. Use this to provide an instruction, or to give the user additional context.

You can hear the Sound for each language **after** you have uploaded the changes and edited the briefing messages.

#### Completion Conditions

If these are met, the scenario will advance to the next step.

There are two types of Completion Condition:

 - **State Conditions:** this works in the same way as the `State` tab, except it is looking for a value to match a state.
 - **Location Conditions:** here, the aircraft needs to be within a radius of a latitude and longitude. Use this if you want the user to fly through a specific area.

Things to be aware of:
 - **Tolerance:** if the value is a number, you can provide a tolerance which is the error margin. i.e. if you are expecting the value 100, but have a tolerance of 25, we will accept any state between 75 and 125.
 - **Minimum Time:** the state must match the values for this amount of time. This is so we don't immediately advance to the next step. We recommend 5 seconds.

#### Configuration

You can set a timeout here, in the case the user doesn't complete the conditions required. For example, if they ignore the instruction, you can advance to the next step after 10 seconds.

**Continue button title** lets you customize the button in the Mission Brief that the user can tap on to proceed to the next step.

**Wait for confirmation** requires the user to tap on the mission brief, otherwise the scenario is stuck waiting for input.