# Frequently Asked Questions {docsify-ignore}



### Apple Account Authentication

+ Can I use an *App Specific Password* instead of my real password +

  No. App Specific Passwords are not supported by iCloud3. iCloud3 is a program running on a computer, not an app running on an iDevice. It uses web service calls to request the location of the devices in the iCloud's Family Sharing List. Apps running on iDevices use a different access method that is not available by programs. This is discussed further in the _Apple Accounts_ section.



+ Can I use a Hardware Security Key instead of my iCloud account password +

  Not at the present time but it is under development. See the *Apple Accounts*  section for more information.



+ Occasionally, My iPhone does not exit the Home Zone when I leave +

  This question is discussed in *Trouble Shooting > Tracking Issues* section.



+ I cannot log into my Apple account, should I delete the *.storage/icloud3.apple_acct* cookie files +

  No, you should not. It will not hurt anything but it does not help anything either. In fact, when you request a new code on the *Authenticate Apple Account Signin* screen, iCloud3 deletes the *session* files which causes Apple to reauthenticate the account and display a new verification code.

  

+ I keep getting a notification that a verification code is needed +

  Apple notifies iCloud3 that a reauthentication code is needed to continue accessing the iCloud account. You need go through *Authenticate Apple Account Signin* to enter the 6-digit verification code that is displayed on one of your trusted devices. 

+ I can not enter the code right now. The alert was displayed on another device. I forgot the code. I lost the code. + 

​	The Authenticate Apple Account Signin message will continue to appear until the code is entered. Although, Apple will continue to provide location information for a while, it  will eventually stop iCloud3 from accessing your iCloud account until it is entered.

+ Will Apple stop asking for the code if I restart Home Assistant or delete and reinstall iCloud3 Integration +

​	No, Apple requires that access to your iCloud account is only done from an authorized device that has been verified. iCloud3 must comply with this request and provide a valid 6-digit verification code. When you restart Home Assistant or reinstall the iCloud3 Integration, Apple will just keep asking for the verification code. 




### Tracking Results

+ How can I display a map of where my iPhone have been +

  HA provides a Lovelace map card that will show the location track of your iDevices. Refer to the HA Map documentation on setting it up. Add each Person (_person.gary_) or iDevice (<em>devicetracker.gary_iphone</em>)  you want to track on the Map configuration screen in the Entity field.



+ What is the difference between *Locate Device(s) using Apple Accounts*  vs *Send Locate Request to Mobile App* +

  Both options will try to locate the iDevice. 
  - **Apple Account Locate** - (Preferred) iCloud3 requests the location from iCloud Location Services and gets an immediate response with it&#39;s location. It also gets the location of the other devices in the Family Sharing list.
  - **Mobile App Request** - iCloud3 sends a message to that iDevice asking for it's location and then waits for a response. There may be a delay in providing the location if the device is asleep, the Mobile App is not loaded and running or if it is running in the background.
  
  

### Installing iCloud3

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



