## Configuration and Setup Issues  {docsify-ignore}



-----
## Configuring iCloud3 Devices

+ An iPhone/iPad is not in the *Update iCloud3 Device screen > Apple Account/iCloud Device* selection list +

  The device must be able to be located on the Apple Account owners device before it can be located by iCloud3.

  - Go to the *Find My App > People* screen and make sure the missing device is displayed. If it is not, then *Location Sharing* is probably not enabled on the missing device. 

  - On the missing device, go to the *Settings App > Privacy and Security > Location Services*, then select *Share My Location*. *Find My iPhone/iPad* should be On (*Find My Network* and *Send Last Location* should be enabled), *Share My Location* should be enabled.

  

-----

## Installing iCloud3

+ How do I setup HACS to also show the iCloud3 v3, Development Version +

  See *Installing iCloud3 > iCloud3 Development Version (Beta)* for detailed instructions



+ Why is the HACS version number is not the same as the iCloud3 that is running  +

  HACS keeps that version number in it's database to be able to identify when an update is available.

	![](../images/version-hacs.png)	

  The version that is running on your system might not be the actual version of iCloud3 that HACS thinks is installed and running. The only way to know is to verify the version in iCloud3 itself.  You will find the iCloud3 version that is running here:

  - On the *device_tracker.[devicename]* attributes for every device being tracked by iCloud3.
  - In the Event Log  when iCloud3 starts at the beginning and end of the startup process.
  -	In the Event Log  when you hover a mouse over the Actions list or when you open the Actions list.
  - In the iCloud3 configuration file *config./storage/icloud3/configuration*  (admin rights must be enabled).





-----
## Event Log

+ I'm getting a *Custom element doesn't exist: icloud3-event-log-card* error setting up the Event Log Card +

  - **Check the Directory containing the Event Log Card program** -  When iCloud3 is installed, the Event Log's *icloud3-event-log-card.js* file is copied to the *www/icloud3* directory. Verify that the file was copied to that directory.
  
  
    - **Check the Directory name in the iCloud3 Configuration** - Verify the directory name containing the Event Log's  *icloud3-event-log-card.js* file is correct on the *Configure Settings > Device Settings and Other Other Parameters* screen. It is listed at the bottom of the parameter list. If not, select the correct directory in the list.
  
  
    - **Check the Lovelace Resource parameter** - This is a Lovelace parameter specified on the *HA Settings > Dashboard > > ... > Resources* screen. This screen specifies *local/directory/file-name.js* for various Lovelace card `.js` files used in HA. iCloud3 tries to add or update this list when it starts with the *www/icloud3* directory entry. 
  
      - Find and verify that the iCloud3 entry, */local/icloud3/icloud3-event-log-card.js* is in the list. Add it if is not. See the *Core Component Details > Event Log* item  <a href="#/chapters/2_event-log?id=lovelace-resource-configuration">here</a> for more information.
      - The value you enter for the resource starts with */local*. It does not start with */www*.
  
  
    - **Find and verify the iCloud3 entry** - The item  */local/icloud3/icloud3-event-log-card.js* should be in the Resources list. Add it if is not. The value you enter for the resource starts with */local*. It does not start with */www*.
  
  
    - **Check the value you are entering when setting up the Dashboard** - You specify the *icloud3-event-log-card* as a custom card when you add it to a Dashboard screen is `type: 'custom:icloud3-event-log-card'`.  More information about this is in the *iCloud3 Components, Event Log* documentation <a href="#/chapters/1.2-event-log?id=create-a-new-dashboard-card-for-the-event-log">here</a>. 
  
      - It must not have any spaces at the end. 
      - Do not add `.js` at the end. 
      - These are wrong:  `type: 'custom:icloud3-event-log-card  '` and `type: 'custom:icloud3-event-log-card.js'`
  

