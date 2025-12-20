# Apple Account Authentication

When iCloud3 logs in the first time and about every 2-3 months after that, access to your Apple Account needs to be authenticated. Various notifications are displayed on your Apple devices:

- The *Apple Id Sign in Requested > Don't Allow/Allow* popup window id displayed on the trusted devices.
- An *Apple Account Authentication is Required* message is displayed in the Event Log.
- An alert is sent to your devices by iCloud3.

> See [here⧉](https://support.apple.com/en-us/HT205064) for additional information from Apple Support about your Trusted Devices.

When you select *Allow*, the 6-digit verification code is displayed on your Trusted Devices. This 6-digit verification code is entered on  *Authenticate Apple Account Sign-in* screen. 

![](..\images\apple-acct-auth.png)



- Verify the Apple account needing authentication is displayed in the selecteion list.
- Enter the 6-digit
- Select *Send Code to Apple to Authenticate Sign-in*, then select *Submit*

**Apple Rejected the Code** - The code is valid for about 15-30 minutes. An error message is displayed if Apple rejects the Verification Code. Reenter it to verify it was not entered incorrectly. It is is still rejected, request a new code.

- Select *Request New Code*, then Select Submit.

A new code will be displayed on your device.

1. Display the *Authenticate Apple Account Sign-in* screen. 
2. Verify the Apple Account requesting authentication is displayed, it will show *Authentication Required*. Select it if necessary.
3. Enter the code and select Submit. The code will be sent to Apple.

The code is valid for about 15-minutes. A *Verification Code Accepted* message is displayed if it is accepted by Apple. If the code rejected, request a new code on the same screen. This will display a new *Apple Id Sign in Requested* window on the Trusted with a new code. 


