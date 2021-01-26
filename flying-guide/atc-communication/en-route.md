---
id: en-route
title: En-Route
meta: Learn how to communicate en-route instructions with ATC in Infinite Flight.
order: 5
contributor: babacar,lucaviness,planegeek,finn-14,Filipe_Samuel_Braine
---

# En-Route



## En-Route Communication Summary



Step 1

: If you were sent "Frequency change approved, good day" then there is currently no Controller active in your area - we recommend just tuning out of the current frequency by tapping "Tune out of [airport ICAO code] [facility]" and continuing en-route. If you have been handed off to an active frequency, it will give you two options, either "Send & Switch" (which will reply and automatically tune you to the next frequency) or "Send" (which will reply but you will then need to tune to the next frequency manually)



![Send and Switch](_images/manual/frames/send-and-switch.png)



Step 2

: Once you are tuned into the Radar Controller's frequency, the following table outlines which requests can be transmitted: 



| Departure Type      | Check In [IFR] | Flight Following [VFR] |
| ------------------- | -------------- | ---------------------- |
| With Flight Plan    | Yes            | No                     |
| Without Flight Plan | No             | Yes                    |



![Initial Contact](_images/manual/frames/initial-contact.png)



Tip

: Make sure to only make ONE request, multiple transmissions increase Controller workload and could result in a [Violation](/guide/getting-started/pilot-user-interface/violation-reasons#spamming-frequency---unecessary-duplicate-requests)!



Step 3

: Make sure to monitor the airspace you are flying in, if you notice you are about to enter an active area or have been sent an "On-Guard" message, tune into the frequency. Below is a summary of the lateral and vertical boundaries of the different facilities:



| Facility           | Vertical Jurisdiction | Lateral Boundary                                     |
| ------------------ | --------------------- | ---------------------------------------------------- |
| Tower              | SFC - 5000ft AAL      | Most immediate ring/boundary surrounding the airport |
| Departure/Approach | SFC - 18,000ft/FL180  | 50nm                                                 |
| Center             | SFC - 60,000ft/FL600  | White boundaries                                     |



Note: Airspace parameters and ATC jurisdictions may be altered with the use of NOTAMs and/or TFRs during special events

![Image 5.1.1.1 - Airspace layout](_images/manual/graphics/atc-airspace-layout.png)



## Pilot to Radar Controller Communication Table

| Request/Message           | When to Send                                                 | When Not to Send                                             |
| ------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| Request Approach          | The pilot should request an approach if they want an ILS, GPS, or visual approach provided. | In any other circumstance.                                   |
| Request Flight Following  | The pilot can request this if they want to fly into their destination without receiving an approach. If approved, they are free to follow their flight plan and have discretion over their altitude. | This service should not be requested after Checking In.      |
| Request Radar Vectors     | If the pilot does not want an ILS, GPS, or visual approach, and they have not requested another service, they can request radar vectors. ATC will vector them onto a VFR pattern leg and hand them off to Tower/Unicom at pattern altitude. | In any other circumstance.                                   |
| Request Altitude Change   | If the pilot is within 1,000ft of terrain or is within 3NM/1,000ft of another aircraft, they should request this. ATC will check their surroundings and take action if necessary. The pilot can also request this if they want to climb past their initial cruising altitude. | The pilot should not request this upon departure. Checking In gives the pilot discretion over their altitude. |
| Executing Missed Approach | The pilot may announce a missed approach if they are unable to continue their approach. If going around, this should be sent to the radar controller upon contact. | In any other circumstance.                                   |
| Check In                  | The Check In is primarily used with Center and Departure. Approval authorizes the pilot to follow their own lateral and vertical guidance filed in their FPL. | The pilot should not Check In with approach. Instead, they should simply request an approach. |
| Request Descent via STAR  | The pilot should request this if they are 1 minute away from their top of descent (TOD) and have a STAR filed. | If Radar tells the pilot to state their approach request, the pilot should not request a descent. |
| Request Frequency Change  | The pilot should request a frequency change if they wish to change frequencies and have not yet been given a clearance to do so. | The pilot should not use this impatiently. Frequency changes will not always be given immediately. |
| Airport In Sight          | The pilot may report airport in sight if they can see the airport while on a visual approach. | In any other circumstance.                                   |



## Radar Controller to Pilot Communication Table


| Instruction/Message                              | ATC Intention                                                | Pilot Actions                                                |
| ------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| Continue As Filed                                | ATC would like the pilot to continue flying at their discretion. | The pilot should continue as filed; all altitude changes and directional changes do not require clearances. |
| Resume Own Navigation                            | ATC would like the pilot to navigate on their own.           | The pilot should continue to navigate at their discretion; all directional changes do not require clearances. All altitude changes do. |
| Speed at Your Discretion                         | ATC would like the pilot to manage their own speed.          | The pilot may fly at any safe speed, following speed restrictions. |
| Maintain Present Speed                           | ATC wants the pilot to maintain their current speed until told otherwise. | The pilot should check their speed and maintain that until told otherwise. |
| Maintain Slowest Practical Speed                 | ATC wants the pilot to fly as slow as is safe.               | The pilot should decrease their speed as much as possible.   |
| Maintain Best Forward Speed                      | ATC wants the pilot to fly as fast as is safe.               | The pilot should increase their speed as much as possible.   |
| Adjust Speed to Follow Aircraft ahead.           | ATC wants the pilot to slow down to maintain separation with the aircraft ahead. | The pilot should adjust their speed so that they are flying at or less than the speed of the aircraft ahead. |
| Please Expedite Altitude Change                  | ATC wants the pilot to expedite their altitude change.       | The pilot should increase their vertical speed to descend or ascend expeditiously. |
| Amend Flight Plan to Include ATC Preferred STAR. | ATC needs to regulate traffic flow.                          | The pilot should add an ATC preferred STAR to their flight plan. |
