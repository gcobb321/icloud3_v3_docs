# Configure Settings

The iCloud3 configuration screens are used to:

- Add and update Apple accounts
- Add and update tracked and monitored devices. You can assign the Apple account device and Mobile App device that provides location and other data, zone and tracking parameters, a picture or icon, etc
- Select the sensors to be updated during tracking operations
- Create HA Dashboards with iCloud3 sensors showing tracking results and battery information in several formats.
- Run special Tools to fix configuration problems
- Configure other tracking and formatting parameters
- Set up Special Zones and specify how Waze Route Tracking should be configured

## Open the Configuration screens

There are two ways to open the Configuration Screens. 

- Select the   ![](..\images\evlog-icons-config-small.png) **Configure Icon** shortcut on the *Event Log screen* 
  Then select **Configure** 
  *or*   
- Select from the HA Dashboard using **☰ > HA Settings > Devices & Services > Integrations > iCloud3** screen
  Then select **Configure**


> The Configure Icon shortcut is not available when you first install the iCloud3 integration. It will be available after the Event Log card has been setupit.

![](..\images\cf-configure.png)



The *Configure Devices & Sensors* menu is displayed when you select *Configure*. Toggle between the two menus by selecting it from the Action list at the bottom of the screen.

## Configure Devices & Sensors Menu screen

- Setup, update and log into the Apple Accounts containing the devices you want to track.
- Enable the Mobile App for monitoring location changes and zone enter.exit triggers.
- Setup and update iCloud3 tracked devices
- Select the sensors that report device and tracking results
- Enter the 6-digit verification code or request a new one to authenticate access to the Apple account
- Select how a sensor's time value and the time values in the Event Log should be displayed If you are away from home and in another time zone. You can show show the local time or the time of your HA server.
- Various utility tools for resetting configuration parameters, resetting and cleaning up bad data and other miscellaneous actions used for solving problems

## Configure Parameters Menu screen

- Setup various tracking parameters dealing with time, accuracy, distances, etc.
- Setup how data should be formatted on the sensors and Event Log
- Change the text strings should be shown on the Event log
- Setup Waze Route information and Waze Route History
- Setup sensors changes when entering non-monitored zones, stationary zones that can be used when in a non-zone location for an extended period of time and using a pseudo home zone when away from home
- Setup default inZone time intervals 


![](..\images\cf-menu-12.png)

## Selection and Parameter Update screens

Select the parameter or other screen you want to view from the screen list on the menus.

1. Select the **Screen Name** from the option list at the top of the menu screen
2. Select **Select** from the option list at the bottom part of the menu screen
3. Select **Next**

> Select the Menu screen at the bottom to toggle between the menus



The screen you selected will be displayed It generally has two parts:

- **Top Part - Item Selection or Parameter Entry** - This is used to select a task to be done, select an Apple account or Device to be updated, select an item from a list and entering and configuring parameters, etc
- **Bottom Part - Command or Action to be done** - First select the desired option (Select/Next/Add/Update/Delete/etc.), then select the command i(Submit/Next/Last) in the bottom right-hand corner. Some screens will launch other screens for additional parameters, action confirmation, menu options, etc.

These example screens show these 2-sections. 

![](..\images\cf-device-list.png)

![](..\images\cf-m1-update-device12.png)

