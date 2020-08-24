---
id: atis-pushback-and-taxi
title: ATIS, Pushback and Taxi
meta: Learn how to communicate pushback and taxi instructions with ATC in Infinite Flight.
order: 1
contributor: babacar,lucaviness,planegeek
---

# ATIS, Pushback and Taxi



## ATIS Communication Summary

When spawning, provided ATC is active, you will automatically be tuned to the ATIS frequency (if it is currently staffed by a Controller). The current ATIS will continue to broadcast until you tune out of the frequency.



![Tuned to ATIS](_images/manual/frames/tuned-to-atis.png)



1. As the ATIS is broadcast, it will appear at the top of the screen to show you the latest airport information.

    

2. An on screen notification will appear to inform you that you have been automatically tuned to an active frequency, you can tap it to dismiss the message.

    

3. The communication button can be tapped to change frequencies, transmit/respond to ATC messages and to view the message log.

    


![ATIS Communication Box](_images/manual/frames/atis-communication-box.png)



1. The top left corner of the communication box shows the airport ICAO code, name, frequency and elevation on the top line. The facility and frequency tuned to on the second line (if it is an active frequency); and finally the latest METAR on the third line.

    

2. The back button can be used to select other frequencies or to tune out of the current frequency.

    

3. The last altitude, heading, speed and runway assignment issued by ATC as a reminder (these will be blank until instructions are received).

   

4. This is the message log which shows all communication history, double tap it to just show your communication with ATC.

    

## ATIS Definitions

Below are two tables that define the meaning of all REMARKS and NOTAMS that may be present in an ATIS broadcast:



| REMARKS                           | ATC Intention                                                | Pilot Actions                                                |
| :-------------------------------- | :----------------------------------------------------------- | :----------------------------------------------------------- |
| No Intersection Departures        | ATC require pilots to use the full length of the runway.     | The pilot should hold short at the end of the runway.        |
| No Pattern Work                   | ATC is not accepting pattern work.                           | The pilot should not attempt to fly patterns at the airport, this does not include a touch & go landing provided the pilot then departs the airspace. |
| Flow Control                      | ATC is controlling the departure rate.                       | The pilot should expect a delayed departure.                 |
| Long Taxi                         | ATC may not send departures to the closest runway.           | The pilot should expect to be sent to a runway that requires a long taxi time. |
| Gate Hold                         | ATC needs to freeze all outbound ground movement.            | The pilot should hold at their gate until the hold is lifted, do not send duplicate pushback requests. |
| No Light Aircraft                 | Light aircraft (XCub, C172, P38, SR22, and Spitfire) are not allowed in the airspace or at the airport. | The pilot, if flying a light aircraft, must divert to or respawn at a different airport. |
| Rolling Departures                | ATC would like expedited departures.                         | When cleared for takeoff, the pilot should enter the runway and begin their takeoff roll immediately. |
| Flight Plan Required              | ATC would like the pilot to file a flight plan before pushback/taxiing. | The pilot must file a flight plan before requesting pushback. |
| Straight Out Departures           | ATC would like aircraft to maintain runway heading until the altitude sent with the takeoff clearance is reached AND they are clear of traffic. | The pilot should fly straight until at the assigned altitude AND clear of all traffic before making any directional changes. |
| Multiple Frequencies in Use       | Controllers are using multiple frequencies to manage traffic. | The pilot should be ready to change frequencies at any time. |
| Check Forum for Event Information | ATC is referring pilots to special instructions on the IFC pages (i.e. FNF, VARB Summit) | The pilot should check the forum before flying.              |
| SID/STAR Use Recommended          | SID/STAR use is not essential for traffic management but is recommended. | The pilots should add a SID/STAR to their flight plan.       |
| SID/STAR Use Required             | SID/STAR use is essential for traffic management or for events and is being required. | The pilot must add an ATC preferred SID/STAR to their flight plan. |

| NOTAMS                     | ATC Intention                                     | Pilot Actions                                                |
| :------------------------- | :------------------------------------------------ | :----------------------------------------------------------- |
| Event in Progress          | An event is in progress.                          | The pilot may experience delays or, depending on the event, will not be allowed to participate. |
| Size Restrictions in Place | The airport cannot handle certain sized aircraft. | The pilot should think about the size of their aircraft in relation to the airport. |
| Severe Weather             | Extreme weather conditions have been reported.    | The pilot should expect high winds/turbulence.               |
| Low Visibility             | Low visibility has been reported.                 | The pilot should expect low visibility.                      |



## Pushback Communication Summary



**Communication Table - Pilot to Ground Controller**

| Request/Message  | When to Send                                                 | When Not to Send                                             |
| :--------------- | :----------------------------------------------------------- | :----------------------------------------------------------- |
| Request Pushback | When the pilot wishes to pushback, they should request a pushback clearance. | This should not be requested if the user is piloting an aircraft without pushback capabilities (C172, C208, TBM-930, SR22, XCub, F18, F22, F16, F14, A-10, Spitfire, or P-38) or is in a parking space that does not require a pushback. |



**Communication Table - Ground Controller to Pilot**

| Instruction/Message | ATC Intention                                           | Pilot Actions                                                |
| ------------------- | ------------------------------------------------------- | ------------------------------------------------------------ |
| Pushback Approved   | ATC has given the pilot clearance to pushback.          | The pilot should pushback onto the taxiway.                  |
| Hold Position       | ATC wants the pilot to immediately stop their aircraft. | If at the gate, the pilot should wait until a pushback clearance is given. If the pilot is taxiing, they should bring the aircraft to a full stop and await the “Continue Taxi” instruction. |



Step 1

: Select the active Ground frequency



![Active Ground Frequency](_images/manual/frames/active-ground-frequency.png)



Step 2

: Tap "Request Pushback"



![Request Pushback](_images/manual/frames/request-pushback.png)



Tip

: If you are in a parking spot that does not require pushback, or in an aircraft that is not capable of pushback - then make sure to just request taxi when you are ready instead!



Step 3

: Tap "Send" or "Request Specific Runway" (if you do request a runway, the available runways will appear to select from, tap the desired runway for the request to be sent)



![Send Pushback Request](_images/manual/frames/send-pushback-request.png)



Tip

: If you are going to request a specific runway, make sure it is being used in the ATIS first!



Step 4

: When you receive your pushback clearance (or other communication from the Controller), the Communication symbol will flash amber and the message will appear at the top of the screen, tap the Communication symbol to "Reply" to the message



![Reply to Pushback Clearance](_images/manual/frames/reply-to-pushback-clearance.png)



Tip

: When you receive your pushback clearance, you may be told to expect a specific runway - this means that you will most likely be instructed to taxi to that runway when you are ready so try to pushback in a direction that allows this!



## Taxi Communication Summary



**Communication Table - Pilot to Ground Controller**

| Request/Message                   | When to Send                                                 | When Not to Send                                             |
| --------------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| Request Taxi to an Active Runway  | Sent when the pilot does not have a runway preference.       | The pilot should not send this when they are actively pushing back. |
| Request Taxi to a Specific Runway | Sent when the pilot has a runway preference.                 | The pilot should not request an inactive runway, determined by the current ATIS. |
| Request Runway Crossing           | If the pilot's taxi route requires them to cross a runway, they must request permission to cross. The requested runway should be the same as the runway in use. | In any other circumstance.                                   |
| Request Frequency Change          | The pilot should request a frequency change if they wish to change frequencies and have not yet been given a clearance to do so. | The pilot should not request a frequency change from Ground when they are taxiing to a runway. The frequency change is included in the taxi instruction (“contact Tower when ready”). |



**Communication Table - Ground Controller to Pilot**

| Instruction/Message                      | ATC Intention                                                | Pilot Actions                                                |
| ---------------------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| Taxi to Runway, Contact Tower when Ready | ATC has cleared the pilot to taxi to Runway XX.              | The pilot should begin to taxi to the assigned runway.       |
| Hold Position                            | ATC wants the pilot to immediately stop their aircraft.      | If at the gate, the pilot should wait until a pushback clearance is given. If the pilot is taxiing, they should bring the aircraft to a full stop and await the “Continue Taxi” instruction. |
| Continue Taxi                            | ATC is lifting their "Hold Position" instruction.            | The pilot can continue to taxi.                              |
| Hold Short of Runway                     | ATC wants the pilot to hold short of the runway.             | The pilot should hold their entire aircraft behind the hold short line. |
| Cross Runway                             | ATC has cleared the pilot to cross the runway.               | The pilot should cross the runway. If “Please Expedite” is included, the pilot should expedite crossing. |
| Give Way to Aircraft                     | ATC wants the pilot to give way to another aircraft.         | The pilot should yield to the respective aircraft.           |
| Expect Progressive Taxi Instructions     | ATC will use progressive taxi instructions.                  | The pilot should continue as normal until given further instructions. |
| Turn Left/Right Next Taxiway             | ATC wants the pilot to turn left/right (respectively) at the next taxiway. | The pilot should turn left/right (respectively) at the next taxiway and continue taxiing until given further instructions. |
| Continue Straight Ahead                  | ATC wants the pilot to continue straight on the taxiway they are currently on. | The pilot should stay on the taxiway until given further instructions. |
| Make a 180                               | ATC wants the pilot to make a 180º turn.                     | The pilot should turn around and await further instructions. |
| Follow Aircraft Ahead                    | ATC wants the pilot to follow the aircraft ahead.            | The pilot should follow the aircraft ahead until given further instructions. |
| Continue Taxi at your Discretion         | ATC wants to let the pilot know that they are no longer subject to progressive taxi instructions. | The pilot can continue their taxi at their discretion. If any other taxi instructions are given, they should follow those. |



Step 1

: Tap "Request Taxi"



![Request Taxi](_images/manual/frames/request-taxi.png)



Step 2

: Tap "Active Runway" to send the message, or "Request Specific Runway" (if you do request a runway, the available runways will appear to select from, tap the desired runway for the request to be sent)



![Send Taxi Request](_images/manual/frames/send-taxi-request.png)



Tip

: If you are going to request a specific runway, make sure it is being used in the ATIS first!



Step 3

: When you receive your taxi clearance (or other communication from the Controller), the Communication symbol will flash amber and the message will appear at the top of the screen, tap the Communication symbol to "Reply" to the message



![Reply to Taxi Clearance](_images/manual/frames/reply-to-taxi-clearance.png)