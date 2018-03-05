# configurator

## What does it do?

The configurator is, like it's name suggests, an app for configuring keyboards, without all that messing around with firmware code. It's cross-platform, relatively lightweight, and it's built on top of the QMK firmware, which is pretty well established and tested, so the firmwares it generates are rock-solid.

The information in this readme is taken from: http://www.machineindustries.co/guides/configurator-manual

[Installing](https://github.com/CountParadox/configurator/blob/master/README.md#installing)

- [For macOS & Linux](https://github.com/CountParadox/configurator/blob/master/README.md#for-macos--linux)
- [For Windows](https://github.com/CountParadox/configurator/blob/master/README.md#for-windows)

[Overview](https://github.com/CountParadox/configurator/blob/master/README.md#overview)

Selecting a board

Configuring a key

- To be a regular key
- To be a board action
- To be a macro
- To do nothing

Macros

- Overview
- Add a key to a macro
- Setting key up, down & type actions
- Removing a key from the macro
- Re-arranging a macro
- Saving the macro
- Cancel the macro

Layers

- Overview
- Changing layers
- Adding keys to other layers

Backlighting

- Overview
- Setting the backlight

Saving configurations for later

Loading saved configurations

Compiling & uploading configurations

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
