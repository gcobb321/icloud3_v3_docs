# Apple Account, iCloud3 Devices and Sensor Questions, Issues and Problems {docsify-ignore}



## Apple Account Questions

+ Can I use an *App Specific Password* instead of my real password +

  No. App Specific Passwords are not supported by iCloud3. iCloud3 is a program running on a computer, not an app running on an iDevice. It uses web service calls to request the location of the devices in the iCloud's Family Sharing List. Apps running on iDevices use a different access method that is not available by programs. This is discussed further in the _Apple Accounts_ section.



+ Can I use a Hardware Security Key instead of my iCloud account password +

  Not at the present time but it is under development. See the *Apple Accounts*  section for more information.





-----
## Apple Account Issues and Problems

+ I cannot log into my Apple account, should I delete the *.storage/icloud3.apple_acct* cookie files +

  No, you should not. It will not hurt anything but it does not help anything either. In fact, when you request a new code on the *Authenticate Apple Account Sign-in* screen, iCloud3 deletes the *session* files which causes Apple to reauthenticate the account and display a new verification code.

  

+ I keep getting a notification that a verification code is needed +

  Apple notifies iCloud3 that a reauthentication code is needed to continue accessing the iCloud account. You need go through *Authenticate Apple Account Signin* to enter the 6-digit verification code that is displayed on one of your trusted devices. 

  

+ I do not know the verification code, I can not enter the code right now, the alert was displayed on another device +

  The Authenticate Apple Account Sign-in message will continue to appear until the code is entered. Although, Apple will continue to provide location information for a while, it  will eventually stop iCloud3 from accessing your iCloud account until it is entered.

  
  
+ Will Apple stop asking for the code if I restart Home Assistant or delete and reinstall iCloud3 Integration +

  No, Apple requires that access to your iCloud account is only done from an authorized device that has been verified. iCloud3 must comply with this request and provide a valid 6-digit verification code. When you restart Home Assistant or reinstall the iCloud3 Integration, Apple will just keep asking for the verification code. 





-----

## Sensor Issues and Problems

+ My Sensors are no longer available +

  The entity_id for iCloud3 sensors are assigned by HA when iCloud3 starts. The entity ids on the dashboard screens follow the format of [devicename]_[entity_id] (*gary_iphone_zone_distance*). If HA detects that the entity id already exists in the HA entity registry file *(.storage/core.entity_registry*), HA will assign a suffix to it to make it unique (*gary_iphone_zone_distance_2*). iCloud3 will update the *_2* entity, not the one on the dashboard resulting in an *unavailable* value.

  Try the following to remove the sensors with the *_2* suffix and correct this problem:

  1. Go to *Configure > Tools*
  
  2. Select *Repair '_2' Sensor Entity Name Errors*
  
  3. Restart HA
  
  If this does not fix the problem, see the question describing how to recreate all iCloud3 entities.





+ How do I remove and recreate all iCloud3 Sensor Entities +

  There may be times when HA has unassociated the iCloud3 sensors entities from iCloud3. This can be corrected by removing all of the iCloud3 entities from the HA entity registry. They will be recreated when HA and iCloud3 restarts.

  Do the following:

  1. Backup all HA files.
  2. Go to *Settings > Devices & Services > Integrations*. 
  3. Disable iCloud3 - Click the 3-dots to the right of the configure gear icon to open the drop down action window. Select *Disable*
  4. Restart HA
  5. Restart HA again to make sure the HA caches have been cleared
  6. Go to *Settings > Devices and Services > Entities*. The *Status* column will display a 'red reset/info icon' for all unused sensors. This will include all entities with iCloud3, since it is disabled, and any others that are no longer assigned to a previously installed integration.
  7. Click the *Enter Selection Mode* icon to the right of the *Filters* item at the top. A check box will be displayed next to each entity item
  8. Click the *Master Checkbox* in the heading line at the top to select all entities
  9. Click the 3-dots in the upper right corner of the screen to open a drop down window. Select *Delete Selected*. This will delete all entities associated with iCloud3 since it is disabled. It will not delete entities tied to an active device or  integration.
  10. Confirm deleting these items
  11. Restart HA
  12. Go back to *Settings > Devices and Services > Integrations*. 
  13. Enable iCloud3 - Click the 3-dots to the right of the configure gear icon to open the drop down action window. Select *Enable*
  14. Restart HA. This should recreate all the iCloud3 devices and sensors.

  

  ### Spook

  If you get HA errors related to iCloud3 sensors can not be created or another error related to entity registry problems, check out the custom component *Spook* on HACS. It is a tool for fixing various entity registry errors written by Frenck, one of the HA developers, to fix entity and registry problems.

  - **Gemini's description** - HA (Home Assistant) custom component "Spook" is a powerful, unofficial toolbox by developer Frank that adds missing features, cleans up unused entities, and provides advanced actions (like entity management, blueprint import, or cloud monitoring) via new services and entities, installed through [HACS](https://www.google.com/search?q=HACS&sca_esv=1307f981479751f5&sxsrf=ANbL-n42ioipAGxVnI-OQwCb4QXaoqhAjQ%3A1767981168832&source=hp&ei=cEBhafHGMNeLwbkPooKuuAk&iflsig=AFdpzrgAAAAAaWFOgEQVegHfORRTREJpp6xEYz3arkE1&ved=2ahUKEwicnuCRg_-RAxVZmYQIHdkQBhcQgK4QegQIARAC&uact=5&oq=ha+custom+component+spook&gs_lp=Egdnd3Mtd2l6IhloYSBjdXN0b20gY29tcG9uZW50IHNwb29rMgUQIRigATIFECEYoAEyBRAhGKABMgUQIRigATIFECEYoAFItDhQAFikMXAAeACQAQCYAaQBoAGOFaoBBDkuMTa4AQPIAQD4AQGYAhmgAtcVwgIKECMYgAQYigUYJ8ICBBAjGCfCAg4QLhiABBixAxjHARjRA8ICCxAuGIAEGLEDGIMBwgILEAAYgAQYsQMYgwHCAg4QLhiABBiKBRixAxiDAcICBBAAGAPCAgUQABiABMICCxAuGIMBGLEDGIAEwgIIEC4YgAQYsQPCAggQABiABBixA8ICCxAuGK8BGMcBGIAEwgIFEC4YgATCAgcQABiABBgKwgILEAAYgAQYigUYhgPCAggQABiABBiiBMICBRAAGO8FwgIGEAAYFhgewgIIEAAYiQUYogTCAggQABgWGB4YCsICBRAhGKsCmAMAkgcENi4xOaAHlqABsgcENi4xObgH1xXCBwYzLjIwLjLIBy6ACAE&sclient=gws-wiz&mstk=AUtExfDcuRBuCYlE5ukKQ8PDNrOvTIKdhl3BUJ5SejyEARcYTHua5v0-nF07z3K1_seF0UHQll1DsKq75kKIMUBkk1cU8MDPJoH7gkHPsIXCjCDuDgB9H2N4jt4Tc0AEsWyaO_SNT9bykbLwak_9LkCG22c3avclUJGo9fCmof7_8o0afjk&csui=3) to enhance existing integrations and find issues in the [Repairs Dashboard](https://www.google.com/search?q=Repairs+Dashboard&sca_esv=1307f981479751f5&sxsrf=ANbL-n42ioipAGxVnI-OQwCb4QXaoqhAjQ%3A1767981168832&source=hp&ei=cEBhafHGMNeLwbkPooKuuAk&iflsig=AFdpzrgAAAAAaWFOgEQVegHfORRTREJpp6xEYz3arkE1&ved=2ahUKEwicnuCRg_-RAxVZmYQIHdkQBhcQgK4QegQIARAD&uact=5&oq=ha+custom+component+spook&gs_lp=Egdnd3Mtd2l6IhloYSBjdXN0b20gY29tcG9uZW50IHNwb29rMgUQIRigATIFECEYoAEyBRAhGKABMgUQIRigATIFECEYoAFItDhQAFikMXAAeACQAQCYAaQBoAGOFaoBBDkuMTa4AQPIAQD4AQGYAhmgAtcVwgIKECMYgAQYigUYJ8ICBBAjGCfCAg4QLhiABBixAxjHARjRA8ICCxAuGIAEGLEDGIMBwgILEAAYgAQYsQMYgwHCAg4QLhiABBiKBRixAxiDAcICBBAAGAPCAgUQABiABMICCxAuGIMBGLEDGIAEwgIIEC4YgAQYsQPCAggQABiABBixA8ICCxAuGK8BGMcBGIAEwgIFEC4YgATCAgcQABiABBgKwgILEAAYgAQYigUYhgPCAggQABiABBiiBMICBRAAGO8FwgIGEAAYFhgewgIIEAAYiQUYogTCAggQABgWGB4YCsICBRAhGKsCmAMAkgcENi4xOaAHlqABsgcENi4xObgH1xXCBwYzLjIwLjLIBy6ACAE&sclient=gws-wiz&mstk=AUtExfDcuRBuCYlE5ukKQ8PDNrOvTIKdhl3BUJ5SejyEARcYTHua5v0-nF07z3K1_seF0UHQll1DsKq75kKIMUBkk1cU8MDPJoH7gkHPsIXCjCDuDgB9H2N4jt4Tc0AEsWyaO_SNT9bykbLwak_9LkCG22c3avclUJGo9fCmof7_8o0afjk&csui=3). It's known for filling gaps not covered by official HA Core, offering features like deleting orphaned entities, managing devices/areas, and adding random services, but requires careful use and a backup beforehand due to its use of undocumented APIs. 

  - **More Information about Spook** - Find more information about Spook [here](https://community.home-assistant.io/t/spook-your-homie/539588) and [here](https://github.com/frenck/spook?tab=readme-ov-file). The *Spook Getting Started* page is [here](https://spook.boo/) and [here](https://spook.boo/about/).

  

  

  



