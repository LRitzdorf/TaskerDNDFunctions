# TaskerDNDFunctions
Do Not Disturb-related functionality for Tasker


## Setup
Setting up this project is identical to any other Tasker project.
1. Install and open Tasker
1. Get the [`Do_Not_Disturb.prj.xml`](./Do_Not_Disturb.prj.xml) file from this repo onto your phone (probably by downloading it to your computer and transferring it to your phone's internal storage over USB)
1. Long-press any tab on Tasker's bottom bar
1. Choose `Import`
1. Navigate to and select the project XML file
1. Customize and enjoy!


## Functions
These are the various DND-related functions that this Tasker project contains.

### Auto DND (Profile)
Description

### Reload DND (Task)
Description

#### :heavy_check_mark: Activation
To use this function, go to `Settings > Preferences > Action [tab]`. Under `Quick Settings Tasks`, on any line (I recommend using the second one), tap the magnifying glass and choose the `Reload DND` task. Hit the `Back` arrow.

Open Quick Settings (swipe down from the top of your screen with two fingers) and hit the pencil icon (or whichever "edit" icon your Android version uses). Scroll down to the "Drag to add tiles" section. Tap and hold the `Reload DND` icon, and drag it up into your Quick Settings. Rearrange as desired.

### Volume Button Toggle (Profile)
Description

### Smartwatch-Volume Toggle (Profile)
Toggles DND when you hit either volume-adjustment button on your smartwatch. Default configuration works with Garmin devices. Credit for music-playing detection to Reddit's [MuppetMaster42](https://www.reddit.com/user/MuppetMaster42/), via [this post](https://www.reddit.com/r/tasker/comments/52p6h6/how_to_check_if_music_is_playing_without_an/).


## Parameters (please edit!)
This is a list of parameters that control the various DND functions available in this project, along with their locations in Tasker. Edit them! They are the conditions that make your DND setup unique.

### Auto DND
- Times: Description
- Months/Days: Description
- Location: ...

### Reload DND (Quick Settings tile)
- Quick Tile Icon: ...
- Tile Location: ...

### Volume Button Toggle
- Trigger Buttons: ...
- Trigger Time: ...

### Smartwatch-Volume Toggle
- Watch Companion App: ...
- Default Volume Level: ...
