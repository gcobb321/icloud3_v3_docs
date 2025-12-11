# Frequently Asked Questions {docsify-ignore}





+ App Specific Passwords +

  App Specific Passwords are not supported by iCloud3. iCloud3 is a program running on a computer, not an app running on an iDevice. It uses web service calls to request the location of the devices in the iCloud's Family Sharing List. Apps running on iDevices use a different access method that is not available by programs. This is discussed further in the _Apple Accounts_ section.



+ Occasionally, My iPhone does not exit the Home Zone when I leave +

  This question is discussed in *Trouble Shooting > Tracking Issues* section.



+ Can I use a Hardware Security Key instead of my iCloud account password +

  Not at the present time but it is under development. See the *Apple Accounts*  section for more information.



+ How can I display a map of where my iDevices have been +

  HA provides a Lovelace map card that will show the location track of your iDevices. Refer to the HA Map documentation on setting it up. Add each Person (_person.gary_) or iDevice (<em>devicetracker.gary_iphone</em>)  you want to track on the Map configuration screen in the Entity field.



+ Locate Device(s) using _Apple Accounts_  vs *Send Locate Request to Mobile App* +

  Both options will try to locate the iDevice. 
  - **Apple Account Locate** - (Preferred) iCloud3 requests the location from iCloud Location Services and gets an immediate response with it&#39;s location. It also gets the location of the other devices in the Family Sharing list.
  - **Mobile App Request** - iCloud3 sends a message to that iDevice asking for it's location and then waits for a response. There may be a delay in providing the location if the device is asleep, the Mobile App is not loaded and running or if it is running in the background.
  
  
  
+ HACS displays information about the version of iCloud3 it has downloaded +

  HACS keeps that version number in it's database to be able to identify when an update is available.
  
    ![](../images/version-hacs.png)	
  
  The version that is running on your system might not be the actual version of iCloud3 that HACS thinks is installed and running. The only way to know is to verify the version in iCloud3 itself.  The following screens highlight the version number running in red.
  - On the *device_tracker.[devicename]* attributes for every device being tracked by iCloud3.
  - In the Event Log  when iCloud3 starts at the beginning and end of the startup process.
  - In the Event Log  when you hover a mouse over the Actions list or when you open the Actions list.
  - In the iCloud3 configuration file *config./storage/icloud3/configuration*  (admin rights must be enabled).
  - In the _config/icloud3.log_  log file.
  
    ![](../images/version-running.png)
  
+ How do I setup HACS to also show the iCloud3 v3, Development Version +

  See *Installing iCloud3 > iCloud3 Development Version (Beta)* for detailed instructions
