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



-----

## Login email from Apple

An email is sent from Apple when you log into your your iCloud account using your password. You will receive this email:

- When you are setting up iCloud3 and you login the first time
- Every time the password is used to log into your account. This may be several times or more during the day.

!> You will receive a number of these emails from Apple each day while iCloud3 is tracking your devices. The number you receive is determined by Apple, iCloud3 can not do anything about this.  iCloud3 minimizes the number you receive as best it can by using tokens first and only logging in when Apple requests one.

![](..\images\apple-acct-auth-email.png)

####  What can you do to minimize these emails from clogging up your inbox

The short answer is not much. 

I have set up a gmail filter that detects the email from Apple, marks it as read, bypasses the inbox and puts it in a special Apple email folder. Some have said they are concerned about someone hacking into their Apple account, they will not know about it and do not want to use these automatic filters. A valid concern but this works for me. I would welcome any other suggestions I might add to this User Guide to help others deal with this problem.

#### Monitoring the emails from Apple

Although the chance of someone else successfully logging into your Apple Account is almost impossible, especially where 2fa is now required, you may want to review the times iCloud3 logs in with your password and compare these logins with the email you receive. 

1. Select *Event Log > Actions > Show Startup Logs, Errors and Alerts*. 

   Scroll through the items for an entry similar to this. Logins during the startup process are in the Stage 4 area while logins during normal tracking are shown near the top of the list. 

   ![](..\images\apple-acct-auth-evlog-password-msg.png)

2. Refresh the Event Log or select a device to redisplay the tracking screen.

