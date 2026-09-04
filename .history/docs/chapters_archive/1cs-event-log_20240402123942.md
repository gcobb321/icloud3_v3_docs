## Event Log  <!-- {docsify-ignore} -->

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


------
### Quick Link Icons

The icons above the *Actions* drop-down menu list in the top-right are used for various iCloud3 activities.

| Icon                                                      | Description                                                  |
| --------------------------------------------------------- | ------------------------------------------------------------ |
| ![evlog-icons-refresh](../images/evlog-icons-refresh.png) | **Refresh** - This updates the Event Log screen with new activity for the selected device. |
| ![](../images/evlog-icons-coffee.png)                     | **Buy Me a Coffee** - You find iCloud3 useful, appreciate the work I have done and want to send me a few dollars, euros, pesos, pounds, etc. Thanks. I appreciate it. |
| ![](../images/evlog-icons-issues.png)                     | **GitHub Issue** - You are having a problem and think you may have found a bug or other problem. This takes you to the iCloud3 GitHub Issues page to create a new issue or to review existing issues. |
| ![](../images/evlog-icons-config.png)                     | **Configure Settings** - This opens the iCloud3 Configure Settings screen. This will open a new browser page. It will only work when you are connected to your local network. It may not work on iPads and iPhones using the Mobile App. |
| ![](../images/evlog-icons-help.png)                       | **User Manual** - This opens the iCloud3 User Manual.        |





------

### Actions

The **Actions** drop-down menu is used to issue commands to:

- Control iCloud3 operations

- Locate devices

- Change the debug Log Level

- Start Waze History maintenance operations

  ![](../images/evlog-actions.png)

| Command                                        | What Happens                                                 |
| ---------------------------------------------- | ------------------------------------------------------------ |
| **Global Actions**                             |                                                              |
| Restart iCloud3                                | The configuration file is loaded, iCloud3 is reinitialized, all zones, devices and tracking is reset, iCloud3 restarts, all devices are relocated and tracking begins again |
| Pause All Tracking                             | Tracking is paused for all devices                           |
| Resume All Tracking                            | Tracking is resumed for all devices                          |
| Locate All Devices (FamShr)                    | A location request is sent to iCloud FamShr, iCloud locates the devices. The new locations are processed and the tracking/location results are determined |
| Send Location Request to the Mobile App        | A location request is sent to the Mobile App for all devices that are using the Mobile App. If the Mobile App is alive, it should respond with the current location. The new locations are processed and the tracking/location results are determined |
| **Selected Device**                            |                                                              |
| Pause Tracking This Device                     | Tracking is paused for the selected devices                  |
| Resume Tracking This Device                    | Tracking is resumed for the selected  devices                |
| Locate This Device (FamShr)                    | A location request is sent to iCloud and the tracking/location results are updated for the selected |
| Send Location Request to the Mobile App        | A location request is sent to the Mobile App for the selected device if it is using the Mobile App. If the Mobile App is alive, it should respond with the current location and the tracking/location results are updated |
| Send Find My Phone Alert (FamShr)              | Send a Find My Phone Alert request to the selected device. This will play the alert tone on the device. |
| **Other Commands**                             |                                                              |
| Export Event Log                               | The Event Log is exported to a file in the HA _config_ directory. The file name is _icloud3-event-log-[date-time].log_ |
| Show Tracking Monitors, Hide Tracking Monitors | Show (or Hide) additional information about starting iCloud3 and processing tracking events using FamShr and Mobile App location data. |
| Show Startup Log, Errors & Alerts              | Many event messages are written to the Event Log when iCloud3 starts. This command will redisplay these messages. Select the Refresh Icon or a Devicename to return to normal operations. |
| Start/Stop Debug Logging                       | Start/Stop adding additional debug items to the _iCloud3-0.log_ file |
| Start/Stop RawData Logging                     | Start/Stop Debug Logging plus display the actual device and location data as it is received from iCloud or the Mobile App |
| WazeHist-Recalculate Route Time/Dist           | The Waze Time and Distance information is saved to the Waze History Database for local handling of Waze route requests. This eliminates delays that can occur responding to route requests in poor cell phone areas with poor internet response times. This command will send a request to Waze to update the time and distance for all locations in the database. It is processed in the background at midnight on your HA server. Select it a second time to start the update immediately. |
| WazeHist-Load Track Locations for Map          | The locations in the Waze History database can be displayed on an HA Map. This command will load those locations into the _sensor.icloud3_wazehist_track_ entity, the data source for the map. See  _Reference > Other iCloud3 Features > Display the Waze History Location on a Map Card_ for more information. |
| Request Apple ID Verification Code             | Request a new 6-digit verificatoin code from Apple. This is the same as requesting a new code on the _Configure Settings > Enter/Request an Apple  ID Verification Code_ screen. |



------
### Creating the Event Log screen

The Event Log shows the status of iCloud3 operations. It displays a lot of information on how iCloud3 starts and on provides the tracking events for all of the devices being tracked and monitored. For this custom card to be displayed, it needs to be added to the Lovelace Resources. 

![](../images/lovelace-evlog-gary-away.png)

The Event Log is a custom card and HA looks for it in the /www directory. 

- When iCloud3 was installed, the *icloud3-event-log-card.js* file was copied from the *icloud3/event_log_card* directory to the */www/icloud3* directory (or another custom_card directory you might have set up for iCloud3 v2).

-  When iCloud3 starts, it does the following:
  - Determine if the Event Log in the */www/icloud3* directory is the latest version. If not, it is updated. A browser refresh will be needed it it was updated. A notification is displayed on each device that a refresh is needed. 

    Note: The notification will not be displayed when it is first installed, it is only displayed on an update.

  - Determine if the Lovelace Resource list contains the Event Log and if the directory is correct. It will be added or updated if that is needed.



#### Add the Event Log to an existing dashboard layout

The following yaml will create the Event Log custom card on the dashboard card you added at another time all of the other statements.


- **GUI Entry Method**
  
  1. Display the dashboard you want to add the card to. 
  2. Select the **Edit Pencil** in the upper right corner, then select **+ Add Card** at the bottom.
  3. Scroll to the bottom of the Card Type Selection screen and select **Manual**. A screen with ```type: ''``` is displayed.
  4. Paste  ```custom:icloud3-event-log-card```  between the quote marks. Delete the blank line #2 so the error/warning message will go away. It should now read:
  
  	     type: 'custom:icloud3-event-log-card'
  
  5. Select **Save** to save your changes.
  
     
  
- **Manual Entry Method**

  1. Display the dashboard you want to add the card to. 
  2. Select the **Edit Pencil** in the upper right corner. Then select the **three-dots** and then **Raw Configuration Editor**. 
  3. Scroll to the bottom or the location where you want to create the Event Log card. Insert the code below at that location. YAML is very unforgiving and you have to pay attention to spaces and indents.
  
      ```
              - type: grid
                square: false
                columns: 1
                cards:
                  - type: 'custom:icloud3-event-log-card'
      ```
  



#### Create a new dashboard card for the Event Log

The following yaml will create the Event Log custom card on the dashboard card you added at another time all of the other statements.

- **GUI Entry Method**
  
   1. Display the dashboard you want to add the card to or create a new one.
   2. Select **+ (Plus Sign)** on the top line to add the new dashboard. The *View Configuration* screen is displayed.
   3. Enter the dashboard title (**iCloud3 Event Log**) and select **Save**.
   4. Select **+ Add Card** at the bottom and follow steps 3, 4 and 5 in the GUI Entry Method above.
   
- **Manual Entry Method**
   1. Follow steps 1, 2 and 3 above.
   
   2. Select the **Edit Pencil** in the upper right corner. Then select the **three-dots** and then **Raw Configuration Editor**. 
   
   3. Scroll to the bottom or the location where you want to create the Event Log card. Insert the code below at that location. YAML is very unforgiving and you have to pay attention to spaces and indents.
   
      ```
      title: iCloud3 Event Log
      columns: 1
      square: false
      type: grid
      cards:
        - type: 'custom:icloud3-event-log-card'
      ```
   
   

Hopefully, the Event Log displayed correctly. If it did not display and *Custom element doesn't exist icloud3-event-log-card* error message displayed instead, the Event Log needs to be added to the Lovelace Resources.



------
### Lovelace Resource for the Event Log

The Lovelace Resources points to the location of the *icloud3-event-log-card.js* file and must be set up for the Event Log to be displayed.  If a problem occurs setting up the Lovelace Resource automatically, the Event Log (on the right in the above screenshot) will not be displayed and the following will be displayed instead:

![](../images/lovelace-evlog-resource-error.png)

Do the following to set it up manually:

1. Select **☰ > HA Settings > Dashboards > ⋮ (Upper right corner) > Resources**. The following screen is displayed:

   ![](../images/lovelace-resources-list.png)

2. Select **+ Add Resource** to open the Add Resources window (on the left).

![](../images/lovelace-resources-add.png)

3. Enter the following:

   - `/local/icloud3/icloud3-event-log-card.js` in the **URL** field. 
   - DO NOT ENTER `/www/icloud3/icloud3-event-log-card.js` . It will not work.
   - Check **JavaScript Module**
4. Select **Create (or Update)**

#### Using another custom card directory
If you move the Event Log card to another directory, the Lovelace Resources should automatically be changed. If something happens and it is not changed, change the directory (*icloud3*) in the URL statement on the above screen to the new directory name. Then select the new directory name in the *Event Log Directory* field on the *iCloud3 Configure Settings > Menu Page 2 > Other Parameters*  screen.



------
### Event Log During Startup

When iCloud3 starts,  a number of events take place where it sets up the configuration, zones, support structure, devices and sensors. The results of this process are shown in the Event Log. The information in these startup stages can help identify errors with tracked devices, parameters and actual device data in the Apple iCloud account and associated with the Mobile App.

Below are examples of each stage.

------
#### Stage 1 - Initial Preparation

During the *Initial Preparation* stage:

- The iCloud3 directory is identified.
- The version of the Event Log is checked to verify the latest version is being used. It will be updated and a message is sent to all devices if necessary.
- The Apple iCloud account login process is started if the username/password is available. If not available, the login process will be done later.

![](../images/evlog-stage-1.png)


------
#### Stage 2 - Prepare Support Services

During the *Prepare Support Services* stage:

- The Waze Route Service is setup.
- The Waze History data base is checked and prepared.
- The Stationary Zone location is prepared.
- The Home Assistant zones are imported and set up.

![](../images/evlog-stage-2.png)


------
#### Stage 3 - Prepare Configured Devices

During the *Prepare Configured Devices* stage:

- The tracked device parameters are read from the configuration file.
- Each tracked and monitored device is set up.

![](../images/evlog-stage-3.png)


------
#### Stage 4 - Setup iCloud & Mobile App Tracking Methods

During the *Setup iCloud & Mobile APP Tracking Methods* stage:

- The devices in the Family Sharing list and the Find-my-Friends list in the Apple iCloud account are identified.
- The devices in the HA device and entity registries are read and identified.
- The iCloud3 devices are linked to those in the Family Sharing list, the Find-my-Friends list and the Mobile App device list.
- The devices in each of these lists that are not associated with an iCloud3 device are identified.

!> The final verification of each device is done during this stage. Configuration errors due to a change in device names, device_tracker entity name errors and unavailable devices are reported.

![](../images/evlog-stage-4.png)


------
#### Stage 5 - Configure Tracked Devices

The *Configure Tracked Devices* stage:

- Finalizes the configuration of the tracked devices.
- Links the *Battery Sensor*, *Notifications* and *Stationary Zones* to each tracked device

![](../images/evlog-stage-5.png)
