# Apple Account Authentication

When iCloud3 logs in the first time and then about every 90 days, access to your Apple Account needs to be authenticated again. iCloud3 supports three authentication methods:

- **Push notification** - The *Apple Id Sign in Requested... > 6-digit Verification Code* pop-up window 
- **Text Messages** - Sending a text message to your Trusted Phone Numbers - These are set up on your Apple Account. On your iPhone/iPad, go to *Settings App > Your Apple Account > Sign-in & Security > Email & Phone Numbers*. 
- **Security Keys (YubiKey**) - Touching the Security Key, when it is activated, will authenticate the access to your Apple Account.
  - An *Apple Account Sign-on* window is displayed on your iPhone when the key is activated in the Authentication step. You do not need to respond it to complete the authentication. Select the 'OK' option to close the window.
  - The Security Key is inserted into your HA Server, not your iPhone or iPad.

> The following links will provide additional information from Apple Support:
>
> - See [here⧉](https://support.apple.com/en-us/122621) for information about Trusted Devices
> - See [here⧉](https://support.apple.com/guide/mac-help/add-or-remove-trusted-devices-mchl2310b175/mac) for information about Trusted Devices on a Mac
> - See [here⧉](https://support.apple.com/en-us/102637) for information about Security Keys



### Authenticate Apple Account Sign-in screens

The screen below is used to Authenticate Apple Account access and to configure how you want to do it:

![](..\images\apple-acct-auth.png)

- **Request an Authentication Code or Security Key Keypress** - *Step #1* - Start the authentication process. The screens below are displayed. It will untrust your Apple Account and then:

  - **Authentication Code Popup window** - Display *Apple Account Sign in..*. popup window and the code
  - **Text Message** - Sends the text message to the selected Trusted Device
  - **Security Key** - Gets ready for the Authentication step

  ![](C:\Users\Gary\GitHub\icloud3_v3_docs\docs\images\apple-acct-auth-code-hwkey.png)

- **Authenticate** - *Step #2* - Completes the authentication process, what you need to do:

  - **Authentication Code Popup window**, **Text Message**:
    1. Enter the 6-digit code in the Authentication Code field. 
    2. Submit to send to Apple for verification.
  - **Security Key**:
    1. Submit to activate the keypress (it should now be blinking). 
    2. Go to the HA Server and touch the Security Key. If it is not blinking, start over with the Request... step.

- **Change Authentication Method** - This screen is used to select the authentication method to be used. Only active methods are displayed. 

  ![](C:\Users\Gary\GitHub\icloud3_v3_docs\docs\images\apple-acct-auth-change-method.png)

- **Apple Did not Send a Code** - There may be times when the text messages do not arrive or the push notification window is not being sent. This is a work-around, manual way of authenticating access to your account. Follow the instructions on the screen.

  ![](C:\Users\Gary\GitHub\icloud3_v3_docs\docs\images\apple-acct-auth-no-code.png)

#### General Notes:

- **Apple Rejected the Code** - The code is valid for about 15-30 minutes. An error message is displayed if Apple rejects the Verification Code. Reenter it to verify it was not entered incorrectly. It is is still rejected, request a new code.

- **Security Keys** - Security Keys are set up on your iPhone/iPad, go to *Settings App > Your Apple Account > Sign-in & Security > Two-Factor Authentication > Security Keys*. 

