

# Installing the iCloud3 Integration

There are several steps that that need to be done to install and start using iCloud3 to track your devices. They are:

1. Install iCloud3 from HACS (or add it manually).
2. Install and configure the HA Mobile App if you are using it on any of your tracked devices (optional). 
3. Add the iCloud3 integrations component which adds iCloud3 and it's *Configure Settings* screens. 
4. Click the Gear Icon on the iCloud3 Integration screen to display *Configure Devices & Sensors* screen. 
5. Add your Apple Account on the *iCloud Account & Mobile App* screen.
6. Approve iCloud3 signing into your Apple Account on the *Authenticate Apple Acct Sign-in* screen
7. Add iCloud3 devices you want to track on the *iCloud3 Devices* screen.

Steps 1-3 are described below. Steps 5-7 (Adding and authenticating the Apple Account and adding tracked devices) are discussed later.


------

###  Installing iCloud3

iCloud3 is available on the HACS and is installed using the same process as other HACS custom components.

- **Using HACS to install iCloud3**
  1. Open HACS.
  2. Select **Integrations** and type **icloud3** in the search bar.
  3. Select the **iCloud3 v3, iDevice Tracker** item, then select **+Download** to download iCloud3 and follow the normal steps for installing an integration using HACS.

- **Manual Installation from the iCloud3 Repository Releases Page**
  1. Download the *icloud3 v3.x.x.zip* file from the *gcobb321/icloud3 iCloud3 GitHub Repository Releases* page [here](https://github.com/gcobb321/icloud3/releases). Selects *Assets* at the bottom, then the zip file. The file save screen is displayed, select the location on your computer and save the zip file.
  2. Unzip the file into the *config/custom_components/icloud3* directory on your Home Assistant server (ex.: Raspberry Pi)
  3. Restart Home Assistant



------

### Prelease versions are on the iCloud3 v3 Development Version GitHub Repository

New features are added to iCloud3 Development Version before they are released to the General Availability version on HACS. This Beta version can be added to HACS as a Custom Repository. Follow the instructions below:

- **Adding the iCloud3 Development Edition to HACS**

  1. Open HACS
  2. Select the 3-dots in the upper-right corner, then select *Custom Repositories*.
  3. Enter the following values in the fields displayed:
     - Repository: `gcobb321/icloud3_v3`
     - Category: `Integration`
  4. Select **Add**

  ![](C:\Users\Gary\GitHub\icloud3_v3_docs\docs\images\hacs-add-ic3-custom-repo.png)

  *Notes*:

  1. Additional information in the HACS User Guide can be found [here](https://www.hacs.xyz/docs/faq/custom_repositories/?h=reposit).

  2. Monitor the gcobb321/icloud3_v3 Issues page for an announcement that a new release is available.

  3. Download the *icloud3.v3.x.x.zip* file from the *gcobb321/icloud3_v3 iCloud3 GitHub Repository Releases* page [here](https://github.com/gcobb321/icloud3_v3/releases). Follow the Manual instructions above. 

     


------

### Add the iCloud3 Integration

iCloud3 is a Home Assistant Integration and is configured on the Integrations screens like all the other Integrations you may be using.

1. Select **☰ > HA Settings > Devices & Services > Integrations**.
2. Select **+ Add Integration** in the lower-right hand corner.
3. Type **iCloud3**. Then select **iCloud3 v3** from the list of Integrations. The iCloud3 v3 entry will be added to the *Integrations* screen.
4. Open the *iCloud3 Configure screen* as depicted below.
   - Event Log has not been set:
     - Select **☰ > HA  Settings > Devices & Services > Integrations  > iCloud3  > Configure Gear Icon**.
   - Event Log has been set up:
     - Select the **Event Log > Purple Configure Gear Icon  > Configure Gear Icon**.

![](C:\Users\Gary\GitHub\icloud3_v3_docs\docs\images\cf-configure.png)

