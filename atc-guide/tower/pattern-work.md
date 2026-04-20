---
id: pattern-work
title: Pattern Work
meta: How to manage the pattern, transitions and flight of xx when operating a tower facility within Infinite Flight.
order: 4
---



# Pattern Work

The traffic pattern is a standard flight path followed by aircraft when taking-off and landing while maintaining visual contact with the airport. In Infinite Flight the pattern altitude is 1000ft AAL (above aerodrome level) for prop aircraft, and 1500ft AAL for jet aircraft. It consists of multiple legs, each being joined by a 90 degree turn, and these are shown in the image below:



![The Traffic Pattern](_images/manual/graphics/atc-traffic-pattern.jpg)



Manual

: For Pattern Work to be allowed, Visual Meteorological Conditions (VMC) **must**{.red} exist, aircraft **must**{.red} be able to fly a standard pattern and traffic levels need to be manageable. [More info?](/guide/atc-manual/3.-tower/3.4-pattern-work-transitions-flight-of-xx#3.4.1) 



For a step by step guide on how to issue pattern entries, sequencing and clearances, make sure to check out the [Inbounds](/guide/atc-guide/tower/inbounds) page.



+ SCENARIO - Re-sequencing to control the size of the pattern 

::: scenario-heading
Scenario
:::

::: scenario
*I-DRUM* and *N1DC* have both already been sequenced and cleared for RWY05L. As both aircraft continue downwind, *I-DRUM* has gone further downwind than the Controller expected.
::: 

![](_images/manual/screens/atcg-pw-downwind.png){.scenario}

| Technique 1                                                  |
| ------------------------------------------------------------ |
| 1: Re-clear *N1DC* as number 1                               |
| 2: Re-sequence *I-DRUM* as number 2                          |
| 3: If you are concerned about separation, you can tell *I-DRUM* to "extend downwind, I'll call your base" to alleviate this |

{.technique}

| Technique 1       | Pro or Con?                                                |
| ----------------- | ---------------------------------------------------------- |
| :fa-check-circle: | Efficient                                                  |
| :fa-check-circle: | Greater Pilot satisfaction                                 |
| :fa-times-circle: | May increase workload as you have to send various commands |

{.prosandcons}

| Technique 2                                          |
| ---------------------------------------------------- |
| 1: Instruct *I-DRUM* to "turn base"                  |
| 2: This will force *I-DRUM* to fly a tighter pattern |

{.technique}

| Technique 2       | Pro or Con?                                                  |
| ----------------- | ------------------------------------------------------------ |
| :fa-check-circle: | Can be efficient                                             |
| :fa-times-circle: | Some pilots/aircraft may not be able to fly as tight a pattern |

{.prosandcons}

+++


+ SCENARIO - Re-sequencing more then one aircraft on the opposite downwind 

::: scenario-heading
Scenario
:::

::: scenario
*YU-MMY* is number 1 for runway 10R, *G-ZZJB* is sequenced number 2 for runway 10R, *G-RIZZ* is number 1 for runway 10L and *N623KB* is sequenced number 2 for runway 10L. *YU-MMY* then asks for a RWY change to 10L. 
::: 

[Insert requested by Regan]

{.scenario}

| Technique 1                                                  |
| ------------------------------------------------------------ |
| 1: Instruct *YU-MMY* to "enter right downwind RWY10L, number 2, traffic to follow is on left downwind” |
| 2: If you are concerned about a conflict on base between *‌G-RIZZ* and *YU-MMY*, then you can also tell *G-RIZZ* to "turn base" ahead of *YU-MMY* to alleviate this | 
| 3: When you clear *YU-MMY* for the option, you can then tell them to “make left traffic” if you wish to do so to move them onto that side for subsequent patterns |
| 4: Issue *N623KB* a re-sequence to follow *‌G-RIZZ* “number 3, traffic to follow is on left downwind” |

{.technique}

| Technique 1       | Pro or Con?                                 |
| ----------------- | ------------------------------------------- |
| :fa-check-circle: | *YU-MMY* will not have to extend downwind and the controller will have to issue less commands, lightening the pilot’s and controller’s workload                             |
| :fa-times-circle: | *N623KB* is in a C172 and you could accommodate a shorter downwind for them by sequencing *YU-UMMY* number 3 to follow *N623KB* | 

{.prosandcons}


Tip

: Aircraft performance should be taken in to account when sequencing aircraft. Controllers should try to accommodate a shorter pattern for slower performance aircraft. 

| Technique 2                                                  |
| ------------------------------------------------------------ |
| 1: Instruct *G-ZZJB* to "turn base”                     |
| 2: Instruct *YU-MMY* to “enter right downwind RW10L, number 3 traffic to follow is on left downwind” |
| 3: To alleviate the risk of confusion between pilots you can instruct *YU-UMMY* to “extend downwind, I’ll call your base” to ensure there is no conflict with *N623KB* |
| 4: You can instruct *N623KB* to turn base when appropriate so *YU-UMMY* doesn’t have to extend downwind as far |
| 5: Instruct *YU-MMY* to “turn base” when adequate spacing is achieved between them and *N623KB* | 

{.technique}

| Technique 2       | Pro or Con?                                                  |
| ----------------- | ------------------------------------------------------------ |
| :fa-check-circle: | Accommodates a shorter pattern for *N623KB*  |
| :fa-times-circle: | Higher workload for the controller with the risk of confusion between pilots |

{.prosandcons}

+++



## Transitions

Transitions can be requested by aircraft when they are not with a radar facility and are transiting through the tower controller's airspace. For Infinite Flight, Tower airspace is defined as the most immediate ring/boundary surrounding the airport and up to 5000ft AAL (therefore if the elevation of the airport is 1000ft, the tower’s airspace would be 1000ft – 6000ft).



Manual

: A transition **must**{.red} only be approved within tower’s airspace (so in the example above, no higher than 6000ft). Separation **must**{.red} be applied if the Tower Controller has aircraft in the pattern. [More info?](/guide/atc-manual/3.-tower/3.4-pattern-work-transitions-flight-of-xx#3.4.2)



@[vimeo](563250409)



Step 1

: When an aircraft requests a transition, the aircraft symbol will flash amber on the map as well as their callsign on the flight progress strip



Step 2

: Either tap the aircraft on the map (and then "Other Message"), or the flight progress strip to bring up the communication menu



Step 3

: Determine an altitude that will keep the aircraft within tower's airspace, but also provide separation with traffic that may be in the pattern



Step 4

: Tap "Respond to Transition > [select <10,000ft / >=10,000ft ] > [select altitude]"



Tip

: A minimum of 500ft is required between VFR traffic however we recommend giving a transition that provides a minimum of 1000ft separation to satisfy IFR requirements too!



## Flight of XX



Manual

: When controlling aircraft using the "Flight of XX" callsign, you **must**{.red} only send commands to the lead aircraft and treat the flight of xx as one aircraft. [More info?](/guide/atc-manual/3.-tower/3.4-pattern-work-transitions-flight-of-xx#3.4.5)



@[vimeo](563261625)



Step 1

: When the lead aircraft makes a request, the aircraft symbol will flash amber on the map as well as their callsign on the flight progress strip



Step 2

: Either tap the aircraft on the map (and then "Other Message"), or the flight progress strip to bring up the communication menu 



Tip

: It may be easier to use the flight progress strip as multiple aircraft flying in formation can make tapping the aircraft on the map a bit tricky!
