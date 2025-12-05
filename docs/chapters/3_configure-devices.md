 iCloud3 Devices screen

Up to 10-devices can be tracked by iCloud3. They are shown on this screen.  Since no devices have been set up, the list is empty and *Add Device* is selected.

1. Select **Add Device**, then select **Next** to display the *Add Device* screen

![](..\images\cf-device-list-empty.png)



#### Step #3.3 - Add Tracked iCloud3 Device screen

New iCloud3 tracked devices are added on this screen.

1. Assign a  **iCloud3 Device Name** to the device (*gary_iphone*). This will create the HA *device-tracker.[devicename]* entity and the HA *sensor.[devicename]_[sensorname]* entities for this device.

![](..\images\cf-device-add-empty.png)

2. Type the **Friendly Name** (*Gary*) and change the **Device Type** if necessary.

![](..\images\cf-device-add-gary.png)

3. Select **Next** to display the *Update Tracked iCloud3 Device* screen to enter the rest of the parameters.

*Notes*:

1. The *Tracking Mode* field describes how the device will be tracked: 
   - **Track** - Request the location and track the device,
   - **Monitor** - Do not request the location. Report it's location when it is requrned from an iCloud location request for another device.
   - **Inactive** - Not tracked or monitored. This option keeps the device's parameters in the the configuration file but does not track it. 



#### Step #3.4 - Update Tracked iCloud3 Device screen

This screen specifies various parameters used by iCloud3 to track the device. The major parameters are:

1. The Family Sharing List and the Find-my-Friends device from your iCloud account that is associated with this iCloud3 device.
2. The iOS App device tracker entity tha will be monitored for location changes, zone enter/exit triggers and battery information.
3. The picture to be displayed on the *device_tracker.[devicename]* entity and the *sensor.[devicename]_badge* entity.

![](..\images\cf-device-update.png)

1. Select and enter the parameters for this device.
2. Select **Submit** to add the device. It will be added to the *iCloud3 Device Tracker Entities* screenn.

![](..\images\cf-device-list-gary-added.png)

!> At this time, it is advisable to only set up the main device associated with the Apple iCloud account. This will make sure iCloud3 is up and running, the device_tracker and sensor entities are being created, the Lovelace sensor screens are showing the correct information, the Event Log is operational before continuing and you have become familiar with the *Configure Settings* screens and iCloud3.

!> Apple discontinued the Find-my-Friends (FmF) data source in May, 2023. References to FmF have not been removed from iCloud3 or this User Guide with hopes that a new solution will be found to provide this service at a later time. 