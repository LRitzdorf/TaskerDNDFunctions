# TaskerDNDFunctions
Handy Do Not Disturb-related functionality for [Tasker](https://play.google.com/store/apps/details?id=net.dinglisch.android.taskerm), the ultimate Android automation app.

If you were sent here after importing this project, read below for setup and usage tips!


## Setup

### Standard
Setting up this project is identical to any other Tasker project.
1. Install and open Tasker
1. Get the [`Do_Not_Disturb.prj.xml`](./Do_Not_Disturb.prj.xml) file from this repo onto your phone (probably by downloading it to your computer and transferring it to your phone's internal storage over USB)
1. Long-press any tab on Tasker's bottom bar
1. Choose `Import`
1. Navigate to and select the project XML file
1. Customize and enjoy!

### TaskerNet
This project is available on TaskerNet! On your phone, go to <https://taskernet.com/shares/?user=AS35m8k80GaDd5dXaSh1zON%2FjeGpbCvKMUpxEUgWrnJlmyY98C1z2BEwlM1TmxR2BoGhlXGYlNWh&id=Project%3ADo+Not+Disturb>, hit the green `Import` button, and confirm. Customize and enjoy!


## Functions
These are the various Do Not Disturb (DND) -related functions that this Tasker project contains.

### Custom DND (Profile)
Useful mainly as a template, to duplicate and customize. Contains several example triggers, including location (ideal for work or school), other active profiles (to prevent DND activation with headphones, for example), time period (9AM - 5PM by default), and day of week (Monday - Friday). It will deactivate if any of these conditions becomes false - for example, you leave for lunch - and reactivate when the condition becomes true again.

### Calendar DND (Profile)
Activates DND during calendar events whose description contains a trigger phrase. The trigger pattern is actually a regular expression, read in from the `%dndCalendarTrigger` variable, and is set to `DND` by default. Feel free to customize this! (If you're not familiar with "regex," don't worry - unless you have some special characters in your trigger, just setting `%dndCalendarTrigger` to that phrase should work. If you want to learn more, <https://regex101.com> is an excellent resource!)

### Reload DND (Task)
Refreshes the specified profiles. For example: you can manually turn DND off (by tapping the icon in Quick Settings, usually) to play a video for a friend, but then the Custom DND function is deactivated. Reload DND reactivates Custom DND, so you can still use it after manually turning off DND mode.

The Reload DND task reads a list of profiles to reload from the `%dndTasks` variable. This is set to `Custom DND,Calendar DND`, to work with the profiles that are present by default, but can be edited to change which profiles are reloaded as you add your own!

#### :heavy_check_mark: Quick Tile Setup
To use this function, it needs to be added to Android's Quick Settings for you to trigger - it will not trigger automatically.

To do this, go to `Settings > Preferences > Action [tab]`. Under `Quick Settings Tasks`, on any line (I recommend using the second one), tap the magnifying glass and choose the `Reload DND` task. Hit the `Back` arrow.

Open Quick Settings (swipe down from the top of your screen with two fingers) and hit the pencil icon (or whichever "edit" icon your Android version uses). Scroll down to the "Drag to add tiles" section. Tap and hold the `Reload DND` icon, and drag it up into your Quick Settings. Rearrange as desired.

### Volume Button DND Toggle (Profile)
Toggles DND when you press and hold either volume button (customizable, see below) for one second (also customizable). Note that, due to a limitation of Tasker, this only works while the phone screen is on. Great for discreetly silencing your phone without having to take it out of a bag or pocket!

### Smartwatch Volume DND Toggle (Profile)
Toggles DND when you hit either volume-adjustment button on your smartwatch (if music is not playing). An even better version of the volume-button toggle - you don't even have to be within reach of your phone! Default configuration works with Garmin devices, on *some* Android versions (Android 11 is known __not__ to work). Credit for music-playing detection to Reddit's [MuppetMaster42](https://www.reddit.com/user/MuppetMaster42/), via [this post](https://www.reddit.com/r/tasker/comments/52p6h6/how_to_check_if_music_is_playing_without_an/).


## Parameters (please edit!)
This is a list of parameters that control the various DND functions available in this project, along with their locations in Tasker. Edit them! They are the conditions that make your DND setup unique.

Note that __all__ profile triggers (on the left side under each profile) must be active for a profile to trigger. Feel free to add or remove triggers as desired!

### Custom DND
- Location: The location at which DND should be active, for example school or work. Note that this includes both a center point and a radius. `Profiles > Custom DND > [first trigger, flag icon]`
- `Other Sound Profiles Inactive` condition: Use `%PACTIVE` not matches `*,Profile Name Here,*` to not trigger when other conditions are active, like headphones. `Profiles > Custom DND > [second trigger, half-shaded circle icon]`
- Times: The time range over which DND should be active, for example 9:00 AM to 5:00 PM (default). `Profiles > Custom DND > [third trigger, clock icon]`
- Months/Days: The months and days of the week during which DND should be active, for example weekdays in September through May. `Profiles > Custom DND > [fourth trigger, calendar icon]`

### Reload DND (Quick Settings tile)
- Quick Tile Icon: The icon that represents this task in Quick Settings. `Tasks > Reload DND > [reload icon at bottom center]`
- Quick Tile Location: The Quick Settings tile can be moved around in your Quick Settings sheet. See the __Quick Tile Setup__ section, above, for relevant instructions.

### Volume Button DND Toggle
- Trigger Buttons: Which volume buttons cause DND to be toggled. `Profiles > Either Volume DND Toggle > [bell icon trigger] > Types`
- Trigger Time: How long the selected button must be held to cause DND to be toggled. `Profiles > Either Volume DND Toggle > [bell icon trigger] > Additional Time` (use magnifying glass button)

### Smartwatch Volume DND Toggle
- Watch Companion App: If your smartwatch allows you to change your *phone's* volume level, this may work. Choose the package name of the app that your watch uses to sync with your phone (e.g. Garmin Connect Mobile is `com.garmin.android.apps.connectmobile`). `Profiles > Watch Volume DND Toggle > [bell icon trigger] > Filter` (change the package name following `caller=`)
    - This profile was created and tested on Android 8 using Garmin Connect Mobile. It does not seem to work on Android 11. This profile is best for users who are comfortable playing with settings until something works.
- Default Volume Level: Since there is no reliable way to determine whether the watch's volume up or down button was pressed, the phone's media volume is simply reset to a default level after the volume change occurs but before DND is activated. `Profiles > Watch Volume DND Toggle > [profile task, to the right of the green arrow] > Media Volume [third item] > Level`

## Further Customization
Please don't hesitate to further customize this project! If you have Tasker, there's a fairly good chance you know how to use it, so let your creativity go wild! If you're not that familiar with Tasker, I would certainly recommend learning about it. There's almost nothing it can't do!

