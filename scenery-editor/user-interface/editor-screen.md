---
id: editor-screen
title: Editor Screen
meta: Learn how the user interface of the Editor Screen works.
order: 1
---

# Editor Screen

Welcome to the editor screen within the Infinite Flight app. Below you’ll find everything you need to know about the user interface!



![Scenery Editor Screen](_images/manual/frames/scenery-editor-screen.png)



1. The [management buttons](/guide/scenery-editor/user-interface/editor-screen#management-buttons) allow you to manage files, edit recent activity, change the view, adjust object altitude, change roof orientation, change building facades, and edit buildings

    

2. When a new editing session is started (even if you remain in-app), it will reset the "Last Saved" on the bottom bar to "N/A" (note: anything previously saved will still be there as the "last saved" information is only specific to the current editing session)

    

3. The main [navigation bar](/guide/scenery-editor/user-interface/editor-screen#navigation-bar) allows you to change between the library of objects, properties, loaded items, log and facades

     

4. The [edit buttons](/guide/scenery-editor/user-interface/editor-screen#edit-buttons) allow you to move, copy & paste, or deleted selected buildings and objects (you can also insert points if a building is selected)

     

5. The [camera](/guide/scenery-editor/user-interface/editor-screen#camera) in use can be changed here

   

6. The [settings](/guide/scenery-editor/user-interface/editor-screen#settings) page can be shown by tapping this button




## Management Buttons



+++ File

| Button                  | Function                                                     |
| ----------------------- | ------------------------------------------------------------ |
| File Manager            | This will show details of the latest changes to the airport as well as the option to "share", "upload", "download", and "close". *Note: Airports will only be uploaded to the server when "upload complete" is shown. Downloading a version from the server will override your local device version* |
| Save                    | Saves the latest changes locally to your device. *Note: The autosave function will automatically save once every minute to ensure work is not lost* |
| Save Selected as Bundle | Select a group of buildings and/or objects and then tap this button to save them as a bundle for future use to speed up editing times |
| Share Selected Bundle   | By selecting the bundle you wish to share from the "Library", you can then tap this button to share it with other airport scenery editors |
| Download OSM            | By tapping this button, the Open Street Map data will be downloaded which will usually provide most of the buildings within (and close to) the airport boundaries |
| Download OSM at Cursor  | If buildings are missing or you accidentally delete some, you can download the OSM data at the cursor point with this button (it has an approximate range of 200 meters) |
| Import GeoJson          | GeoJson files can be imported using this button              |
| Scenery Stats           | This shows key stats about the objects currently placed including poly count |

+++



+++ Edit

| Button             | Function                                                     |
| ------------------ | ------------------------------------------------------------ |
| Undo               | Undo your latest edit                                        |
| Redo               | Redo your latest edit                                        |
| Selection (Add)    | Create a selection of several objects to move or edit them as a group. While "Selection (Add)" is active, all objects you select [by tapping on them or using the "rectangular selection tool"](/guide/scenery-editor/objects/selection-and-placement#selecting-and-placing-an-object) will be added to the selection |
| Selection (Remove) | Objects that are selected [by tapping on them or using the "rectangular selection tool"](/guide/scenery-editor/objects/selection-and-placement#selecting-and-placing-an-object) while the "Selection (Remove)" feature is active are removed from the existing selection |
| Lock Selected      | Locks the selected building(s) and/or object(s) and prevents them from being moved or their properties adjusted. For more information check out the Frozen function within [Properties](/guide/scenery-editor/buildings-and-facades/properties) |
| Unlock Selected    | Unlocks the selected building(s) and/or object(s) and allows them to be moved and their properties adjusted. For more information check out the Frozen function within [Properties](/guide/scenery-editor/buildings-and-facades/properties) |
| Unlock All         | Unlocks all building(s) and/or object(s) and allows them to be moved and their properties adjusted |

+++



+++ View

| Button              | Function                                                   |
| ------------------- | ---------------------------------------------------------- |
| Hide Buildings      | Currently not in use                                       |
| Show Start Location | Shows all locations that aircraft are able to spawn in-app |
| Facade Editor       | Currently not in use                                       |

+++



+++ Object

| Button                | Function                                                     |
| --------------------- | ------------------------------------------------------------ |
| Auto Roof Orientation | Automatically aligns the selected building's roof            |
| Auto Altitude         | Automatically adjusts the altitude of the selected building(s) and/or object(s) so that they sit on top of the building(s) that they are currently place within |

+++



+++ Building

| Button                | Function                                                     |
| --------------------- | ------------------------------------------------------------ |
| Set Texture & Facades | Once a building is selected, facades can be selected and changed |
| Edit Building         | Once a building is selected, this button allows you to edit  |

+++



## Navigation Bar



+++ Library

This contains a repository of all available objects that can be used. To add an object, follow the steps below:



Step 1

: Scroll up/down using your finger to see all objects



Step 2

: Tap the object **(1)** that you want to add



Step 3

: Tap on the airport **(2)** to move the white cursor to the location where you would like the object to be located



Step 4

: Tap "Add Object" **(3)**



![Adding Objects](_images/manual/frames/adding-object.png)

+++



+++ Properties

The properties tab will vary based on whether [buildings](/guide/scenery-editor/buildings-and-facades/properties), [objects](/guide/scenery-editor/objects/properties) or [jetbridges](/guide/scenery-editor/objects/properties#jetbridges) are selected.

+++



+++ Loaded Items



This shows a list of all buildings and objects that are currently loaded at the airport. You can scroll up/down using your finger.



> Tapping on an item within the list will select the object and show the ["changing orientation"](/guide/scenery-editor/objects/selection-and-placement#changing-orientation-of-an-object) movement symbols to make it easy to identify at your airport 

+++



+++ Log



This logs the activity of the app (not your editing).

+++



+++ Facades

This contains a repository of all available facade styles and their respective faces.

+++



## Edit Buttons



| Button           | Function                                                     |
| ---------------- | ------------------------------------------------------------ |
| Select/Move      | Toggle between these two buttons to be able to select or move buildings and objects |
| Copy/Paste       | These buttons can be used to copy and paste the selected buildings and objects |
| Delete Selection | This button will delete the select buildings and objects     |
| Insert Point     | When editing buildings, this button allows a node to be inserted which can be used to adjust the shape of the building. *Note: before inserting a node, you must select a node on the building - the new node will be inserted to the left of the selected one* |



## Camera



Tip

: Currently it is recommended to use the "Airport/Scen Editor" camera when editing however the "Free" camera is particularly useful for positioning the ATC Tower (for more info, see the ATC Tower tab under [Objects](/guide/scenery-editor/objects/objects))



@[vimeo](558260851)



## Settings



Currently there are no new settings. Please look at the [Getting Started Guide](https://infiniteflight.com/guide/getting-started/home-user-interface/settings) for more information. 



## In-App Ruler

To use the ruler, follow the steps below:



Step 1

: Place two fingers on your device's screen and hold



Step 2

: A rule will appear (both fingers must remain on the screen whilst using the ruler)



Step 3

: The ruler can then be used to measure by sliding your two fingers on the screen. It will provide measurements in meters, feet and nautical miles as well as bearing information 



Tip

: Make sure to have on screen what you would like to measure (the ruler will disappear if you try to move the camera)



Step 4

: When you are finished with the ruler, simply remove your fingers from the screen