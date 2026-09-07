## Configure Settings Field Reference  {docsify-ignore}

This is a cross-reference of every data field on the iCloud3 Configure Settings screens.
Field names are the labels displayed on the screen and come from the `data` and
`data_description` entries in `translations/en.json`. Selection list options come from
`configure/const_form_lists.py`.

Each entry is shown as:

- **FIELD LABEL** — Description of the field. Selection options, when the field has them, are listed as bullets below the description.

The line under each screen name identifies the screen it is selected from.

The **ACTION COMMANDS** field appears on almost every screen. Its line lists the commands
offered on that screen; click the line to open the full description of each command.

---

## Installation Screens

### iCloud3 v3 Integration Installer

Selected from Screen - *HA Settings → Devices & Services → Add Integration → iCloud3*

- **CONTINUE** — Select SUBMIT to complete the iCloud3 installation.
- **PREVIOUS ICLOUD3 CONFIG WAS FOUND. DO YOU WANT TO REINITIALIZE THE APPLE ACCOUNTS & DEVICES?** — The iCloud3 Configuration has been previously set up and is normally used when adding the iCloud3 Integration again. Check this option if you want to remove the Apple Account and Devices configuration and start over.
- **Select to continue iCloud3 installation. Then RESTART HOME ASSISTANT** — Continue the iCloud3 installation, then restart Home Assistant.

---

## Apple Account Screens

### Apple Accounts

Selected from Screen - *Menu #1*

- **DATA SOURCE** — Header for the Data Source section of the screen.
- **APPLE ICLOUD ACCOUNTS** — Header for the Apple iCloud Accounts section of the screen.
- **(no label)** — The list of Apple Accounts that have been set up. Select the account to be updated, authenticated, imported from or deleted.
- **(no label)** — Separator for the Mobile App Integration section of the screen.
- **ACTION COMMANDS** — Update Apple Account, Authenticate Apple Acct Sign-In, Import Apple Devices, Delete Apple Account, Menu +

    - UPDATE APPLE ACCOUNT → Update the Username/Password of the selected Apple Account, Add a new Apple Account, Remove the Apple Account
    - AUTHENTICATE APPLE ACCT SIGN-IN → Send/Request the 6-digit Authentication Code
    - IMPORT APPLE DEVICES → Create iCloud3 devices from the devices in the Apple Accounts
    - DELETE APPLE ACCOUNT → Delete the selected Apple Account. Delete or reassign iCloud3 devices using it
    - ➤ MENU → Display the Menu screen

### Update Apple Account Username/Password

Selected from Screen - *Apple Accounts*

- **ACCOUNT SELECTED** — The Apple Account being updated.
- **USERNAME** — Email address/username used to sign in to the Apple Account.
- **PASSWORD** — Apple Account password.
- **APPLE SERVER LOCATION** — The country hosting this account's Apple Server:
    - USA/OTHER - The Apple Server is not located in China
    - CHINA - The Apple Server is located in China (GCJ02)
    - CHINA - The Apple Server is located in China (GCJ02 → WGS84)
    - CHINA - The Apple Server is located in China (BD09 → WGS84)
- **LOCATE ALL DEVICES (Only applies with multiple Apple Accounts)** — Locate all devices in the Apple Account. ENABLED locates the Owner's and other Family members' devices in the Apple Account; DISABLED locates only the Owner's devices.
- **CHINA USERS** — Use Apple Account Servers located in China (`.cn` URL suffix).
- **ACTION COMMANDS** — Save, Log In & Import Apple Devices, Authenticate Apple Acct Sign-In, Other Apple Account Parameters, Return → Apple Accounts +

    - SAVE, LOG IN & IMPORT APPLE DEVICES → Save any configuration changes, Log into the Apple Account, Import Apple devices
    - LOG INTO APPLE ACCT → Log into the Apple Account, Save any configuration changes
    - AUTHENTICATE APPLE ACCT SIGN-IN → Send/Request the 6-digit Authentication Code
    - OTHER APPLE ACCOUNT PARAMETERS → Set other config parameters (China Apple Server Location)
    - STOP USING AN APPLE ACCOUNT → Stop using an Apple Account, Remove it from the Apple Accounts list and all devices using it
    - STOP RETRYING LOGIN → Stop retrying to log into the Apple Account
    - ➤ RETURN → APPLE ACCOUNTS → Return to the screen showing the Apple Accounts

### Other Apple Account Parameters

Selected from Screen - *Update Apple Account Username/Password*

- **APPLE SERVER LOCATION (CHINA)** — Always display the Apple Server Location selection field on the `Apple Acct Username/Password` screen (China, Hong Kong).
- **APPLE SERVER LOCATION** — The country hosting this account's Apple Server:
    - USA/OTHER - The Apple Server is not located in China
    - CHINA - The Apple Server is located in China (GCJ02)
    - CHINA - The Apple Server is located in China (GCJ02 → WGS84)
    - CHINA - The Apple Server is located in China (BD09 → WGS84)
- **PASSWORD SRP** — How the password should be verified when logging into the Apple Account. The PasswordSRP protocol sends an encoded key over the internet to Apple instead of sending the password itself:
    - ENABLED - Use the Password SRP Protocol
    - DISABLED - Use the standard Password protocol
    - NOTES - There are times when Apple servers will refuse the password if too many login attempts have been made in a short period of time. This is done to prevent fraudulent logins. An Error 503-Server Refuses Connection is returned.
- **ACTION COMMANDS** — Save & Return, Return → Update Apple Account +

    - ➤ SAVE & RETURN → Update Configuration File, Return to the Previous screen
    - ➤ RETURN → UPDATE APPLE ACCOUNT → Return to the Update Apple Account screen

### Remove an Apple Account

Selected from Screen - *Apple Accounts*

- **ACCOUNT SELECTED** — The Apple Account being deleted.
- **HOW SHOULD DEVICES ASSIGNED TO THIS APPLE ACCT BE HANDLED** — The action taken on the devices that are using this Apple Account:
    - REASSIGN DEVICES → Search for another Apple Account with this device and reassign it to that Apple Account. Set it to Inactive if one is not found
    - DELETE DEVICES → Delete all devices that are using this Apple Account
    - SET DEVICES TO INACTIVE → Set the devices using this Apple Account to Inactive. They will be assigned to another Apple Account later
- **CONFIRM DELETING THE APPLE ACCOUNT** — Delete Apple Account, Return +

    - DELETE APPLE ACCOUNT → Delete the selected Apple Account. Delete or reassign iCloud3 devices using it
    - ➤ RETURN → Return to the previous screen. Cancel any unsaved changes

---

## Apple Account Authentication Screens

### Authenticate Apple Account Sign-In

Selected from Screen - *Menu #1*

- **APPLE ACCOUNT TO BE AUTHENTICATED** — The Apple Account to be authenticated.
- **METHOD** — Send the Code to a Push Notification Window, in a Text Msg or use a Security Key:
    - Authentication Code popup window
    - Text Message to `……{method_info}`
    - Security Key ({method_info})
- **AUTHENTICATION CODE** — The 6-digit Authentication Code displayed on the Trusted Devices.
- **TERMS OF USE** — Accept the Apple `Terms of Use`. For more information, go to http://icloud.com.
- **ACTION COMMANDS** — Request Authentication Code or Security Key Keypress, Authenticate, Change Authentication Method +

    - REQUEST AUTHENTICATION CODE or SECURITY KEY KEYPRESS → Untrust the Apple Acct. Get a new Authentication code or Start the Hardware Key keypress Process
    - AUTHENTICATE → Send the Authentication Code back to Apple or Confirm the Security Key security code
    - CHANGE AUTHENTICATION METHOD → Select a new method (Pop-up Window, Text Message, Security Key), Refresh Trusted Phone Numbers & Security Key names
    - ACCEPT `TERMS OF USE` → Send `I Agree` to Apple updates to the `Terms of Use`
    - APPLE DID NOT SEND A CODE (PUSH/TEXT), GET ONE FROM APPLE.COM → Sign into your Apple Acct, get a code, enter it here and send to Apple
    - ➤ RETURN → APPLE ACCOUNTS → Return to the screen showing the Apple Accounts
    - ➤ RETURN → HA ICLOUD3 CONFIGURE SCREEN → Close Authentication screen and return to HA
    - ➤ MENU → Display the Menu screen

### Change Apple Account Authentication Method

Selected from Screen - *Authenticate Apple Account Sign-In*

- **APPLE ACCOUNT BEING AUTHENTICATED** — The Apple Account being authenticated.
- **AUTHENTICATION METHOD** — Method used to authenticate the Apple Account:
    - Authentication Code popup window
    - Text Message to `……{method_info}`
    - Security Key ({method_info})
- **ACTION COMMANDS** — Refresh Trusted Phone Numbers/Security Key Names, Save & Return +

    - REFRESH TRUSTED PHONE NUMBERS/SECURITY KEY NAMES → Get the Trusted Phone Numbers or the registered Security Key names from Apple
    - ➤ SAVE & RETURN → Update Configuration File, Return to the Previous screen

### Touch the Security Key

Selected from Screen - *Authenticate Apple Account Sign-In*

This screen displays progress only and has no data fields. It shows the key name and the
number of seconds remaining before the keypress request times out.

### Get an Authentication Code from Apple.com

Selected from Screen - *Authenticate Apple Account Sign-In*

- **AUTHENTICATION CODE** — Authentication Code just received by logging into your Apple Account.
- **ACTION COMMANDS** — Authenticate, Return +

    - AUTHENTICATE → Send the Authentication Code back to Apple or Confirm the Security Key security code
    - ➤ RETURN → Return to the previous screen

---

## Device Screens

### iCloud3 Devices

Selected from Screen - *Menu #1*

- **(no label)** — The list of Tracked and Monitored iCloud3 devices. Select the device to be updated or deleted.
- **ACTION COMMANDS** — Update the Device, Import Apple Devices, Delete Device, Change Device Order, Menu +

    - UPDATE THE DEVICE → Update the selected device, Display more Devices on the next page
    - IMPORT APPLE DEVICES → Create iCloud3 devices from the devices in the Apple Accounts
    - DELETE DEVICE → Delete the selected device
    - CHANGE DEVICE ORDER → Change the tracking order of the Devices and their display sequence on the Event Log
    - ➤ MENU → Display the Menu screen

### Add iCloud3 Device

Selected from Screen - *iCloud3 Devices*

- **ICLOUD3 DEVICE_TRACKER ENTITY ID** — The HA `device_tracker` entity for this device, for example `gary_iphone`. This is the entity you are assigning to the iCloud3 device you want to track.
- **FRIENDLY NAME** — Displayed in HA entities and on the Event Log, for example `Gary-iPhone`.
- **APPLE ACCOUNT DEVICE** — The Apple Acct device providing location data. The list contains the devices in the Apple Account Family Sharing list:
    - Apple iCloud Location Service is not used
    - *(followed by the Apple Account device list)*
- **MOBILE APP DEVICE** — Mobile App `device_tracker` entity providing location data and zone triggers:
    - None - The Mobile App is not installed on this device
    - *(followed by the Mobile App device list)*
- **PICTURE** — Image of the person normally using this device. 44x44 pixels is a good size:
    - None - Display the Device's Icon instead of a picture
    - *(followed by the image files found in the selected `/www` directories)*
- **ICON** — Icon to display when the Picture has not been selected (=None).
- **DEVICE TYPE** — iPhone, iPad, Watch, etc.:
    - iPhone
    - Watch-WiFi+Cell
    - Watch-WiFi
    - iPad-WiFi
    - iPad-WiFi+Cell
    - AirPods
    - Mac
    - iPod
    - Other
- **TRACKING MODE** — Location request method (Tracked, Monitored, Inactive):
    - Track - Request Location and track the device
    - Monitor - Report location only when another tracked device is updated
    - INACTIVE - Device is inactive and will not be tracked
- **MOBILE APP INSTALLED** — The HA Mobile App is installed on this device.
- **ACTION COMMANDS** — Add a New Device, Return → iCloud3 Devices +

    - ADD A NEW DEVICE → Add a new device to be tracked by iCloud3
    - ➤ RETURN → ICLOUD3 DEVICES → Return to the screen showing the Tracked and Monitored devices

### Import Apple Devices into iCloud3

Selected from Screen - *iCloud3 Devices*, *Apple Accounts* or *Authenticate Apple Account Sign-In*

- **TRACKED DEVICES** — iCloud3 `device_tracker` entities that will be actively tracked.
- **MONITORED DEVICES** — iCloud3 `device_tracker` entities that will be monitored.
- **INACTIVE DEVICES** — Apple Devices and Accessories that can not be tracked.
- **ACTION COMMANDS** — Add Imported Apple Devices, Return → iCloud3 Devices, Return → Apple Accounts, Menu +

    - ADD IMPORTED APPLE DEVICES → Create iCloud3 device_tracker entities from imported Apple devices
    - ➤ RETURN → ICLOUD3 DEVICES → Return to the screen showing the Tracked and Monitored devices
    - ➤ RETURN → APPLE ACCOUNTS → Return to the screen showing the Apple Accounts
    - ➤ MENU → Display the Menu screen

### Update iCloud3 Device

Selected from Screen - *iCloud3 Devices*

- **ICLOUD3 DEVICE_TRACKER ENTITY ID** — The HA `device_tracker` entity assigned to this device.
- **DISPLAY NAME** — Displayed in HA `device_tracker` and sensor names and on the Event Log.
- **APPLE ACCOUNT iCLOUD DEVICE** — Apple iCloud device providing location data:
    - Apple iCloud Location Service is not used
    - *(followed by the Apple Account device list)*
- **MOBILE APP DEVICE** — Mobile App `device_tracker` entity providing location data and zone triggers:
    - None - The Mobile App is not installed on this device
    - *(followed by the Mobile App device list)*
- **PICTURE** — Image of the person normally using this device. 44x44 pixels is a good size:
    - None - Display the Device's Icon instead of a picture
    - *(followed by the image files found in the selected `/www` directories)*
- **ICON** — Icon to display when the Picture has not been selected (=None).
- **DEVICE TYPE** — iPhone, iPad, Watch, etc.:
    - iPhone
    - Watch-WiFi+Cell
    - Watch-WiFi
    - iPad-WiFi
    - iPad-WiFi+Cell
    - AirPods
    - Mac
    - iPod
    - Other
- **TRACKING MODE** — How location requests should be done (Full tracking, Monitor, Inactive):
    - Track - Request Location and track the device
    - Monitor - Report location only when another tracked device is updated
    - INACTIVE - Device is inactive and will not be tracked
- **INZONE INTERVAL** — Time between location requests when the device is in a zone. The range is 5 to 480 minutes.
- **DISPLAY RARELY UPDATED PARAMETERS** — Check and Submit to update these items.
- **ZONE LOG ACTIVITY** — Enter/exit zone info (date, time, distance) is saved to a spreadsheet `.csv` file. Select None, one or more zones, and the activity file name format:
    - None
    - *(followed by the HA zones that have been set up)*
    - ⎯⎯⎯⎯⎯⎯ ACTIVITY FILE NAME ⎯⎯⎯⎯⎯⎯
    - ⋙ Zone ([year]-[zone].csv)
    - ⋙ Device ([year]-[device].csv)
    - ⋙ Device+Zone ([year]-[device]-[zone].csv)
    - ⋙ Zone+Device ([year]-[zone]-[device].csv)
- **TRACK-FROM-ZONES** — Track travel time and distance from Home and other zones. The list contains the HA zones that have been set up.
- **TRACK-FROM-HOME ZONE OVERRIDE** — Use this zone instead of Home for tracking results. Normally, the Home zone is used as the primary Track-from-Zone for all tracking (travel time, distance, etc). However, a different zone can be used if you are away from Home for an extended period or the device is normally at another location (vacation house, second home, parent's house, etc.). This can be set globally for all devices on the Special Zones screen.
- **FIXED INTERVAL** — A fixed time between location requests when not in a zone. iCloud3 calculates the interval for the next locate request and uses the calculated value if this is not set (= 0). This value will NOT be used when the calculated interval is less than 5-min, the current location data is old, the device is off-line or when the device is not in a zone.
- **ACTION COMMANDS** — Save & Return, Update Other Device Parameters, Return → iCloud3 Devices, Menu +

    - ➤ SAVE & RETURN → Update Configuration File, Return to the Previous screen
    - UPDATE OTHER DEVICE PARAMETERS → Update the rarely changed device parameters
    - ➤ RETURN → ICLOUD3 DEVICES → Return to the screen showing the Tracked and Monitored devices
    - ➤ MENU → Display the Menu screen

### Update Other Device Parameters

Selected from Screen - *Update iCloud3 Device*

- **ICLOUD3 DEVICE_TRACKER ENTITY ID** — The HA `device_tracker` entity assigned to this device.
- **DISPLAY NAME** — Displayed in HA `device_tracker` and sensor names and on the Event Log.
- **DEVICE TYPE** — iPhone, iPad, Watch, etc.:
    - iPhone
    - Watch-WiFi+Cell
    - Watch-WiFi
    - iPad-WiFi
    - iPad-WiFi+Cell
    - AirPods
    - Mac
    - iPod
    - Other
- **TRACKING MODE** — How location requests should be done (Full tracking, Monitor, Inactive):
    - Track - Request Location and track the device
    - Monitor - Report location only when another tracked device is updated
    - INACTIVE - Device is inactive and will not be tracked
- **INZONE INTERVAL** — Time between location requests when in a zone.
- **ZONE LOG ACTIVITY** — Enter/exit zone info (date, time, distance) is saved to a spreadsheet `.csv` file:
    - None
    - *(followed by the HA zones that have been set up)*
    - ⎯⎯⎯⎯⎯⎯ ACTIVITY FILE NAME ⎯⎯⎯⎯⎯⎯
    - ⋙ Zone ([year]-[zone].csv)
    - ⋙ Device ([year]-[device].csv)
    - ⋙ Device+Zone ([year]-[device]-[zone].csv)
    - ⋙ Zone+Device ([year]-[zone]-[device].csv)
- **TRACK-FROM-ZONES** — Track travel time and distance from Home and other zones.
- **TRACK-FROM-HOME ZONE OVERRIDE** — Use this zone instead of Home for tracking results. Normally, the Home zone is used as the primary Track-from-Zone for all tracking (travel time, distance, etc). However, a different zone can be used as the primary Track-from-Zone if you are away from Home for an extended period or the device is normally at another location (vacation house, second home, parent's house, etc.). This can be set globally for all devices on the Special Zones screen.
- **FIXED INTERVAL** — A fixed time between location requests when not in a zone. iCloud3 calculates the interval for the next locate request and uses the calculated value if this is not set (= 0). This value will NOT be used when the calculated interval is less than 5-min, the current location data is old, the device is off-line or when the device is not in a zone.
- **ACTION COMMANDS** — Save & Return, Return → Update iCloud3 Device +

    - ➤ SAVE & RETURN → Update Configuration File, Return to the Previous screen
    - ➤ RETURN → UPDATE ICLOUD3 DEVICE → Return to Update iCloud3 Device screen

### Delete iCloud3 Device

Selected from Screen - *iCloud3 Devices*

- **SELECTED DEVICE** — The device that will be deleted.
- **DELETE OPTIONS** — Yes, No +

    - YES → Complete the requested action
    - NO → Cancel the request

### Review Untracked (Inactive) Devices

Selected from Screen - *iCloud3 Devices*, or automatically when exiting the Configure Settings session

- **TRACK DEVICES** — Update these Devices to Tracked (from Inactive). iPhone/Watch devices are Tracked, iPad/Mac devices are Monitored.
- **ACTION COMMANDS** — Save +

    - ➤ SAVE → Update the Tracking Mode of the selected devices, Tracked-iPhone/Watch devices, Monitored-iPad/Mac devices

### Event Log Device Display Sequence

Selected from Screen - *iCloud3 Devices*

- **ICLOUD3 DEVICES** — The devices in the order they are displayed in the Event Log heading area and in Event Log messages. Select the device to be moved.
- **ACTION COMMANDS** — Move Up, Move Down, Save & Return, Return → iCloud3 Devices +

    - MOVE UP → Move the Device up in the list
    - MOVE DOWN → Move the Device down in the list
    - ➤ SAVE & RETURN → Update Configuration File, Return to the Previous screen
    - ➤ RETURN → ICLOUD3 DEVICES → Return to the screen showing the Tracked and Monitored devices

### Set up Picture Directory Filter

Selected from Screen - *Update iCloud3 Device* (select `SET PICTURE DIRECTORY FILTER` in the PICTURE field)

- **Group 1 - Directory 1-5** — Select the `\www` directories 1-5 to be searched for image (png, jpg) files.
- **Group 2 - Directory 6-10** — Select the `\www` directories 6-10 to be searched for image (png, jpg) files.
- **Group 3 - Directory 11-15** — Select the `\www` directories 11-15 to be searched for image (png, jpg) files.
- **Group 4 - Directory 16-20** — Select the `\www` directories 16-20 to be searched for image (png, jpg) files.
- **Group 5 - Directory 21-25** — Select the `\www` directories 21-25 to be searched for image (png, jpg) files.
- **ACTION COMMANDS** — Save & Return, Return +

    - ➤ SAVE & RETURN → Update Configuration File, Return to the Previous screen
    - ➤ RETURN → Return to the previous screen

---

## Tracking & Display Parameter Screens

### Tracking Parameters

Selected from Screen - *Menu #2*

- **GPS LOCATION AND ZONE TRIGGER DATA SOURCES** — Source of location data and zone Enter/Exit triggers used to track iCloud3 devices:
    - ICLOUD & MOBILE APP → Request data from iCloud and the Mobile App
    - ICLOUD ONLY → Mobile App is not used
    - MOBILE APP ONLY → iCloud Location Services is not used
- **DISCARD POOR RESULTS** — Discard Location Updates with Poor GPS Accuracy when in a Zone.
- **GPS ACCURACY THRESHOLD** — Locations with GPS Accuracy above this value will be discarded. The range is 5 to 300 metres.
- **OLD LOCATION THRESHOLD** — Locations older than this value will be discarded. The range is 1 to 60 minutes.
- **OLD LOCATION ADJUSTMENT** — Add this to the time that determines if a location is old. The range is 0 to 60 minutes.
- **USE LOCATION RESULTS FROM A NEAR-BY DEVICE** — When tracking results are updated, any nearby devices are identified. When tracking results for those devices are updated, the tracking results of the one originally updated can be used instead. This improves performance since the Waze route time and distance are not requested again.
- **MAXIMUM INTERVAL** — The maximum time between location requests. The range is 15 to 480 minutes.
- **EXIT ZONE INTERVAL** — The time to the first location request after exiting a zone. The range is .5 to 10 minutes.
- **REQUEST MOBILE APP LOCATION INTERVAL** — Send a location request to the Mobile App if there has been no contact after this amount of time. This will check to see if the Mobile App is responding to location requests or is asleep and not running. The range is 15 to 240 minutes.
- **TRACK-FROM-ZONE DISPLAY DISTANCE** — Normally the Home zone's time and distance data is displayed on the Device's `device_tracker` and sensor entities. Display the Track-from-Zone instead when the Device is within this distance of the Track-from-Zone. The range is 1 to 100 km.
- **DEVICE OFFLINE INTERVAL** — Location request interval when offline (Airplane mode, dead cell area, etc.). The range is 5 to 240 minutes.
- **TRAVEL TIME INTERVAL AND NEXT LOCATION UPDATE MULTIPLIER** — This is used to calculate the Interval and Next Location Time when going towards Home. A smaller value will reduce the interval time and increase the location requests; a larger value will increase the interval and reduce the location requests:
    - Shortest Interval Time - 1/4 TravelTime (¼ × 8 mins = Next Locate in 2m)
    - Shorter Interval Time - 1/3 TravelTime (⅓ × 8 mins = Next Locate in 2m40s)
    - Half Way (Default) - 1/2 TravelTime (½ × 8 mins = Next Locate in 4m)
    - Longer Interval Time - 2/3 TravelTime (⅔ × 8 mins = Next Locate in 5m20s)
    - Longest Interval Time - 3/4 TravelTime (¾ × 8 mins = Next Locate in 6m)
- **ACTION COMMANDS** — Save & Return, Menu +

    - ➤ SAVE & RETURN → Update Configuration File, Return to the Previous screen
    - ➤ MENU → Display the Menu screen

### Display Settings & Other Parameters

Selected from Screen - *Menu #2*

- **EVENT LOG ZONE DISPLAY NAME** — How the Zone name is displayed in sensors and the Event Log:
    - HA Zone Friendly Name (Home, Away, TheShores) → PREFERRED
    - HA Zone entity_id (home, not_home, the_shores)
    - iCloud3 reformated Zone entity_id (zone.the_shores → TheShores)
    - iCloud3 reformated Zone entity_id (zone.the_shores → The Shores)
- **DEVICE TRACKER STATE VALUE** — How the device's `device_tracker` entity state value is determined. HA uses the device's gps coordinates to determine the zone. The gps accuracy is not considered so the zone may be exited when the gps wanders out of the zone. iCloud3 does consider the gps accuracy and will not exit the zone when this occurs:
    - iCloud3 Zone - EventLog Zone Display Name (GPS+accuracy) → PREFERRED
    - iCloud3 Zone - Zone Friendly Name (GPS+accuracy)
    - HA Zone - GPS coordinates will determine the zone (except Stationary Zones)
- **TIME FORMAT** — How time fields are displayed in sensors and in the Event Log:
    - 12-hour Time Format (9:05:30a, 4:40:15p)
    - 24-hour Time Format (09:05:30, 16:40:15)
- **UNIT OF MEASUREMENT** — How distance fields are displayed in sensors and in the Event Log:
    - Imperial (mi, ft)
    - Metric (km, m)
- **DISPLAY GPS COORDINATES** — Display GPS-(22.32771, -76.33073/±35m) instead of GPS-/±35m in the Event Log.
- **EVENT LOG SYSTEM OVERRIDES** — Header for the Event Log system override section of the screen. It changes the directory containing the Event Log Custom Card File (`event-log-card.js`) and sets the `Gear` URL for the HA Devices & Svcs → iCloud3 Config screen.
- **PICTURE DIRECTORY FILTER** — Select the directories containing Device image files (.png, .jpg). iCloud3 scans `/www` for all picture files to build a table for selecting the picture for a device. The picture can be hard to find if you have many image files in many directories, so specify the directories with your device image files here.
- **EVENT LOG CARD LOVELACE RESOURCES DIRECTORY** — Event Log custom card `.js` file directory.
- **EVENT LOG CONFIGURE BUTTON (GEAR) URL** — Special URL that displays the HA Configure Settings screen. Normally, this is blank and iCloud3 will determine the URL for its Configure Settings screen. However, if there is a problem caused by running HA in a virtual environment, docker or on another device and the actual URL can not be determined, a 404 not found error may be encountered. If that happens, select it the normal way (HA Devices & Services > Integration > iCloud3 > Configure Settings gear) and copy the URL from the browser into this field.
- **ACTION COMMANDS** — Save & Return, Menu +

    - ➤ SAVE & RETURN → Update Configuration File, Return to the Previous screen
    - ➤ MENU → Display the Menu screen

### Display Location Time Zone when Away

Selected from Screen - *Menu #2*

- **Devices in Away Time Zone #1** — The devices that are in Away Time Zone #1:
    - Not used
    - All are Away and in the same Time Zone
    - *(followed by the iCloud3 device list)*
- **Time & Time Zone Adjustment at Current Location #1** — Primary devices and location time. The current location time when away and in another time zone.
- **Devices in Away Time Zone #2** — The devices that are in Away Time Zone #2:
    - Not used
    - All are Away and in the same Time Zone
    - *(followed by the iCloud3 device list)*
- **Time & Time Zone Adjustment at Current Location #2** — Secondary devices and location time. The current location time when away and in another time zone.
- **ACTION COMMANDS** — Save & Return, Menu +

    - ➤ SAVE & RETURN → Update Configuration File, Return to the Previous screen
    - ➤ MENU → Display the Menu screen

### Event Log 'Display Text As'

Selected from Screen - *Menu #2*

- **TEXT REPLACEMENT FIELDS - [Actual text > Displayed text]** — The text replacement entries. Select the entry to be updated.
- **ACTION COMMANDS** — Next Page Items, Select, Save & Return, Menu +

    - NEXT PAGE ITEMS → Display the text replacement entries on the next page
    - SELECT → Update selected `Display Text As` field
    - ➤ SAVE & RETURN → Update Configuration File, Return to the Previous screen
    - ➤ MENU → Display the Menu screen

### Update Event Log 'Display Text As' Value

Selected from Screen - *Event Log 'Display Text As'*

- **ORIGINAL TEXT** — Text to be replaced, for example `gary_real_email@gmail.com`.
- **DISPLAYED TEXT** — Text to be displayed, for example `gary@email.com`.
- **ACTION COMMANDS** — Clear, Save & Return, Menu +

    - CLEAR → Remove `Display Text As` entry
    - ➤ SAVE & RETURN → Update Configuration File, Return to the Previous screen
    - ➤ MENU → Display the Menu screen

---

## Waze Screens

### Waze - Route Service Travel Time/Distance

Selected from Screen - *Menu #2*

- **WAZE ROUTE SERVICE** — Enable the Waze Route Service. It provides the travel time and distance information from your current location to the Home or another tracked-from zone. This information is used to determine when the next location request should be made.
- **ROUTE SERVER LOCATION** — Location of the Waze Route Server for your area:
    - United States, Canada
    - Israel
    - Rest of the World
- **USE REAL TIME DATA** — Waze should consider traffic delays when determining travel time.
- **WAZE MINIMUM DISTANCE** — Use the Waze Route Service when the zone distance is greater than this value. The range is 0 to 100 km.
- **WAZE MAXIMUM DISTANCE** — Do not use the Waze Route Service when the zone distance is greater than this value. The range is 0 to 1000 km.
- **WAZE HISTORY DATABASE** — Enable the Waze History Database. It stores 'close to zone' travel time and distance information for a GPS location (100m radius). It reduces the number of internet requests to the Waze Servers after it has been in use for a while and speeds up response time when in a poor cell area.
- **GENERAL TRAVEL DIRECTION** — Used to display 'Map Trace Lines' between saved locations:
    - North-South - You generally travel in North-to-South direction
    - East-West - You generally travel in East-West direction
- **HISTORY MAX DISTANCE** — Do not save the Waze travel time and distance to the Waze History Database if the distance is greater than this value. The range is 0 to 1000 km.
- **ACTION COMMANDS** — Save & Return, Menu +

    - ➤ SAVE & RETURN → Update Configuration File, Return to the Previous screen
    - ➤ MENU → Display the Menu screen

---

## Special Zones Screen

### Special Zones

Selected from Screen - *Menu #2*

- **STATIONARY ZONE** — Enable Stationary Zones. A Stationary Zone is automatically created if the device remains in the same location (store, friend's house, doctor's office, etc.) for an extended period of time.
- **FRIENDLY NAME BASE** — Name to display when in a Stationary Zone (StatZone). It is displayed in the Event Log, `device_tracker`, travel direction and zone entities. iCloud3 assigns a number to the Stationary Zone. Use the wildcard character `#` to display this value in the Stationary Zone's name (StatZon1, StatZon2, etc). A 7-letter name leaves room for the name and number to be displayed on iPhone screens without being truncated.
- **NO MOVEMENT TIME** — Time at the same location before moving into a Stationary Zone. The range is 0 to 60 minutes.
- **INZONE INTERVAL** — Time interval between location requests when in a Stationary Zone. The range is 5 to 60 minutes.
- **ENTER ZONE DELAY** — Enable the Enter Zone Delay. You may be driving through a non-tracked zone but not stopping at the zone. The Mobile App issues an Enter Zone trigger when the device enters the zone and changes the `device_tracker` entity state to the Zone. iCloud3 does not process the Enter Zone trigger until the delay time has passed. This prevents processing a Zone Enter trigger that is immediately followed by an Exit Zone trigger.
- **ENTER ZONE DELAY TIME** — Delay processing an Enter Zone Trigger that you may be driving through and not actually entering. The range is 0 to 5 minutes.
- **PRIMARY TRACK-FROM-HOME ZONE OVERRIDE** — Enable the Track-from-Home Zone Override. Normally, the Home zone is used as the primary track-from-zone for the tracking results (travel time, distance, etc). However, a different zone can be used as the base location if you are away from Home for an extended period or the device is normally at another location (vacation house, second home, parent's house, etc.). This is a global setting that overrides the Primary Track-from-Home Zone assigned to an individual Device on the Update Devices screen.
- **TRACK FROM ZONE** — Use this zone instead of Home for tracking results for all devices. This is a global setting. The list contains the HA zones that have been set up.
- **TRACK FROM HOME ZONE** — Keep tracking from the Home zone when the Primary Track From Zone is not Home.
- **ACTION COMMANDS** — Save & Return, Menu +

    - ➤ SAVE & RETURN → Update Configuration File, Return to the Previous screen
    - ➤ MENU → Display the Menu screen

---

## Sensor Screens

### Sensors

Selected from Screen - *Menu #1*

- **MONITORED DEVICE SENSORS** — Select the type of sensors to create for a Monitored Device:
    - _badge → Badge sensor - A badge showing the Zone Name or distance from the Home zone. Attributes include location related information
    - _battery, battery_status → Create Battery (65%) and Battery Status (Charging, Low, etc) sensors (ALWAYS CREATED)
    - Location related sensors → Name, zone, distance, travel_time, etc. (_name, _zone, _zone_fname, _zone_name, _zone_datetime, _home_distance, _travel_time, _travel_time_min, _last_located, _last_update)
- **DEVICE SENSORS** — Device status and information:
    - _name → iCloud3 Device Name
    - _badge → A badge showing the Zone Name or distance from the Home zone
    - _battery, _battery_status → Create Battery Level (65%) and Battery Status (Charging, Low, etc) sensors (ALWAYS CREATED)
    - _info → An information message containing status, alerts and errors related to device location updates, data accuracy, etc
- **LOCATION UPDATE SENSORS** — Device location update times:
    - _interval → Time between location requests
    - _last_update → Last time the location was updated
    - _next_update → Next time the location will be updated (ALWAYS CREATED)
    - _last_located → Last time the device was located using iCloud or Mobile App location
- **TIME SENSORS** — Device tracking timers:
    - _travel_time → Waze Travel time to Home or closest Track-from-Zone zone (ALWAYS CREATED)
    - _travel_time_min → Waze Travel time to Home or closest Track-from-Zone zone in minutes
    - _travel_time_hhmm → Waze Travel time to a Zone in hours:minutes
    - _arrival_time → Home Zone arrival time based on Waze Travel time (ALWAYS CREATED)
- **DISTANCE SENSORS** — Device tracking distances:
    - _home_distance → Distance to the Home zone (ALWAYS CREATED)
    - _zone_distance → Distance to the Home or closest Track-from-Zone zone
    - _dir_of_travel → Direction of Travel for the Home zone or closest Track-from-Zone zone (Towards, AwayFrom, inZone, etc)
    - _moved_distance → Distance moved from the last location
- **TRACK FROM MULTIPLE ZONE SENSORS** — Used when tracking from more than one zone and not needed when tracking only from the Home zone:
    - Include General Sensors (_zone_info)
    - Include Travel Time Sensors (_travel_time, _travel_time_mins, _travel_time_hhmm, _arrival_time)
    - Include Zone Distance Sensors (_zone_distance, _distance, _dir_of_travel)
- **OTHER TRACKING SENSORS** — Not normally used but available:
    - _trigger → Last action that triggered a location update
    - _waze_distance → Waze distance from a TrackFrom zone
    - _calc_distance → Calculated straight line distance from a TrackFrom zone
- **ZONE SENSORS** — Device zone status and information:
    - _zone_fname → HA Zone Name (`Home`, `The Shores`) → From: HA Config → Areas & Zones → Zones → Name field
    - _zone → HA Zone entity_id (`home`, `the_shores`)
    - _zone_name → Reformat the Zone entity_id, capitalize and remove `_`s (`Home`, `TheShores`)
    - _zone_datetime → The time the Device entered the Zone
    - _last_zone_[...] → Create the same sensors for the device's last HA Zone
- **OTHER SENSORS** — Sensors not in the above areas:
    - _gps_accuracy → GPS accuracy of the last location coordinates
    - _vertical_accuracy → Vertical (Elevation) Accuracy
    - _altitude → Altitude/Elevation
- **EXCLUDED SENSORS** — Sensors that will not be created when iCloud3 starts.
- **ACTION COMMANDS** — Exclude Sensors, Set to Default, Save & Return, Menu +

    - EXCLUDE SENSORS → Select specific Sensors that should not be created
    - SET TO DEFAULT → Reset sensors to the default selection
    - ➤ SAVE & RETURN → Update Configuration File, Return to the Previous screen
    - ➤ MENU → Display the Menu screen

The following sensors are always created and can not be deselected:

- _battery, _battery_status → Create Battery Level (65%) and Battery Status (Charging, Low, etc)
- _arrival_time → Home Zone arrival time based on Waze Travel time
- _travel_time → Waze Travel time to Home or closest Track-from-Zone zone
- _home_distance → Distance to the Home zone
- _next_update → Next time the location will be updated

### Exclude Sensors

Selected from Screen - *Sensors*

- **EXCLUDED SENSORS** — Sensors that will not be created when iCloud3 starts.
- **FILTER DISPLAYED SENSORS** — Enter text to select the Sensors that should be displayed, or `all` to display all sensors.
- **ICLOUD3 SENSORS** — A list of Sensors that are created when iCloud3 starts. Select the sensors to be added to the Excluded Sensors list.
- **ACTION COMMANDS** — Filter Sensors, Update List Select More Sensors, Update List Return to Sensor Screen +

    - FILTER SENSORS → Select Sensors that should be displayed
    - UPDATE LIST, SELECT MORE SENSORS → Update the Excluded Sensors List, Select more Sensors to Exclude
    - UPDATE LIST, RETURN TO SENSOR SCREEN → Return to the Sensor screen with the updated Excluded Sensors list

---

## Dashboard Builder Screen

### iCloud3 Dashboard Builder

Selected from Screen - *Menu #1*

- **ICLOUD3 DASHBOARDS** — The iCloud3 Dashboard to be created or updated. The Style Format and Devices fields below specify how the Dashboard's Main View screen will be constructed.
- **MAIN VIEW STYLE FORMAT** — How the device information should be presented:
    - Result Summary - Show Arrival Time, Distance Travel Time, Battery Info
    - Tracking Details - Show all results of a location update
- **MAIN VIEW DEVICES** — Devices to display on the Main view screen. Only 2 devices can be selected:
    - All Devices
    - First 2 iPhones
    - *(followed by the iCloud3 device list)*
- **ACTION COMMANDS** — Create/Update a Dashboard, Menu +

    - CREATE/UPDATE A DASHBOARD → Erase and recreate an existing Dashboard, Create a new Dashboard
    - ➤ MENU → Display the Menu screen. Cancel any unsaved changes

---

## Tools & Maintenance Screens

### Tools

Selected from Screen - *Menu #1*

- **APPLE ACCOUNT TOOLS** — The maintenance tool to be run:
    - CHANGE THE LOG LEVEL → Change the current log level (info, debug, rawdata)
    - CLEANUP HA ENTITY REGISTRY → Extract and Delete iCloud3 Entity Registry Devices and Sensors
    - RESTART ICLOUD3 → Restart iCloud3 Now (Reloads the current version of iCloud3)
    - CLEAR DEVICE'S DATA SOURCE SELECTIONS → Erase the `Apple Acct Device` and `Mobile App Device` selection fields for all iCloud3 devices (Update iCloud3 Device screen)
    - REMOVE ALL APPLE ACCTS & DEVICES → Erase all Apple Accts (Apple Acct and Mobile App screen) and Erase all Devices (iCloud3 Devices screen)
    - RESET GENERAL CONFIGURATION PARAMETERS → Set the `General Parameters` to their default value (Other Parameter Menu screens). Sensors are reset on the Sensors screen.
    - DELETE ALL APPLE/ICLOUD COOKIE FILES → Delete Apple Acct Cookie & Session files in the '.storage/icloud3.apple_acct' directory, Restart HA
    - DELETE ALL ICLOUD3 CONFIGURATION FILES → Delete the iCloud3 Configuration files in the '.storage/icloud3' directory. Apple Accts will be reverified.
    - ➤ MENU → Display the Menu screen
- **(no label)** — Menu +

    - ➤ MENU → Display the Menu screen

### Set Log Level

Selected from Screen - *Tools*

- **LOG LEVEL** — The type of messages (Informational, Debug or RawData from the Apple Account) written to the `iCloud3.log` file:
    - Info - Log General Information and Event Log messages
    - Debug - Info + Other Internal Tracking Monitors
    - Debug (HALog) - Also add log records to the `home-assistant.log` file
    - Debug (AutoReset) - Debug logging that resets to Info at midnight
    - Rawdata - Debug + Device Data (filtered) received from iCloud Location Servers
    - Rawdata (AutoReset) - RawData logging that resets to Info at midnight
    - Rawdata (Unfiltered) - Device Data fields (everything) received from iCloud Location Servers
- **RAWDATA LOG DEVICE FILTER** — Write iCloud Device Data to the log file for only these devices.
- **(no label)** — Save & Return, Menu +

    - ➤ SAVE & RETURN → Update Configuration File, Display the Menu screen
    - ➤ MENU → Display the Menu screen

### Cleanup HA Entity Registry Devices & Sensors

Selected from Screen - *Tools*

- **ACTIVE DEVICES** — Devices that are being tracked by iCloud3. These devices will be deleted and then recreated.
- **INACTIVE DEVICES** — Devices that are set to `Inactive` and not tracked by iCloud3.
- **ORPHANED SENSORS** — Sensors that once existed but are no longer associated with the iCloud3 Integration.
- **DISABLED DEVICES & SENSORS** — Devices and Sensors that have been disabled on the HA Devices, Entity or iCloud3 Integration screen.
- **DELETED DEVICES** — Sensors that were used by a device that has been deleted from iCloud3.
- **DELETED SENSORS** — Sensors that belong to an iCloud3 device that are no longer used.
- **SUFFIX ERRORS** — Sensors that have been duplicated by HA and are now Unavailable (`[sensor]` and `[sensor_2]`).
- **OTHER SENSORS** — Sensors that were not in the other groups.
- **(no label)** — Select or unselect all of the items in the groups above.
- **ACTION COMMANDS** — Delete Selected Device Sensors, Return +

    - DELETE SELECTED DEVICE SENSORS → Remove the selected device sensors from the HA Entity and Device Registry
    - ➤ RETURN → Return to the previous screen

### Confirm Restarting Home Assistant

Selected from Screen - *Add iCloud3 Device* or *Import Apple Devices into iCloud3*

- **ACTION COMMANDS** — Restart Home Assistant, Restart Now, Restart Later +

    - RESTART HOME ASSISTANT → Restart HA & iCloud3
    - RESTART NOW → Restart iCloud3 now to load the updated configuration
    - RESTART LATER → The configuration changes have been saved. Load the updated configuration the next time iCloud3 is started

### Restart Home Assistant or iCloud3

Selected from Screen - *Tools*

- **ACTION COMMANDS** — Restart Home Assistant, Restart iCloud3, Reload iCloud3 +

    - RESTART HOME ASSISTANT → Restart HA & iCloud3
    - RESTART ICLOUD3 → Restart iCloud3 Now
    - RELOAD ICLOUD3 → Reload & Restart iCloud3 (This does not load a new version)

### Confirm Selected Action

Selected from Screen - *Tools* or *iCloud3 Devices*

- **REQUESTED ACTION** — A description of the action that was requested and needs to be confirmed.
- **ACTION COMMANDS** — Yes, No +

    - YES → Complete the requested action
    - NO → Cancel the request

---

## Menu Screens

### Configure Devices & Sensors (Menu #1)

Selected from Screen - *HA Settings → Devices & Services → iCloud3 → Configure*, or *Menu #2*

- **PRIMARY MENU SELECTIONS** — The screen to be displayed:
    - APPLE ACCOUNTS → Add, Change Delete and List Apple Accounts, Import Apple Devices into iCloud3
    - AUTHENTICATE APPLE ACCT SIGN-IN → Authenticate Apple Account access, Request a new Auth Code, Change Authentication Method
    - ICLOUD3 DEVICES → Add, Change, Delete and List Tracked and Monitored Devices, Import Apple Devices into iCloud3
    - SENSORS → Select Sensors created by iCloud3 for all devices, Exclude Specific Sensors
    - DASHBOARD BUILDER → Create a Dashboard that displays iCloud3 device sensor information from prebuilt templates
    - TOOLS → Log Level, Cleanup HA Registry Files, Cleanup/Reset iCloud3 Device Parameters, Apple Acct Cookies & iCloud3 Config File
    - ➤ MENU #2 (PARAMETERS) → Tracking, Sensor Display Parameters, Display Text As, Waze Route Service, Special Zones
    - ➤ EXIT → End the iCloud3 Configure Session
- **ACTION COMMANDS** — Review Inactive Devices, Menu, Exit +

    - REVIEW INACTIVE DEVICES → Some Devices are `Inactive` and will not be located or tracked
    - ➤ MENU → Display the Menu screen
    - ➤ EXIT → End the iCloud3 Configure Session, Return to HA
    - ➤ EXIT → End the iCloud3 Configure Session. Update the Dashboards and Restart
    - ➤ EXIT → End the iCloud3 Configure Session. Add new devices and sensors, Update the Dashboards and Restart

### Configure Parameters (Menu #2)

Selected from Screen - *Menu #1*

- **SECONDARY MENU SELECTIONS** — The screen to be displayed:
    - AWAY TIME ZONE → Change the time displayed in the Event Log to the local time when away from Home
    - TRACKING PARAMETERS → Enable/disable the Mobile App data source, Configure how device location data is verified and displayed
    - DISPLAY SETTINGS & OTHER PARAMETERS → Specify how tracking results are displayed in the Event Log, sensors and device_tracker entities
    - DISPLAY TEXT AS → Event Log Text Replacement
    - WAZE ROUTE DISTANCE, TIME & HISTORY → Specify how the Waze Route Server is used and enable the Waze Tracking History Database
    - SPECIAL ZONES → Configure special zone handling - Delay zone enter triggers, Set up Stationary Zones for non-moving devices, Override the Home zone
    - ➤ MENU #1 (DEVICES & SENSORS) → Apple Account, iCloud3 Devices, Apple Acct Authentication, Sensors, Dashboard Builder, Maintenance Tools
    - ➤ EXIT → End the iCloud3 Configure Session
- **ACTION COMMANDS** — Review Inactive Devices, Menu, Exit +

    - REVIEW INACTIVE DEVICES → Some Devices are `Inactive` and will not be located or tracked
    - ➤ MENU → Display the Menu screen
    - ➤ EXIT → End the iCloud3 Configure Session, Return to HA
    - ➤ EXIT → End the iCloud3 Configure Session. Update the Dashboards and Restart
    - ➤ EXIT → End the iCloud3 Configure Session. Add new devices and sensors, Update the Dashboards and Restart

---

## Event Log Action Screen

These commands are issued from the Event Log Action screen rather than from the Configure
Settings screens.

- **ICLOUD3 CONTROL ACTIONS** — Restart, Pause, Resume +

    - RESTART → Restart iCloud3
    - PAUSE → Pause polling on all devices
    - RESUME → Resume Polling on all devices, Refresh all locations
- **DEBUG LOG ACTIONS** — Start Debug Logging, Stop Debug Logging, Start RawData Logging, Stop RawData Logging, Commit Debug Log Records +

    - START DEBUG LOGGING → Start or stop debug logging
    - STOP DEBUG LOGGING → Start or stop debug logging
    - START RAWDATA LOGGING → Start or stop debug rawdata logging
    - STOP RAWDATA LOGGING → Start or stop debug rawdata logging
    - COMMIT DEBUG LOG RECORDS → Verify all debug log file records are written
- **OTHER COMMANDS** — Export Event Log, Waze Hist Database, Waze Hist Map Track, Restart HA Restart iCloud3, Main Menu +

    - EXPORT EVENT LOG → Export Event Log data
    - WAZE HIST DATABASE → Recalc time/distance data at midnight
    - WAZE HIST MAP TRACK → Load route locations for map display
    - RESTART HA, RESTART ICLOUD3 → Restart HA, Restart iCloud3
    - MAIN MENU → Return to the Main Menu
