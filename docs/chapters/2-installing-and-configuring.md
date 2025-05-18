# Installing and Configuring iCloud3

There are several steps that that need to be done to install and start using iCloud3 to track your devices. They are:

1. Install iCloud3 from HACS (or manually).
2. Install and configure the HA Mobile App if you are using it on any of your tracked devices. 
3. Set up the Lovelace Resource entry for the Event Log custom card component.
4. Add the iCloud3 integrations component which adds iCloud3 and it's *Configure Settings* screens. 
5. Open the *Configure Settings > Menu Page 1* screen. 
6. Open the *iCloud Account & Mobile App* screen and set up your Apple iCloud account.
7. Log into your iCloud account and enter the 6-digit verification code. 
8. Open the *iCloud3 Tracked Devices* and add your iPhone to the tracked device list. 
9. Set up a Lovelace card for for your iPhone.
10. Set up a Lovelace card for the Event Log. 
11. Restart Home Assistant.

These steps are described below.


------
### Step 1 - Install iCloud3

iCloud3 is not available on the HACS base integration yet. It will be added as an update to iCloud3 v2 once it has been released for general usage and has a sufficient number of users to insure a smooth transition. There are almost 7000 users now and  supporting a large number of people that might upgrade it at the same time is not feasible.

However, it can be added to HACS as a custom repository. This provides all the benefits of HACS and ensures a smooth rollout.

- **Using HACS to install iCloud3**
  1. Open HACS.
  2. Select **Integrations** and type **icloud3** in the search bar.
  3. Select the **iCloud3 v3, iDevice Tracker** item, then select **+Download** to download iCloud3 and follow the normal steps for installing an integration using HACS.
  
- **Manual Installation from the iCloud3 Repository Releases Page**
  1. Download the *icloud3.zip* file from the *gcobb321/icloud3 iCloud3 GitHub Repository Releases* page [here](https://github.com/gcobb321/icloud3/releases). Selects *Assets* at the bottom, then the zip file. The file save screen is displayed, select the location on your computer and save the zip file.
  2. Unzip the file into the *config/custom_components/icloud3* directory on your Home Assistant server (ex.: Raspberry Pi)
  3. **Restart Home Assistant**



------
### iCloud3 v3 Development Version (HACS Custom Installation)

New features are added to iCloud3 Development Version before they are released to the General Availability version on HACS. This Beta version can be added to HACS as a Custom Repository. Follow the instructions below:

- **Adding the iCloud3 Development Edition to HACS**

  1. Open HACS
  2. Select the 3-dots in the upper-right corner, then select *Custom Repository*.
  3. Enter the following values in the fields displayed:
     - Repository: `gcobb321/icloud3_v3`
     - Category: `Integration`
  4. Select **Add**

   ![](../images/hacs-process-highlighted.png)

  *Notes*:
  1. Additional information in the HACS User Guide can be found [here](https://www.hacs.xyz/docs/faq/custom_repositories/?h=reposit).
  2. Monitor the gcobb321/icloud3_v3 Issues page for an announcement that a new release is available.
  3. Download the *icloud3.zip* file from the *gcobb321/icloud3_v3 iCloud3 GitHub Repository Releases* page [here](https://github.com/gcobb321/icloud3_v3/releases). Follow the Manual instructions above. 
  
     


------
### Step 2 - Install the Mobile App on your iPhone or iPad

The Mobile App is not required for iCloud3 to track devices. But it helps and it's benefits have already been discussed. It can be installed on some of your iDevices and not others. You can, for example, install it on your iPhone and not your wife's. 

The official documentation for the Mobile App (Home Assistant Mobile) can be found [here](https://Mobile.home-assistant.io/).  Select *Getting Started* for instructions on installing and configuring the Mobile App.

The Mobile App must be configured to provide location and zone activity to Home Assistant. The screen below shows the correct settings:

![](../images/mobapp-config.png)


------
### Step 3 - Add the iCloud3 Integration and open *Configure Settings*

iCloud3 is a Home Assistant Integration and is configured on the Integrations screens like all the other Integrations you may be using.

1. Select **☰ > HA Settings > Devices & Services > Integrations**.
2. Select **+ Add Integration** in the lower-right hand corner.
3. Type **iCloud3**. Then select **iCloud3 v3** from the list of Integrations. *Do not select iCloud3, it is v2.4 if it is displayed.* The iCloud3 v3 entry will be added to the *Integrations* screen.
4. Open the *Configure Settings* screen.
   - Event Log has not been set - Select **☰ > HA  Settings > Devices & Services > Integrations**.
   - Event Log has been set up - Select the **Configure iCloud3 Settings** icon (gear) on the **Event Log**.
5. Select **iCloud3 > Configure**.



![](../images/cf-configure.png)



​	The *iCloud3 Configure Settings* Menu Page 1 on the left is displayed.

![](../images/cf-menu-12.png)

There are 10-parameter screens on 2-menu pages that are used to display and update the parameters. The name of the screens are displayed at the top, the Action to be performed is displayed at the bottom. All update screens follow this same format.

Only two of the parameter screens are needed to be set up for iCloud3 to start tracking devices. The default values on the other screens will be fine for now. You will want to review them and tailor the parameters for your needs later.

1. *iCloud Account & Mobile App* screen - Add the username and password settings for your Apple iCloud account.
2. *iCloud3 Devices* screen - Add, update and delete devices that will be tracked by iCloud3. 



#### Step 3.1 - iCloud Account & Mobile App screen

This screen is used to indicate the data sources used for location information (iCloud, Mobile App) and the username/password of your Apple iCloud account.

1. Select the **Password Display Icon** at the end of the username and password fields to display their values. Correct them if necessary. 
2. Select **Login**, then select **Submit**.  The iCloud account will be logged into and the lists of iPhones, iPads and other devices associated with the account will be set up. 
3. Select **Save**, then select **Submit** to return to the menu.

![](../images/cf-data-sources.png)

*Notes*:
1. When iCloud3 starts, you are logged into your Apple iCloud account. The account username/password is shown on the *LOGIN Action* line (gc......@gm......./Gc......).
2. The password is encrypted when it is saved in the configuration file.
3. The username and password are not required if you are only tracking with the Mobile App,
4. Apple account authentication - If you are signing into the Apple iCloud Account for the first time, the account access token has expired or your account username or password has changed and you will get an alert on your phone or other device that someone is signing into your Apple account. 
   1. Select **Allow** on your phone or other trusted device, the screen showing the 6-digit verification code is displayed
   2. The code entry form below should display on your computer. If it does not, select *Enter Verification Code*, then select Submit. When iCloud3 starts, you are logged into your Apple iCloud account. The account username/password is shown on the *LOGIN Action* line (gc......@gm......./Gc......).
   3. From time-to-time, you will have to reauthenticate iCloud3's access to your Apple iCloud account. This is discussed later. 
   4. Enter the 6-digit verification code, then select *Submit*.

![](../images/auth-process-3-code-entry.png)



#### Step 3.2 - iCloud3 Devices screen

Up to 10-devices can be tracked by iCloud3. They are shown on this screen.  Since no devices have been set up, the list is empty and *Add Device* is selected.

1. Select **Add Device**, then select **Next** to display the *Add Device* screen

![](../images/cf-device-list-empty.png)



#### Step 3.3 - Add Tracked iCloud3 Device screen

New iCloud3 tracked devices are added on this screen.

1. Assign a  **iCloud3 Device Name** to the device (*gary_iphone*). This will create the HA *device-tracker.[devicename]* entity and the HA *sensor.[devicename]_[sensorname]* entities for this device.

2. Type the **Friendly Name** (*Gary*) and change the **Device Type** if necessary.

![](../images/cf-device-add.png)

3. Select **Next** to display the *Update Tracked iCloud3 Device* screen to enter the rest of the parameters.

*Notes*:
1. The *Tracking Mode* field describes how the device will be tracked: 
   - **Track** - Request the location and track the device,
   - **Monitor** - Do not request the location. Report it's location when it is requrned from an iCloud location request for another device.
   - **Inactive** - Not tracked or monitored. This option keeps the device's parameters in the the configuration file but does not track it. 



#### Step 3.4 - Update Tracked iCloud3 Device screen

This screen specifies various parameters used by iCloud3 to track the device. The major parameters are:

1. The Family Sharing List and the Find-my-Friends device from your iCloud account that is associated with this iCloud3 device.
2. The Mobile App device tracker entity tha will be monitored for location changes, zone enter/exit triggers and battery information.
3. The picture to be displayed on the *device_tracker.[devicename]* entity and the *sensor.[devicename]_badge* entity.

![](../images/cf-device-update.png)

1. Select and enter the parameters for this device.
2. Select **Submit** to add the device. It will be added to the *iCloud3 Device Tracker Entities* screenn.

![](../images/cf-device-list-gary-added.png)

!> At this time, it is advisable to only set up the main device associated with the Apple iCloud account. This will make sure iCloud3 is up and running, the device_tracker and sensor entities are being created, the Lovelace sensor screens are showing the correct information, the Event Log is operational before continuing and you have become familiar with the *Configure Settings* screens and iCloud3.

!> Apple discontinued the Find-my-Friends (FmF) data source in May, 2023. References to FmF have not been removed from iCloud3 or this User Guide with hopes that a new solution will be found to provide this service at a later time. 

-----

### Step 4 - Exit the *Configure Settings* screens

Since a tracked device was updated, iCloud3 will restart when you exit the *Configure Settings*.

1. Display the **Main Menu** screen. Select **Save**, or **Cancel**, or **Return** depending on the screen that is displayed and select **Submit**..
2. Select **Exit and Restart** on the Menu screen, then select **Next** to display the *Confirm Restarting iCloud3* screen. 

![](../images/cf-confirm-ic3-restart.png)

3. Select **Restart Now**, then select **Next**.
4. Select **Finish** on the final *Success, Options Successfully Saved* screen.
5. Redisplay the Lovelace screen showing iCloud3 device information you have been using and/or the Event Log.

iCloud3 will restart, the device_tracker and sensor entities are created, the devices will be located and tracking will begin.



#### The Other Configuration Screens  {docsify-ignore}

Review the other screens just to see what is configurable. Nothing has to be done right now to get you up and running. The default values will work fine. The other screens are shown and described in *Configuring iCloud3 using the Configure Settings Screens* in the next chapter



------
### Step 5 - Review the iCloud3 Dashboard

When the iCloud3 Integration is added the first time, the iCloud3 Dashboard is created and added to the HA Sidebar Manu. The dashboard contains several View Tabs. The *Main* View Tab shows the tracking results and battery information, the *Other Devices* View Tab shows the tracking results, tracking status and device information sensors. Other View Tabs contain Lovelace *sections* that can be copied and pasted to other dashboards or view tabs on the iCloud3 dashboard.

See the Dashboard Builder chapter [here](chapters/1cs-dashboard-builder.md) for more information about the various view tabs, customizing your dashboard and how to create other iCloud3 dashboards.

The dashboard is organized to provide device and tracking information on on the left and the *Event Log* on the right.

-  **Left Side** - Shows the device_tracker and various sensor entities for the two devices showing the distance and travel time from Home, the interval between location requests and when the next request will be made, the battery level, and when it was last located.
- **Right Side** - The Event Log for Gary while traveling towards home.

![](../images/dashboard-allinfo-summary.png)





#### iCloud3 Event Log Lovelace Resource (if needed)

The Lovelace Resources points to the location of the *icloud3-event-log-card.js* file and must be set up for the Event Log to be displayed.  This is setup with iCloud3 is installed. However, if a problem occurs setting it up, the Event Log (on the right in the above screenshot) will not be displayed and the following will be displayed instead:

![](../images/lovelace-evlog-resource-error.png)

Do the following to set it up manually:

1. Select **☰ > HA Settings > Dashboards > ⋮ (Upper right corner) > Resources**. The following screen is displayed:
2. Select **+ Add Resource** to open the Add Resources window
3. Enter the following:
   - **URL** field -  Type **/local/icloud3/icloud3-event-log-card.js** 
   - **Resources type** - Select **JavaScript Module**
4. Select **Create (or Update)**

> *Note: Using another custom card directory* - If you move the Event Log card to another directory, the Lovelace Resources should automatically be changed. If something happens and it is not changed, change the directory (*icloud3*) in the URL statement on the above screen to the new directory name. Then select the new directory name in the *Event Log Directory* field on the *iCloud3 Configure Settings > Menu Page 2 > Other Parameters*  screen.



------
### Congratulations, iCloud3 is set up

If you successfully added the Lovelace tracking, Event Log card and the tracking data is displayed, you have successfully set up iCloud3 and Home Assistant does not have to be restarted, Review the rest of the documentation and the parameter screens



-----

### Installation Notes

The following Installation Notes are not part of the actual installation process but may be useful.

### Restart Home Assistant (if necessary)

If something does not work, errors or alerts are displayed or iCloud3 does not begin tracking devices, restart Home Assistant may solve the problem.

When iCloud3 starts, it follows a startup process to:

- Check the directory settings
- Load the configuration parameters
- Load the tracked and monitored devices
- Access the your iCloud account to get the devices tied to your account
- Get the information for the devices using the HA Mobile App
- Tie everything together
- Start tracking. 

The results of this process are shown in the Event Log and detailed in *Event Log During Startup* in a previous chapter. 

- Check the Event Log (it should display something) for error messages.
- Check the HA Log file (*config/home-assistant.log*)
- Verify that the device_tracker and sensor entities are set up. The *Devices & Settings > Integrations > iCloud3* entry should show at least one device_tracker and some entities for that device.



-----

### Clearing the Browser's Cache

When the a new version of the *Event Log card* is installed, it is not automatically loaded by your browser or the Mobile App. The browser's cache needs to be cleared.

#### Clear the Browser's Cache (Chrome, Edge, Safari, MacOS) {docsify-ignore}

The browser (Chrome, Edge, Safari) stores the Home Assistant screens in it's cache. This needs to be cleared to load the new version of the Event Log card.

1. Press **Ctrl-Shift-Delete**.
2. Select **Cached Images and Files**, the select **Clear Data**
3. Return to the Lovelace screen and click the **Refresh Icon**. 

Note: This process may be different for MacOS.



#### Clear the Home Assistant Mobile (Mobile App) Cache  {docsify-ignore}

The cache needs to be cleared when a new version of the Event Log is installed. A message, with instructions, is displayed when this is needed. It will need to be cleared on every device (iPhones, iPads) that is using the Mobile App. 

1. In the *Home Assistant Mobile App*, tap **☰ > HA Settings > Mobile App.**
2. Tap **Debugging > Reset front end cache**
3. Tap **Settings > Done**
4. Redisplay one of the Lovelace screens and pull it down to reload the screens.


-----

### iCloud3 Log File

iCloud3 writes logging records to the */config/icloud3-0.log* file based on the Log Level configuration setting. This includes:

- **Info** - Informative messages that display tracking results and some messages on it's operations,
- **Debug** - Debug messages that provide a lot more information on the data received from the Mobile App and the iCloud account, it's operational status, error messages and other records on how the devices are being tracked,
- **Rawdata** - Rawdata messages log the actual records sent to and received from the iCloud account, actual data received from the Mobile App, how zones, devices and sensors are set up and event activity during when iCloud3 is starting. The data received from Apple Location Services is filtered to remove any fields that are not used by iCloud3.
- **Unfiltered** - Displays the same rawdata described above without any filters. Every data field received from Apple Location Servers is displayed.

> The Log Level configuration setting is on the *Configure Settings > Page 2 > Format Parameters* screen. Some can also be selected on the *Event Log > Actions* list.

*Notes*: 
- All records are written to the *icloud3-0.log* file. A new file is created if the Log Level is Debug.
- The log file is closed at midnight and renamed *icloud3-1.log*. A new file is created for the new day.
- Log Level Debug and Rawdata have an  Auto-Reset option that will reset the Log Level to Info at midnight.
