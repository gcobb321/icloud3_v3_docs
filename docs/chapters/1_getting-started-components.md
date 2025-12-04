

# iCloud3 Components

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

![](C:\Users\Gary\GitHub\icloud3_v3_docs\docs\images\track-gary-home-lillian-away-captions.png)



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