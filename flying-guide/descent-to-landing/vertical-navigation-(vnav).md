---
id: vertical-navigation-(vnav)
title: Vertical Navigation (VNAV)
meta: Learn how to use VNAV in Infinite Flight.
order: 2
---

# Vertical Navigation (VNAV)



## What is VNAV?

VNAV stands for Vertical Navigation and is an autopilot feature that allows the aircraft to adjust vertical speed to meet a predetermined altitude at a specified waypoint. All SIDs, STARs, and Approaches have altitudes restrictions that have to be met; and VNAV is available (currently for descent only) to help meet these restrictions and reduce your workload. 



Provided your flight plan has at least one waypoint with an altitude restriction, VNAV will calculate a desirable rate of climb/descent and adjust this as conditions change. The following parameters are used for this calculation:



- groundspeed
- distance to the next waypoint
- and the difference in altitude between your initial altitude and your target/final altitude



## How do I calculate my Top of Descent (TOD)?

Top of Descent, also known as TOD; is the point at which you initiate a descent from cruising altitude to another altitude in preparation for the arrival phase of flight. TOD is displayed in time and distance can can be found in two places, these are:



- Within the VNAV button on the [Autopilot](/guide/getting-started/pilot-user-interface/autopilot#autopilot) Flight Control Unit (FCU)
- And also on the [Status Bar](/guide/getting-started/pilot-user-interface/status-bar#status-bar) if this option has been selected



## How do I use VNAV?



Step 1

: Check your flight plan and ensure that the altitude restrictions are present for the procedure you are about to fly, you will require these for VNAV to work correctly



Step 2

: Approaching your TOD, make sure to [request altitude change](/guide/getting-started/pilot-user-interface/communication#communication) if there is Active ATC



Step 3

: Once you have clearance and it is clear, access the [Autopilot](/guide/getting-started/pilot-user-interface/autopilot#autopilot) FCU and tap VNAV to arm this function. Your altitude and VS will change color to magenta to indicate that VNAV is armed



Tip

: Before making any altitude changes, check surroundings to make sure it is clear, use the [Cameras](/guide/getting-started/pilot-user-interface/cameras#camera) and [Mini Map](/guide/getting-started/pilot-user-interface/mini-map#mini-map) to help you



Step 4

: Altitude and VS input is not required, VNAV will now adjust your rate of vertical speed to meet the altitude restrictions programmed into your Flight Plan



Tip

: VNAV will target a Flight Path Angle (FPA) of 2 degrees, however if you descend late, VNAV may increase this in order to meet the restriction. VNAV cannot exceed 3000 feet per minute (fpm) and therefore in this case, manual intervention may be required to meet the altitude restriction. In addition, the TOD calculator will start to read out negative values, this is because you passed the TOD point before commencing your descent



Step 5

: During the descent, an Altitude Arc will be displayed on the map which indicates the predicted position at which the aircraft will be level at the altitude currently displayed in the Autopilot FCU ALT button. If this arc is not at the desired position, VNAV may not be working correctly and manual intervention could be required



## What happens once I'm level?



Once VNAV has captured the desired altitude it will do one of two things:



- The Autopilot will level off and display the new distance to TOD (indicating where your next TOD is for that segment of the Flight Plan provided there are more altitude restrictions programmed in)
- Or, the Autopilot will continue descending if it determines that you will be at or above the 2 degree Flight Path Angle (FPA) when you arrive at that altitude



## What do I do when I’m being Vectored?

In general, Radar Controllers will try to let you fly the selected procedure as it reduces their workload, however they may be required to give vectors (almost certain on the Approach). When you do get given vectors and/or altitude assignments it is important that you follow them:



Step 1

: Acknowledge the instruction sent to you using the [Communication](/guide/getting-started/pilot-user-interface/communication#communication) button



Step 2

: Access the [Autopilot](/guide/getting-started/pilot-user-interface/autopilot#autopilot) FCU and tap VNAV to disarm this function



Step 3

: Adjust your heading, altitude and/or speed as required by ATC



Step 4

: Ensure that your Navaids are tuned for the approach that you are expecting to fly



Tip

: Continuously check surroundings to make sure it is clear and for planning (particularly in the descent), use the [Cameras](/guide/getting-started/pilot-user-interface/cameras#camera) and [Mini Map](/guide/getting-started/pilot-user-interface/mini-map#mini-map) to help you