# Tracking Questions, Issues & Problems  {docsify-ignore}

-----


## Tracking Questions

+ What is the difference between *Locate Device(s) using Apple Accounts*  vs *Send Locate Request to Mobile App* +

  Both options will try to locate the iDevice. 
  - **Apple Account Locate** - (Preferred) iCloud3 requests the location from iCloud Location Services and gets an immediate response with it&#39;s location. It also gets the location of the other devices in the Family Sharing list.
  - **Mobile App Request** - iCloud3 sends a message to that iDevice asking for it's location and then waits for a response. There may be a delay in providing the location if the device is asleep, the Mobile App is not loaded and running or if it is running in the background.
  
  
  + Occasionally, My iPhone does not exit the Home Zone when I leave +

  This question is discussed below.



+ How can I display a map of where my iPhone have been +

  HA provides a Lovelace map card that will show the location track of your iDevices. Refer to the HA Map documentation on setting it up. Add each Person (_person.gary_) or iDevice (<em>devicetracker.gary_iphone</em>)  you want to track on the Map configuration screen in the Entity field.
  


-----
## Tracking Issues and Problems

+ Occasionally, my iPhone does not Exit the Home Zone when I leave +

  My wife and I were at home, ran a short trip (5-6km) and returned. My iPhone has the Mobile App and my wife's does not (or she wore her Watch). My iPhone did not exit the Home zone and no activity was recorded until I returned Home. Her iPhone/Watch didn>t either. Other HA devices did record when I left. 
  What happened? What can I do?

  - The Mobile App on your phone did not issue an Exit Trigger that took your iPhone out of the Home Zone and you returned before the next update time was reached. 
  - Her iPhone/Watch without the Mobile App next update time had not been reached either and you returned Home before then.

  You will never know why events work fine most of the time but fail occasionally. It could be the Mobile App on your iPhone was asleep and did not wake up to issue an Exit Trigger or it was not running, the cell signal was poor at then time, the location was old or the gps accuracy was poor, etc. Also, the iDevice without the Mobile App left and returned before the next update time was reached.
  There are several things you can do:

  - Reduce the inzone interval time for devices not using the Mobile App. It is best not to go below 10-minutes or the interval will approach the >old location> threshold (usually about 3-minutes). A good location could be rejected, a bad location could be used when it shouldn>t or an old location will be within the >old threshold> and used again when a new location should be requested.
  - See if there is another way to identify when the iPhone leaves home. It might be a camera, the garage door opening/closing, the iPhone disconnects from the network, etc. When this happens, and it's iCloud3 device_tracker state still shows Home or the [devicename]_zone_fname entity is still Home, issue an iCloud3 service call to locate the iPhone. This will then update it's current location and take it out of the Home zone.  An example of a location script is shown below.

	```
	alias: iCloud3 Locate (Gary)
	trigger: []
	condition: []
	action:
	
	  - service: icloud3.action
	    data:
	      command: locate
	      device_name: gary_iphone
	   mode: single
	```




+ My iPhone never exits the Home Zone or mine exits but my wife's does not +
  
  Not changing to Away when you leave a zone means iCloud3 is not getting the zone exit trigger from the Mobile app. Check the following:
  
  - Verify the Mobile App device_tracker entity name has not changed. 
  
  - Go to *Configuration &gt; iCloud3 Devices &gt; Select device&gt; Mobile App device_tracker entity* and verify the tracked device has a valid Mobile App device_tracker entity assigned.
  
  - The HA mobile app integration is not installed. 
  
  - Go to *Installing and Configuring iCloud3 &gt; Step #2 - Install the Mobile App on your iPhone or iPad* for more information.




+ The Mobile app device_tracker entity location is not being updated by the Mobile app +

    The Mobile App logs events as they take place, including location changes and zone enter/exit activity. On the device, open the Mobile App. Select *HA Settings &gt; Companion App &gt; Debugging*. Then select *Event Log* to see what events the Mobile App responded to or *Location History* to display a map showing the devices location at various times.
    
  - Check the device_tracker state value to see if is being updated. Go to *Developer Tools &gt; States &gt; device_tracker entity* and see if the zone name is displayed. The value is *not_home* when you are not in a zone and the zone>s name when you are in a zone.
  - erify the Mobile App is sharing location information. Go to *Installing and Configuring iCloud3 &gt; Step #2 - Install the Mobile App on your iPhone or iPad* for screenshots of the correct settings.
  - Tracking Monitors can be displayed in the Event Log that show update activity. Select *Event Log &gt; Actions &gt; Show/Hide Tracking Monitors*. Look at the state change and trigger change values and times they changed. See *Debugging with Tracking Monitors* below.







  - 





