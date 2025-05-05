# iCloud3 Device Tracker

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

