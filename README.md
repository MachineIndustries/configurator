# configurator

## Current version: 1.1.5


## What does it do?

The configurator is, like it's name suggests, an app for configuring keyboards, without all that messing around with firmware code. It's cross-platform, relatively lightweight, and it's built on top of the QMK firmware, which is pretty well established and tested, so the firmwares it generates are rock-solid.

The information in this readme is taken from: http://www.machineindustries.co/guides/configurator-manual

[Installing](https://github.com/CountParadox/configurator/blob/master/README.md#installing)

- [For macOS & Linux](https://github.com/CountParadox/configurator/blob/master/README.md#for-macos--linux)
- [For Windows](https://github.com/CountParadox/configurator/blob/master/README.md#for-windows)

[Overview](https://github.com/CountParadox/configurator/blob/master/README.md#overview)

[Selecting a board](https://github.com/CountParadox/configurator/blob/master/README.md#selecting-a-board)

[Configuring a key](https://github.com/CountParadox/configurator/blob/master/README.md#configuring-a-key)

- [To be a regular key](https://github.com/CountParadox/configurator/blob/master/README.md#to-be-a-regular-key)
- [To be a board action](https://github.com/CountParadox/configurator/blob/master/README.md#to-be-a-board-action)
- [To be a macro](https://github.com/CountParadox/configurator/blob/master/README.md#to-be-a-macro)
- [To do nothing](https://github.com/CountParadox/configurator/blob/master/README.md#to-do-nothing)

[Macros](https://github.com/CountParadox/configurator/blob/master/README.md#macros)

- [Overview](https://github.com/CountParadox/configurator/blob/master/README.md#overview-1)
- [Add a key to a macro](https://github.com/CountParadox/configurator/blob/master/README.md#add-a-key-to-a-macro)
- [Setting key up, down & type actions](https://github.com/CountParadox/configurator/blob/master/README.md#setting-key-up-down--type-actions)
- [Removing a key from the macro](https://github.com/CountParadox/configurator/blob/master/README.md#removing-a-key-from-the-macro)
- [Re-arranging a macro](https://github.com/CountParadox/configurator/blob/master/README.md#re-arranging-a-macro)
- [Saving the macro](https://github.com/CountParadox/configurator/blob/master/README.md#save-the-macro)
- [Cancel the macro](https://github.com/CountParadox/configurator/blob/master/README.md#cancel-the-macro-1)

[Layers](https://github.com/CountParadox/configurator/blob/master/README.md#layers)

- [Overview](https://github.com/CountParadox/configurator/blob/master/README.md#overview-2)
- [Changing layers](https://github.com/CountParadox/configurator/blob/master/README.md#changing-layers)
- [Adding keys to other layers](https://github.com/CountParadox/configurator/blob/master/README.md#adding-keys-to-other-layers)

[Backlighting](https://github.com/CountParadox/configurator/blob/master/README.md#backlighting)

- [Overview](https://github.com/CountParadox/configurator/blob/master/README.md#overview-3)
- [Setting the backlight](https://github.com/CountParadox/configurator/blob/master/README.md#setting-the-backlight)

[Saving configurations for later](https://github.com/CountParadox/configurator/blob/master/README.md#saving-configurations-for-later)

[Loading saved configurations](https://github.com/CountParadox/configurator/blob/master/README.md#loading-saved-configurations)

[Compiling & uploading configurations](https://github.com/CountParadox/configurator/blob/master/README.md#compiling--uploading-configurations-to-your-keyboard)

## Installing

### For macOS & Linux

Installing the configurator for macOS & Linux is super-simple, just download the latest configurator, run the installer and install the configurator to your applications directory and you're ready to go.

### For Windows
Installing for Windows is a little more complicated than for Mac or Linux. Windows requires a couple of drivers to be installed before the configurator will run properly. Let's break it down into 5 steps:

**Step 1**

Download the Configurator drivers for Windows. Extract this to somewhere you'll remember, for example C:\USERS\DEFAULT\M-SERIES-DRIVER\

**Step 2**

Plug in your device into one of the computers USB ports. Pretty easy step.

**Step 3**

Press the RESET button on your configurator-compatible keyboard. Again, keeping it simple.

**Step 4**

Here's where it gets a bit more complicated. Open up your DEVICE MANAGER, opening this varies depending on your Windows version but you'll find it in the CONTROL PANEL.

Look for LUFA DFU. Right click LUFA DFU then click PROPERTIES, click the DRIVER tab followed by pressing the UPDATE DRIVER button.

Still following? Good, proceed by clicking BROWSE MY COMPUTER FOR DRIVER SOFTWARE then LET ME PICK FROM A LIST OF DEVICE DRIVERS ON MY COMPUTER.

**Step 5**

Continue on by pressing the HAVE DISK button. Navigate to where you extracted the downloaded file, for example: C:\USERS\DEFAULT\M-SERIES-DRIVER\. Select the .inf file in the root folder.

**Step 6**

[Download the latest configurator](https://github.com/MachineIndustries/configurator/releases/latest), install, open the configurator and breathe a sigh of relief, you're all done!

## Overview

Before we start digging in any further, here's a quick overview of the interface:

![Image of configurator](http://www.machineindustries.co/uploads/guides/configurator-manual/overview.png "configurator main screen")

1. Selected board. click this to select a keyboard

2. Connection status. shows the current connection status of your keyboard

3. Upload button. sends your configuration up to the cloud to compile, then programs it onto your keyboard

4. Save button. saves your configuration to your computer so you can edit it later

5. Load button. loads an existing configuration to edit and upload

6. Keys button. toggles to editing keys

7. Backlight button. toggles to editing the backlight on supported boards

8. Keyboard. this is the main area of the app, the keyboard. You'll spend the most time here

9. Layers. used to select which layer the keyboard is showing

10. Actions. used to select the action of the selected (outlined in green) key

11. Close button. closes the app

12. Help button. opens the configurator manual in your browser

13. Version number. the version of the configurator you're running


## Selecting a board

When the configurator starts, it looks a little bit like this:

![Image of configurator](http://www.machineindustries.co/uploads/guides/configurator-manual/first-boot.png "configurator board selection screen")

Notice something missing? Yup, it's the actual keyboard. To select which keyboard you want to configure, click "Click to select board" in the top left hand corner. You'll see a list of available boards, click your board to load it up.


## Configuring a key

### To be a regular key

Configuring a key to be a regular key, for example, that enters the letter "x" when you press it, is easy. Click the key you want to configure to highlight it. You'll see the actions menu appear at the bottom of the screen. Click the "Key" action and the key menu will slide up into view. Navigate around using the tab buttons at the top of the panel to find the key you want - in our case we'd click the "Alphabet" tab to find the "x" key. Hover over the keys to see a full explanation of what they do. Click the "x" key and the panel will slide away. Congrats, you just configured your first key!


### To be a board action

Board actions let you control your keyboard, you can use them to increase or decrease your backlight brightness, toggle between layers & to reset the keyboard for programming. Setting a board action is pretty much the same as a key action - select a key, click the "board" button in the actions menu, find the action you want (hover over the keys to see a full explanation of what they do) and click it to set it.

### To be a macro

Macros are super-powerful, we'll go into what they are and how to build them later, but we'll briefly touch on how to add them to a key here. Starting the same as the key and board actions, click a key on the keyboard to select it, then click the "macro" button in the actions menu. The macro panel will slide up, the same as the key and board action panels. Once you've added keys to your macro, click the "Done" button to save it to the key, otherwise click the "X" button to cancel.

### To do nothing

Sometimes you want a key to be lazy and do absolutely nothing. To do this, select the key by clicking it, then click the "None" button in the actions menu, you should see the key blanked out with no text inside it.

## Macros

### Overview

As we mentioned before, macros are super-powerful. Macros are chains of keys you want to be entered in order when you push a key on your keyboard. They can be made up of any of the keys you can usually press on your keyboard, so for exmaple, if you wanted to bind a key to press control alt delete, you could totally do that. Of you could make a key type "Hello, world! It's a great day" all in one go. Maybe even your message signature, a long hotkey combo for excel, or even usernames and passwords, however we don't reccomend it since keyboards aren't secure devices.

Keys in a macro can have one of three actions - down, up and type. Down holds the key down like keeping your finger on a key, up releases a key like lifting your finger off the key, and type pushes a key down and then releases it just like typing a key. Here's an example:

![Image of configurator](http://www.machineindustries.co/uploads/projects/configurator/macro.png "macro example")

If we read the above keys, left to right, we see a shift key with a down action, so you push down the shift key. Next, we get a H key with a type action, so we push the H key down and release it, and since the shift key is held down too, it gets capitalized. Then we get a shift key with the up action, so we release the shift key. Next up, we get E, L, L & O, all with a type action so they're all typed like regular keys and since we're not holding down the shift key, they're lowercase. And finally we see an exclamation mark with a type action, so it gets typed too.

So after that long and boring explanation, we get the string "Hello!" typed out when we press the key. It makes way more sense to just look at it and see it visually rather than explaining it or writing it in code, you can tell just with a look what the macro will do when you press it, and you can add, remove or edit keys just by clicking them. You can also re-arrange them by dragging & dropping them.

### Add a key to a macro

With the macro panel open, find the key you want to add to your macro & click it. The key should appear in the top section of the panel, just beneath "Click keys to build macro...". Add more keys in the same way, by finding and clicking them so they appear in the top section.

### Setting key up, down & type actions
Like we said before, macro keys can have on of three actions - up, down and type. Down holds the key down like keeping your finger on a key, up releases a key like lifting your finger off the key, and type pushes a key down and then releases it just like typing a key. The key action is shown with the little arrow beneath the key, down for down, up for up, and up-down for type, with the selected action shown in green.

To set the macro key action, just click the arrow matching the action you want, so the down arrow for key-down. By default, new keys added to the macro have the type (down then up) action.

### Removing a key from the macro
Removing a key from the macro is pretty simple. Hover over the key you want to remove in the macro constructor section just beneath "Click keys to build macro...". You'll see the key highlight in red and a red "X" appear inside the key. Just click it to remove it from the macro.

### Re-arranging a macro
Noticed one key out of place and want to re-order your macro? No problem, you can drag-and-drop keys from where they were to a new position in the macro easily - drag the key out of it's previous position & over to where you want it to be, an outlined box will appear where the key will end up when you drop it.

### Save the macro
Once you're done builing your macro, you need to save it, otherwise you've wasted everyone's time. To save the macro, click the "Done" button in the top left hand side of the macro panel. The panel will slide away and you'll see the word "macro" in the key you added the macro to.

### Cancel the macro
Want to cancel the macro you just built? No problem, just click the "x" button in the top right of the macro panel. The panel will slide down and the key you had selected will retain it's previous configuration.

## Layers

### Overview
Layers let you store more keys than your keyboard has space for, so your 10-key pad can effectively become a 100 key pad. To make an analogy, they're kind of like home-screens on your phone, when you unlock it, you have 10 apps on your homescreen, but swipe to the right and you have 10 more, swipe right again and you find another ten.

### Changing layers
To change layers you need to add a key with a layer-switching action. To do this, select the key you want to configure, click the "board" button in the actions menu at the bottom of the screen, then click the "layers" tab in the board action panel.

Here you'll see all the layer switching keys available to use, hover over the keys to see a full explanation of what they do & click the one you want to set the key. You can momentarily switch to a layer then switch back when you release the key, or switch to a layer and stay there - but if you want to stay on a layer, remember to add another switch so you can get back, otherwise you'll be stuck!

### Adding keys to other layers
Adding keys to other layers is pretty much the same as adding keys to the default layer. First, click the layer you want to add the key to in the layer selector towards the middle of the screen. The keyboard should change the keys shown to reflect the keys on the layer you selected, by default all layers besides the default one are blank, so don't be alarmed if you don't see any keys.

From here, you can configure keys in exactly the same way you configured keys on the default layer - click a key to select it, pick an action in the actions menu, pick a key or a macro and they key is configured.

To make sure you set the key successfully, toggle back and forth between your layer and another layer and make sure they key you configured is still there when you toggle back.

## Backlighting
### Overview
The backlight is the LED light you see behind the keys on some keyboards. On keyboards that support backlights, you can set the backlight brightness per-layer, so you'll be able to see the brightness change when you switch between layers. You can check is a board supports backlighting by looking for a 'backlight' button next to the 'keys' button just beneath the status bar at the top of the configurator.

### Setting the backlight
To set the backlight brightness for a layer, click the 'backlight' button just beneath the status bar at the top of the configurator. The text on the keyboard keys should appear greyed out and a slider should appear at the bottom of the configurator

Slide the slider to the right to turn the brightness up, or to the left to turn it down or turn it off entirely. The configurator will update as soon as you let go of the slider.

To set the backlight brightness on another layer, click the layer number in the layer bar above the slider to change to the layer you want, then follow the same process to set the brightness.



## Saving configurations for later
Pretty often, you might want to save a configuration so you can edit it later. You can do this by clicking the "save" button in the top right hand side of the screen. It'll open up a save file dialogue, enter a name for the file, then click save. The configuration fill will be saved as [name-you-entered].json on your filesystem ready for you to load up and edit in future.



## Loading saved configurations
To open a configuration you saved earlier, or a configuration created by another user you found online, just click the "load" button at the top right of the screen. A open file dialogue will pop open, find the .json file you want to load in the configurator, select it, then click open. The configurator will load the correct board and configuration from the saved file. From here, you can edit the configuration as much as you like, compile and upload it to your board, or save it again for later.



## Compiling & uploading configurations to your keyboard.
Once you're done configuring your board just the way you like it, it's time to compile your configuration and upload it to your keyboard. Sounds complicated, but don't worry, it's not.

Make sure your computer is connected to the internet and your keyboard is connected to your computer, then push the reset button on your keyboard (you'll find this underneath the board or under one of the keycaps). The connection status in the configurator should change from "disconnected" to "connected" to show your board is ready to get a new configuration, and the upload button will turn from grey to white, ready to be clicked.

When you're ready, click upload - the configurator will send your configuration securely up to the cloud to compile, then back down again to the configurator to upload it to your keyboard - during which the upload button will change from "upload" to "compiling". Once the configuration has compiled, the button will change once again to "uploading" to indicate that it's uploading the configuration to your keyboard. Once this is done, the button will change one more time to "complete", indicating the upload went okay, and after a couple of seconds the button will change back to "upload", ready to go again.

