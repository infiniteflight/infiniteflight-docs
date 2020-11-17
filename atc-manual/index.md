---
id: introduction
title: Introduction
meta: Introduction to the Infinite Flight Air Traffic Controller (IFATC) Manual.
---

# Welcome to the ATC Manual!



Welcome to the Infinite Flight Air Traffic Controller (IFATC) Manual. It is designed to help new entrants and current Controllers with IFATC procedures, as well as cover the fundamental principles associated with all controlling facilities on Infinite Flight. **All Controllers are expected to familiarize themselves with this manual and continue to do so during their time with IFATC.**{.red}



| **NOTICE BEFORE READING THIS MANUAL** |                                          |
| ------------------------------------- | ---------------------------------------- |
| **Must**{.red}                        | The use of **must**{.red} or **must not**{.red} are considered **MANDATORY**{.red} and strict compliance is **REQUIRED**{.red} |
| **Should**{.red}                      | The use of **should**{.red} or **should not**{.red} are considered **ADVISORY**{.red} and compliance is **STRONGLY RECOMMENDED**{.red} |



## Version: 20.2.2

## Last Updated: 1830Z - 17 NOV 20



+++ Summary of Changes - Version: 20.2.2 (CURRENT VERSION)

| Location | Change                                                       |
| -------- | ------------------------------------------------------------ |
| 1.1.5    | VC (Voice Channel) abbreviation added                        |
| 1A.1.3   | *#botcommands* and *#controllers[1-5]* added                 |
| 1A.1.4   | Available commands updated                                   |
| 1A.1.5   | Introduction of guidance for use of Voice Channels within Discord |
| 1A.2.1   | Changes made to accommodate the use of Voice Channels        |
| 1A.2.1   | Region changeover grace period reduced from 1 hour to 30 minutes |
| 4.1.3    | Minor wording correction (broadcast of ATIS change only required on Ground/Tower - currently not available on Radar) |
| 5.2.1    | Minor restructuring of paragraph                             |
| 6.2.3    | Minor wording correction                                     |
| 6.8.9    | A key for flight plan approach prefixes added                |
| 6.9.2    | The GPS Approach is authorized provided the pilot has a published procedure in their flight plan (and not just random waypoints) leading to the intended arrival runway |
| 7.1.4    | Minor wording correction (1 day changed to 24 hour period)   |
| 7.3.4    | Automatic fail if aircraft separation lost in The Initial Practical Test |
| 7.5.6    | Automatic fail if terrain/aircraft separation lost in The Radar Practical Test |
| 7A.1.7   | *#trainer-trainee[1-3]* added                                |
| 7A.1.8   | Trainer specific guidance for use of Voice Channels within Discord |
| 7A.2.8   | Initial and Radar Trainer Checklist incorporated from Google Docs |
| 7B.2.1   | Maximum aircraft permitted at The Initial Practical Test added |
| 7B.3.1   | Maximum aircraft permitted at The Radar Practical Test added |
| 7C.1.4   | *#trainer-trainee[1-3]* added                                |
| 7D.1.3   | Activity requirements added                                  |
| 7D.4.1   | Guidance on adding notes to Controller's records included    |

+++



+++ Summary of Changes - Version: 20.2.1

| Location        | Change                                                       |
| --------------- | ------------------------------------------------------------ |
| 1.1.3           | Minor wording correction to accommodate Discord migration    |
| 1A.1 - 4        | Minor wording corrections to accommodate Discord migration   |
| 1A.1.3          | Channel purposes adjusted for Discord as well as the addition of new channels (i.e. *#announcements*, *#infinite-flight-rules*, *#offtopic* and *#role-assignments*). #issues channel removed |
| 1A.2.1          | Controllers Discord Nickname **must**{.red} be the same as their IFC Username. In addition, Controllers **must**{.red} link their Community Forum Account before controlling |
| 1A.5.1          | Minor wording correction to accommodate Discord migration    |
| 1B.2.2          | Minor wording correction to accommodate Discord migration    |
| 7.5.1           | Minor wording correction to accommodate Discord migration    |
| 7.5.5           | Minor wording correction to accommodate Discord migration    |
| 7A.1.7          | Minor wording correction to accommodate Discord migration    |
| 7A.2.5          | Minor wording correction to accommodate Discord migration    |
| 7A.3.3          | Minor wording correction to accommodate Discord migration    |
| 7B.1.1          | Minor wording correction to accommodate Discord migration    |
| 7B.1.2          | Reference to *#testers[1-3]* Discord channels added          |
| 7B.1.3 / 7B.1.4 | Original 7B.1.2/7B.1.3 moved down by one to 7B.1.3/7B.1.4 respectively |
| 7C.1.4          | Addition of Discord Channel information for Recruiters       |
| 7C.2.2          | Minor wording correction to accommodate Discord migration    |
| 7C.4.1          | Minor wording correction to accommodate Discord migration    |
| 7D.1.1          | Minor wording correction to accommodate Discord migration    |
| 7D.3.1          | Minor wording correction to accommodate Discord migration    |

+++



+++ Summary of Changes - Version: 20.2

| Location        | Change                                                       |
| --------------- | ------------------------------------------------------------ |
| 1A.1.5          | */training* Slack slash command description updated          |
| 1A.2.1          | Controlling Rules updated - "bounds of the ATC Schedule" defined to add clarification on what airports to open |
| 1A.2.1          | Controlling Rules updated - clarification on region changeover times |
| 1A.3.3          | Minor wording correction                                     |
| 1B.1.6          | Removal of "Unable to Communicate" from the Violation list - Controllers can still use this however it will disconnect the pilot from their current session without issuing a Violation |
| 2.3.4           | Reference added to the use of the back-taxi command when taxiways are not aligned for runway crossings |
| 3.2.2           | Introduction of "Ready for Departure in Sequence"            |
| 3.2             | 3.2.2 - 3.2.8 all moved down one (i.e. 3.2.3 - 3.2.9)        |
| 3.5.1           | Hyperlink fixed                                              |
| 3.5.4           | Minor wording correction                                     |
| 5.1.1           | Minor wording correction                                     |
| 6.2.3           | Clarity added on separation requirements when aircraft make initial contact with Radar Controllers |
| 6.2.4           | 6.2.3 moved to 6.2.4                                         |
| 6.4.4           | Check In wording adjusted to reflect changes to Flight Following - Check In is now a IFR service ONLY |
| 6.5             | Reworked - Flight Following is now a VFR service ONLY        |
| 6.6.2           | Check In wording adjusted to reflect changes to Flight Following - Check In is now a IFR service ONLY |
| 6.12.3          | Minor wording correction                                     |
| 6.13.3          | Minor wording correction                                     |
| 6.13.4          | Further clarification added on when Radar Controllers handover to Tower Controllers |
| 6.14.6 - 8      | Speed Control sub-section added                              |
| 7.1.3           | Definitions table updated                                    |
| 7.3.2           | Updated minimum requirements for Candidates to receive Training |
| 7.5             | Various changes to ensure it is up to date with current procedures |
| Section 7A - 7D | Various changes to ensure it is up to date with current procedures |

+++


