# Apple Account Questions, Issues and Problems {docsify-ignore}



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





