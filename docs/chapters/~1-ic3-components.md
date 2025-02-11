# iCloud3 Components

There are 3 major parts to the iCloud3 custom component that are used to configure, track and report device location information. They are:

- iCloud3 Custom Component 
- Event Log
- Configure Settings

This section describes each of the items.



------

### 1.1 iCloud3 Custom Component

The iCloud3 Custom Component provides the core device tracking service. It does the following:
  - Initializes and sets up all tracking activities using the device configuration data from the iCloud account.
  - Monitors the Mobile App device_tracker entity for location changes, zone enter/exit triggers and battery information.
  - Requests and processes location data from iCloud Location Services and the Mobile App.
  - Analyzes the location data and tracks the devices.
  - Updates the sensors associated with each device.

> The iCloud3 files are installed in the *config/custom_components/icloud3* directory on your HA server.


The example screens below show examples of a tracked device's current status. The following is displayed:

- Gary, on the left, is at Home. Lillian, on the Right is Away.
  - Arrive item - The icons and text show Gary is at Home (Home icon in a circle and he arrived home at @3:22p. Lillian is traveling towards home. The Home d at the Home he arrival time. Notice the distance, travel time and travel direction from the Home Zone. 
- Notice when the device was last located by iCloud or the Mobile App, when it was last updated by iCloud3 and the time of the next update. 
- Gary is tracking from Home and the Quail Zone, Lillian just from Home.
- The *Info* field shows tracking results from nearby devices is being used.


![](../images/track-gary-home-lillian-away-captions.png)



Note: The Lovelace code for these screens is in [Step #5 - Set up a Lovelace card tracking card](.../2.0-installing-and-configuring?id=step-6-set-up-a-lovelace-card-tracking-card) 

------

### 1.2 Event Log

The Event Log is a Lovelace custom card that shows past and current activity related to tracking a device. This includes:

- Startup configuration.
- Device information for Family Sharing, Find-my-Friends and Mobile App devices and entities.
- Tracking results including zone, travel time and distance data.
- Error messages, problems and location data issues.
- Detail tracking monitors that show what is going on under the covers, how location data from the iCloud Location Services and the Mobile App is analyzed and processed.

The Event Log has an *Actions* command menu that can control iCloud3 operations and the type of information to display in the Event Log or the Home Assistant log file. This includes:
- Restart iCloud3 without restarting Home Assistant
- Pause and resume tracking
- Relocate all devices
- Issue a *Find My Device* alert
- Export the Event Log to a text file
- Show/hide tracking monitors
- Start/stop detailed debugging that will dump set up information and all raw data received from iCloud Location Services.

Note: The Event Log is installed into the *config/www/icloud3* directory. This directory can be changed on the *Configure Settings > Tracking & Other Parameters* screen on Menu page #2.


![](../images/track-evlog-gary-tfz-away-lillian-home.png)



#### 1.2.1 Quick Link Icons

The icons above the *Actions* drop-down menu list in the top-right are used for various iCloud3 activities.

| Icon                                                      | Description                                                  |
| --------------------------------------------------------- | ------------------------------------------------------------ |
| ![evlog-icons-refresh](../images/evlog-icons-refresh.png) | **Refresh** - This updates the Event Log screen with new activity for the selected device. |
| ![](../images/evlog-icons-coffee.png)                     | **Buy Me a Coffee** - You find iCloud3 useful, appreciate the work I have done and want to send me a few dollars, euros, pesos, pounds, etc. Thanks. I appreciate it. |
| ![](../images/evlog-icons-issues.png)                     | **GitHub Issue** - You are having a problem and think you may have found a bug or other problem. This takes you to the iCloud3 GitHub Issues page to create a new issue or to review existing issues. |
| ![](../images/evlog-icons-config.png)                     | **Configure Settings** - This opens the iCloud3 Configure Settings screen. This will open a new browser page. It will only work when you are connected to your local network. It may not work on iPads and iPhones using the Mobile App. |
| ![](../images/evlog-icons-help.png)                       | **User Manual** - This opens the iCloud3 User Manual.        |



------

### 1.3  iCloud3 Configure Settings

*The Configure Settings* screens are used to configure iCloud3 parameters and are opened from:

- The *Configuration Icon*  on the **Event Log screen**.
- **☰ > HA Settings > Devices & Services > Integrations** screen or from the Gear icon on the Event Log screen. 

![](../images/cf-configure.png)

The *Configure Settings* consists of 2 menus and 10+ parameter entry screens. Each screen has two parts:

- **Selection or parameter entry (top part)** - This is used to select a task to be done, an item to be selected or an option list/text field for the parameter being configured.
- **Command or Action to be done (bottom part)** - First select the desired option (Select/Next/Add/Update/Delete/etc.), then select the command in the bottom right-hand corner of the screen (Next/Submit/Finish/etc.).

The example screens below show these 2-sections. These and the other screens are described in detail in the *Configuring iCloud3 Parameters* chapter.



#### 1.3.1 Update Configuration Main Menu screens

The menus are used to select the specific update screen.

![](../images/cf-menu-1-2-sbs.png)



#### 1.3.2 Update Tracked Device screens

Adding a new devices and updating an existing device is done on this screen.
![](../images/cf-device-update.png)



#### 1.3.3 Format Settings screen

Configuring how information should be displayed in the device_tracker and sensor entities and on the Event Log screen. 
![](../images/cf-format-settings.png)

