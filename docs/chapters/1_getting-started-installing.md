

# Installing iCloud3, Setting up the HA Mobile App

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

###  Installing iCloud3

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

### (Optional) Installing the iCloud3 v3 Development Version (HACS Custom Installation)

New features are added to iCloud3 Development Version before they are released to the General Availability version on HACS. This Beta version can be added to HACS as a Custom Repository. Follow the instructions below:

- **Adding the iCloud3 Development Edition to HACS**

  1. Open HACS
  2. Select the 3-dots in the upper-right corner, then select *Custom Repository*.
  3. Enter the following values in the fields displayed:
     - Repository: `gcobb321/icloud3_v3`
     - Category: `Integration`
  4. Select **Add**

   ![](C:\Users\Gary\GitHub\icloud3_v3_docs\docs\images\hacs-process-highlighted.png)

  *Notes*:

  1. Additional information in the HACS User Guide can be found [here](https://www.hacs.xyz/docs/faq/custom_repositories/?h=reposit).

  2. Monitor the gcobb321/icloud3_v3 Issues page for an announcement that a new release is available.

  3. Download the *icloud3.zip* file from the *gcobb321/icloud3_v3 iCloud3 GitHub Repository Releases* page [here](https://github.com/gcobb321/icloud3_v3/releases). Follow the Manual instructions above. 

     


------

### Add the iCloud3 Integration

iCloud3 is a Home Assistant Integration and is configured on the Integrations screens like all the other Integrations you may be using.

1. Select **☰ > HA Settings > Devices & Services > Integrations**.
2. Select **+ Add Integration** in the lower-right hand corner.
3. Type **iCloud3**. Then select **iCloud3 v3** from the list of Integrations. *Do not select iCloud3, it is v2.4 if it is displayed.* The iCloud3 v3 entry will be added to the *Integrations* screen.
4. Open the *Configure Settings* screen.
   - Event Log has not been set - Select **☰ > HA  Settings > Devices & Services > Integrations**.
   - Event Log has been set up - Select the **Configure iCloud3 Settings** icon (gear) on the **Event Log**.
5. Select **iCloud3 > Configure**.



![](C:\Users\Gary\GitHub\icloud3_v3_docs\docs\images\cf-configure.png)

