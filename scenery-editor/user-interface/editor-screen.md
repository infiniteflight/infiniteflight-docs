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

    

2. The main [navigation bar](/guide/scenery-editor/user-interface/editor-screen#navigation-bar) allows you to change between the library of objects, properties, loaded items, log and facades

    

3. The [edit buttons](/guide/scenery-editor/user-interface/editor-screen#edit-buttons) allow you to move, copy & paste, or deleted selected buildings and objects (you can also insert points if a building is selected)

    

4. The [camera](/guide/scenery-editor/user-interface/editor-screen#camera) in use can be changed here

    

5. The [settings](/guide/scenery-editor/user-interface/editor-screen#settings) page can be shown by tapping this button




## Management Buttons



+++ File

| Button                  | Function                                                     |
| ----------------------- | ------------------------------------------------------------ |
| File Manager            | This will show details of the latest changes to the airport as well as the option to "share", "upload", "download", and "close". *Note: Airports will only be uploaded to the server when "upload complete" is shown. Downloading a version from the server will override your local device version* |
| Save                    | Saves the latest changes locally to your device              |
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
| Selection (Add)    |                                                              |
| Selection (Remove) |                                                              |
| Lock Selected      | Locks the selected building(s) and/or object(s) and prevents them from being moved or their properties adjusted |
| Unlock Selected    | Unlocks the selected building(s) and/or object(s) and allows them to be moved and their properties adjusted |
| Unlock All         | Unlocks all building(s) and/or object(s) and allows them to be moved and their properties adjusted |



Add something about selection add/remove

See freezing bits in properties for lock/unlock selected

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



Once a building or object is selected, the properties can be edited using this tab. The tables below show the options available for buildings and objects:



**Buildings**

| Button               | Function                                                     | Notes                                                        |
| -------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| Height               | This shows the height (in meters) of the building. Tap the number and then enter in a new value to adjust this | When OSM is imported it will automatically give buildings a default height but this can be manually adjusted to make sure that it looks in proportion (e.g. a hanger that you know can park a 777 inside needs to be given a height that can accommodate this) |
| Roof Orientation     | Tap the "+/-" symbols to adjust the orientation of the roof (you can also use the "Auto Roof Orientation" button) | Building roofs have a square pattern, use this tool to get the lines to match the building edges for aesthetic purposes. You can also use the [Auto Roof Orientation](/guide/scenery-editor/user-interface/editor-screen#management-buttons) by tapping Object > Auto Roof Orientation (this may still require manual adjustments) |
| Facade               | The facade group can be changed here but it will change all sides of the selected building(s) | This can be good to use if you are changing multiple buildings at the same time however you are only able to change the facade group, facade styles and individual sides of the building(s) will have to be adjusted using the [other technique](/guide/scenery-editor/buildings-and-facades/editing-facades) |
| Roof Depth           | This shows the roof depth (in meters) of the building. Tap the number and then enter in a new value between 0 and 1 to adjust this | Adds an "edge" around the building. If being used, only add to top level of buildings. |
| Latitude / Longitude | Current latitude/longitude of the building                   |                                                              |
| Altitude             | This shows the current altitude (in meters) of the building. Tap the number and then enter in a new value to adjust this | The altitude is always based on the bottom of the building. You can also use [Auto Altitude](/guide/scenery-editor/user-interface/editor-screen#management-buttons) by tapping Object > Auto Altitude if the building is positioned on top of the building you want it to go on top of (perfect for layering!) |
| Name                 | You can name the building using this field                   | OPTIONAL: we recommend labelling buildings to help keep track (e.g. "Lvl 1 Terminal 1") |
| Frozen               | Tap the "tick" symbol to toggle between the building being frozen (orange tick) and unfrozen (grey tick) | Frozen buildings cannot be edited until they have been unfrozen, this can be useful to avoid changing buildings by accident whilst editing other things nearby |
| Type                 | N/A                                                          |                                                              |



**Objects**

| Button               | Function                                                     | Notes                                                        |
| -------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| Scale                | Tap the "+/-" symbols to adjust the scale of the object      | Really useful for making objects match in size what you see from external sources (e.g. lighting AC units and blast deflectors etc.) |
| Orientation          | Tap the "+/-" symbols to adjust the orientation of the object |                                                              |
| 3D Model Name        | N/A                                                          |                                                              |
| Animations           | N/A                                                          |                                                              |
| 3D Model Ref Name    | N/A                                                          |                                                              |
| Latitude / Longitude | Current latitude/longitude of the building                   |                                                              |
| Altitude             | This shows the current altitude (in meters) of the object. Tap the number and then enter in a new value to adjust this | Always based on the bottom of the surface they you are working from. Can be adjusted here manually or go to Object > auto altitude if youre doing layering for example |
| Name                 | You can name the object using this field                     |                                                              |
| Frozen               | Tap the "tick" symbols to toggle between the building being frozen (orange tick) and unfrozen (grey tick) | Frozen buildings cannot be edited until they have been unfrozen, this can be useful to avoid changing buildings by accident whilst editing other things nearby |
| Type                 | N/A                                                          |                                                              |



**Objects (Jetbridges)**

| Button        | Function                                                     | Notes                                                        |
| ------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| Base Rotation | Tap the "+/-" symbols to adjust the orientation of the jetbridge, it is based on a default position from the base/connector and rotates counter clockwise | Orientation in [Properties](/guide/scenery-editor/user-interface/editor-screen#navigation-bar) can be used for the same function |
| Height        | Tap the "+/-" symbols to adjust the height of the jetbridge floor | Use to match the level of the aircraft door (some stands accept multiple aircraft types and so you can just pick a default height that would cater to most in these cases) |
| Extension     | Tap the "+/-" symbols to adjust the length of the jetbridge  | Try to match the jetbridge length with the external sources being used |
| Head Rotation | Tap the "+/-" symbols to moves the head of the jetbridge     | Adjust to be parallel with aircraft door                     |
| Columns       | Tap the "+/-" symbols to adjust the column height at the end of a jetbridge | Use to ensure that wheels are not above or below ground level |

+++



+++ Loaded Items



This shows a list of all buildings and objects that are currently loaded at the airport. You can scroll up/down using your finger. 

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

: Currently it is recommended to use the "Airport/Scen Editor" camera



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