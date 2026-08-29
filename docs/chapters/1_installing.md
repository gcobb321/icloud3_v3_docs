

# How to Install iCloud3 and Configure it for the first time

There are several steps that that need to be done to install and start using iCloud3 to track your devices. They are:

1. Install the iCloud3 custom component integration:
   - Install iCloud3 from HACS (or add it manually)
   - Install and configure the HA Mobile App if you are using it on any of your tracked devices (optional
   - Add the iCloud3 custom component
2. Configure iCloud3:
   - Add your Apple account
   -  Authenticate access to your Apple account
   - Import the devices in your Apple account
   - Build the iCloud3 Dashboard


------

##  Installing iCloud3

iCloud3 is available on the HACS and is installed using the same process as other HACS custom components.

- **Using HACS to install iCloud3**
  1. Open HACS.
  2. Select **Integrations**, type **icloud3** in the search bar.
  3. Select the **iCloud3, iDevice Tracker** item, then select **+Download** to download iCloud3 and follow the normal steps for installing an integration using HACS.

- **Manual Installation from the iCloud3 Repository Releases Page**
  1. Download the *icloud3 v3.x.x.zip* file from the *gcobb321/icloud3 iCloud3 GitHub Repository Releases* page [here](https://github.com/gcobb321/icloud3/releases). Selects *Assets* at the bottom, then the zip file. The file save screen is displayed, select the location on your computer and save the zip file.
  2. Unzip the file into the *config/custom_components/icloud3* directory on your Home Assistant server (ex.: Raspberry Pi)
  3. Restart Home Assistant



------

## Installing iCloud3 Development Version (Beta)

New features are added to iCloud3 Development Version before they are released to the General Availability version on HACS. This Beta version can be added to HACS as a Custom Repository. Follow the instructions below:

- **Adding the iCloud3 Development Edition to HACS**

  1. Open HACS
  2. Select the 3-dots in the upper-right corner, then select *Custom Repositories*.
  3. Enter the following values in the fields displayed:
     - Repository: `gcobb321/icloud3_v3`
     - Category: `Integration`
  4. Select **Add**

  ![](..\images\hacs-add-ic3-custom-repo.png)

  *Notes*:

  1. Additional information in the HACS User Guide can be found [here](https://www.hacs.xyz/docs/faq/custom_repositories/?h=reposit).

  2. Monitor the gcobb321/icloud3_v3 Issues page for an announcement that a new release is available.

  3. Download the *icloud3.v3.x.x.zip* file from the *gcobb321/icloud3_v3 iCloud3 GitHub Repository Releases* page [here](https://github.com/gcobb321/icloud3_v3/releases). Follow the Manual instructions above. 

     


------

## Add the iCloud3 Integration

iCloud3 is a Home Assistant Integration and is configured on the Integrations screens like all the other Integrations you may be using.

1. Select **☰ > HA Settings > Devices & Services > Integrations**.
2. Select **+ Add Integration** in the lower-right hand corner.
3. Type **iCloud3**. Then select **iCloud3** from the list of Integrations. The iCloud3 entry will be added to the *Integrations* screen.
4. Open the *iCloud3 Configure screen* as depicted below.
   - You have installed it for the first time:
     - Select **☰ > HA  Settings > Devices & Services > Integrations  > iCloud3  > Configure Gear Icon**.
   - You have installed it before and the Event Log has been set up:
     - Select the **Event Log > Purple Configure Gear Icon  > Configure Gear Icon**.

![](../screens/home_assistant/ha-integrations-icloud3-entry.png)

-----

## Configure iCloud3 for the first time

### Add your Apple Account

Click the Gear icon in the above image to open the iCloud3 Configure screens. Since you are doing this for the first time, the iCloud3 configuration file (*.storage/icloud3/configuration*) will be created with default values. The *Update Apple Account* screen is displayed.

![](C:\Users\Gary\GitHub\icloud3_v3_docs\docs\screens\apple_acct\apple-acct-update-first-time.png)

- Enter your Apple account email (username) and pasword.
- Click **Submit**

The username and password will be validated, iCloud3 will log into your Apple account and download the devices in your account. If *Locate All Devices* is enabled, all of the devices in your Family List will downloaded. If it is disabled, only your devices are downloaded. The *Authenticate Apple Account Sign-in* screen will be displayed.

### Authenticate Apple Account Sign-in

The next step is to authenticate iCloud3 access to your Apple account. This is done by entering the 6-digit 2fa code that will be sent to your trusted device. 

Three-methods of authentication are supported - getting the code from a Push notification pop-up window on your iPhone, getting the code in a Text message sent to a Trusted Phone and using a security key (YubiKey) that you will insert into the computer running HA (Mac, RPi, etc). 

iCloud3 defaults to the Push notification window and the code request is automatically sent. You should see the pop-up window display on your iPhone. Enter that 6-digit code in the Authentication Code field and click submit. The code will be sent to Apple and be verified. If Apple accepts the code, the *Import Apple Devices* screen is displayed.

![](C:\Users\Gary\GitHub\icloud3_v3_docs\docs\screens\authenticate\apple-acct-auth.png)

If you are using a security key or want to get the code from a text message, select the *Change Authentication Method* action at the bottom of the screen and click Submit. Then, select the method you want and return to this screen. Select *Request Authentication Code* to restart the process and click Submit. Then enter a new code or press the security key. Then select *Authenticate* and click Submit.

### Importing Apple Devices

The next step is to create the iCloud3 devices from the devices in your Apple account that was downloaded when you logged into your Apple account. Devices are grouped into three categories:

- Tracked (iPhone, Watch) - iCloud3 issues location requests to Apple when they are needed. The location, battery and other information is updated.
- Monitored (iPad, Mac) - These devices are updated using data Apple provides when the Tracked are located.
- Inactive (AirPods, other Apple devices) - Apple does not provide any location or battery information for these devices. 

Note: You can change the tracking mode for a device after the iCloud3 devices are created on the *iCloud3 Devices > Update Device* screen.

![](C:\Users\Gary\GitHub\icloud3_v3_docs\docs\screens\apple_acct\import-apple-devices.png)

- Click Submit to create the iCloud3 device_tracker and sensor entities for all of the devices that have been checked.

The *iCloud3 Device List* screen is displayed. 

### Review the iCloud3 Devices

This screen lists all of the devices that iCloud3 will Track and Monitor. Devices can be updated, added and deleted from this screen. 

![](C:\Users\Gary\GitHub\icloud3_v3_docs\docs\screens\device\cf-device-list.png)

## Complete the setup process

You have completed all of the steps needed to configure iCloud3. Exit back to the HA Devices & services screen.

- Select **Menu**, then click Submit to display to the Configure and *Devices and Sensor*s menu.
- Select **Exit**, then click Submit to end the Configuration session. 

The iCloud3 Dashboard will be created and added to the HA Sidebar with a *Cloud* icon and iCloud3 is restarted. The devices you added are located and all of the device_tracker and sensor entities are updated. 

![](C:\Users\Gary\GitHub\icloud3_v3_docs\docs\screens\dashboard-summary.png)

- Click the *Cloud* icon on the HA Sidebar to display the iCloud3 Dashboard screen.

That's it. Congratulations! You have installed iCloud3 and are tracking your devices. You entered 3-fields - your Apple email id, the Apple account password and the 6-digit authentication code. 

That was the easy part. Now for the hard part - review the rest of the documentation and see how the many features can be used. Be sure to review the *Core Component Details* section so you can get familiar with the *Event Log*, the *Dashboard Builder* and various Configure screens. Go through the *Configure Tracked Devices* and *Operational Settings* and look for things that might be useful to you.



Thanks and good luck

Gary Cobb aka GeeksterGary

*and if you like iCloud3, I like coffee*

<a href="https://www.buymeacoffee.com/gcobb321" target="_blank"><img src="images/buymeacoffee-sidebar-button.png"/></a>
