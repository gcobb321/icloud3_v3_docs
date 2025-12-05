# iCloud3 v3 Device Tracker Custom Component

[![CurrentVersion](https://img.shields.io/badge/Current_Version-v3.2-blue.svg)](https://github.com/gcobb321/icloud3_v3)  [![Type](https://img.shields.io/badge/Type-Custom_Component-orange.svg)](https://github.com/gcobb321/icloud3_v3)  [![HACS](https://img.shields.io/badge/HACS-Custom_Repository-orange.svg)](https://github.com/gcobb321/icloud3_v3)

[![ProjectStage](https://img.shields.io/badge/Project_Stage-General_Availability-forestgreen.svg)](https://github/gcobb321/icloud3_v3)  [![Released](https://img.shields.io/badge/Released-May,_2025-forestgreen.svg)](https://github.com/gcobb321/icloud3_v3)

-----

iCloud3 is a device tracker custom component that tracks your iPhones, iPads and Apple Watches. Devices in the Family Sharing List and the HA Mobile App Integration are trackable. The device requests location data from from Apple's iCloud  Location Services and monitors various Mobile App sensors and triggers to determine the device's  battery level, location, distance, travel time and arrival to Home. 

### iCloud3 Components

There are 4 major parts to the iCloud3 custom component that are used to configure, track and report device location information. They are:

- **iCloud3 Device Tracker** - This monitors the device's location, determines when the device should be located next and updates all the sensors.
- **Event Log** - Shows a devices location, how the location changes are handled, the results of location updates, errors, and startup information.
- **Configure Settings** - Set up all the iCloud3 tracked devices, Apple Accounts, iCloud3 Dashboards, sensors and other parameters.
- **Dashboard Builder** - Create iCloud3 dashboards with tracking results, battery information and the Event Log in several formats. The dashboards can then be customized with the Home Assistant Dashboard Editor and the various items and views can be copied and pasted into other dashboards. The Dashboard Builder is one of the *Configure Settings* screens. 

### iCloud3 v3 Highlights

Although Home Assistant has it's own official iCloud component, iCloud3 goes far beyond it's capabilities. The following highlights the important features.

#### General

- **HA Integration** - iCloud3 is a Home Assistant custom integration that is set up and configured from the *HA Settings > Devices & Services > Integrations* screen.
- **Configuration Settings** - Configuration parameters are updated online using various screens and take effect immediately without restarting HA.
- **Updating and Restarting** - iCloud3 can be restarted without restarting Home Assistant.
- **Restore state values on restart** - The current device_tracker and sensor entity states are restored on a restart. The attributes are not restored but are reset on the first tracking Event. 
- **Device_tracker and sensor entities** - iCloud3 devices and sensors are Home Assistant entities that are added, deleted and changed on the  *Update iCloud3 Devices* and *Sensors* configuration screens.
- **Dashboard Builder** - iCloud3 Dashboards in various formats are added to Home Assistant when the iCloud3 Integration is first installed.

#### Device Tracking

- **Track iPhones, iPads and Apple Watches** - Track or monitor your iDevices. 
- **Location data sources** - Location data comes from the iCloud Account and the HA Mobile App.
- **Multiple Apple Accounts** - Devices from several Apple Accounts can be tracked (yours, your spouse, children, friend, relative, etc.)
- **Monitors Mobile App activity** - Looks for location and trigger changes every 5-seconds. 
- **Improved GPS accuracy** - GPS wandering errors leading to incorrect zone exits are eliminated.
- **Actively track a device** - The device will request it's location on a regular interval based on its distance from Home or another zone. 
- **Passively monitor a device** - The device does not request it's location. It is updated when another tracked device requests theirs.

#### Special Zone Tracking

- **Stationary Zone** - A dynamic *Stationary Zone* is created when the device has not moved for a while (doctors office, store, friend's house). This helps conserve battery life.
- **Zone monitoring** - The number of devices in each zone is displayed when a device is updated. 
- **Zone Distance Sensor Attributes** - Shows the distance to the center and edge of the Home zone, distance to other zones and distance to other devices. 

- **Track from multiple zones** - Tracking results (location, travel time, distance, arrival time, etc.) are reported from the Home zone or another zone (office, second home, parents, etc.). 
- **Enter Zone delay** - Delay processing Zone Enter triggers in case you are just driving through it.
- **Zone Exits for devices not using the Mobile App** - Devices that do not or can not (Apple Watch) use the Mobile App respond to a zone exit when it detects another nearby device has left a zone.
- **Primary Home Zone** - Set another zone as the primary zone for the device and report tracking results based on that location. This is useful when you have two homes, on a vacation at another location, triggering automations at your parents house with true devices, etc.

#### Advanced Features

- **Battery status** - Updates the battery level and status (charging/not charging) from iCloud data during a tracking event and from the Mobile App every 5-seconds.
- **Waze Route Service** - The travel time and distance to Home or another tracked zone is provided by Waze.
- **Waze Route Service History Database** - The travel time and distance data from Waze is saved to a local database and reused when the device is in a previous location. 
- **Zone Activity Log** - A log can be kept for each time you are in a zone. This log file (.csv format) can be imported into a spreadsheet program and used for expense reporting, travel history, device location monitoring, etc. 
- **Nearby devices** - The distance to other devices is displayed and used to determine tracking results.
- **Local Time Zone** - Event times are normally displayed using the time zone your HA server is in. If, however, you are away from home and in another time zone can, the Event times can be displayed for the time zone you are in.
- **Sensors and more sensors** - Many sensors are created and updated with distance, travel time, polling data, battery status, zone attributes, etc. Select only the ones you want to use. 

#### And ...

- **Event Log** - The current status and event history of every tracked and monitored device is displayed on the iCloud3 Event Log custom Lovelace card. Information about device configuration, errors and alerts, nearby devices, tracking results, debug information and location request results is displayed.
- **Extensive Documentation** - The iCloud3 User Guide explains the three main components, hot to get started, how to migrate from v2, how to install the integration, each of the screens and special features, the service calls that can request updates, locate iPhones and send notification alerts, examples of how to automate opening your garage door when you arrive home, etc.
- **And More** - Review the following documentation to see if it will help you track and monitor the locations of your iPhones, iPads and Apple Watches.

### Tracking Information Screens with Event Log

The screens below are an example of how the many tracking sensors can be displayed. The screen on the left shows the current tracking formation for Gary while the Event Log on the right shows a history of important tracking events.

![](https://gcobb321.github.io/icloud3_v3_docs/images/dashboard-allinfo-summary.png)



## iCloud3 Documentation

- Introduces the many features and components of iCloud3
- Provides step-by-step instructions to install and configure iCloud3, it's components and it's supporting components (iCloud Account and the Mobile App)
- Highlights the configuration screens and parameters
- Provides example screens, automations and scripts

  

## Installing iCloud3

iCloud3 can be installed two ways:

- Using HACS
- Downloading the *icloud3.zip* file from the *iCloud3 GitHub Repository Releases Page* [here](https://github.com/gcobb321/icloud3/releases). 

The procedures for both methods are described in the *Installing and Configuring iCloud3* chapter [here](chapters/2-installing-and-configuring.md).



## iCloud3 Components

There are 4 major parts to the iCloud3 custom component that are used to configure, track and report device location information. They are:

- **iCloud3 Device Tracker** - This monitors the device's location, determines when the device should be located next and updates all the sensors
- **Event Log** - Shows a devices location, how the location changes, the results of location updates, errors, and startup information
- **Configure Settings** - Set up all the iCloud3 tracked devices, Apple Accounts, sensors and other parameters
- **Dashboard Builder** - Create iCloud3 dashboards with tracking results, battery information and the Event Log in several formats. The dashboards can then be customized with the Home Assistant Dashboard Editor and the various items and views can be copied and pasted into other dashboards. The Dashboard Builder is one of the *Configure Settings* screens. 



### iCloud3 Device Tracker

The iCloud3 Custom Component provides the core device tracking service. It does the following:

  - Initializes and sets up all tracking activities for the Devices using location data from iCloud Location Services or the Mobile App device_tracker entity (or both).
  - Monitors the Mobile App device_tracker entity for location changes, zone enter/exit triggers and battery information.
  - Requests and processes location data from iCloud Location Services and the Mobile App.
  - Analyzes the location data and tracks the devices.
  - Updates the sensors associated with each device.


The screens below show examples of a tracked device's current status. The following is displayed:

- Gary, on the left, is at Home. Lillian, on the Right is Away.
  - Arrive item - The icons and text show Gary is at Home (Home icon in a circle and he arrived home at @3:22p. Lillian is traveling towards home. Notice the distance, travel time and travel direction from the Home Zone. 
- Notice when the device was last located by iCloud or the Mobile App, when it was last updated by iCloud3 and the time of the next update. 
- Gary is tracking from Home and the Quail Zone, Lillian just from Home.
- The *Info* field shows tracking results from nearby devices is being used.

![](../images/track-gary-home-lillian-away-captions.png)



### Event Log

The Event Log is a Lovelace custom card that shows past and current activity related to tracking a device. The right side of the *Information screen showing Tracking Information* above is the *Event Log*. The *Event Log* shows:

- Startup configuration.
- Device information for Apple account and Mobile App devices and entities
- Tracking results including zone, travel time and distance data
- Error messages, problems and location data issues
- Detail tracking monitors that show what is going on under the covers, how location data from the iCloud Location Services and the Mobile App is analyzed and processed



### Configure Settings

The iCloud3 configuration screens are used to:

- Add and update Apple accounts
- Add and update tracked and monitored devices. You can assign the Apple account device and Mobile App device that provides location and other data, zone and tracking parameters, a picture or icon, etc
- Select the sensors to be updated during tracking operations
- Create HA Dashboards with iCloud3 sensors showing tracking results and battery information in several formats.
- Run special Tools to fix configuration problems
- Configure other tracking and formatting parameters
- Set up Special Zones and specify how Waze Route Tracking should be configured



### Dashboard Builder

The Dashboard Builder is a tool that will create and update dashboards showing iCloud3 tracking results and other device information provided by iCloud3. It is added to the HA Sidebar panel when it is created and can be edited using the HA Dashboard Editor in the same manner as other dashboards. It's name starts with *iCloud3-#* and can be changed to meet your needs. There is no limit to the number of iCloud3 dashboards that can be created.

!> When the iCloud3 Integration is install the first time, the *iCloud3* is created and added to the HA Sidebar panel.

!> When new devices are added on the *Update iCloud3 Devices* screen, they are added to all iCloud3 dashboards *All Info, *Track Results and *Badge, Battery view tabs.*

Each dashboard has six view tabs. The *Main* and *Other Devices* view tabs are built for the selected devices when the dashboard is created. The other view tabs (their name starts with a '*') are recreated for all devices whenever a dashboard is updated. The type of elements that are created are:

- All tracking information (tracking results sensors + tracking status sensors  + device information sensors) as one item
- All tracking information (tracking results sensors, tracking status sensors, device information sensors) as separate items
- Device Badge sensors and Battery sensor as one item in several formats
- Device Battery sensors in several formats
