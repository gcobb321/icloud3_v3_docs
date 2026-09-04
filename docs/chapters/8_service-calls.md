# Device Tracker Services  {docsify-ignore}

Four services are available for the iCloud3 device tracker component that can be used in automations.  These are also requested using *Event Log > Actions*.

- **action** - Send commands to iCloud3 that change the way it is running (pause, resume, restart, etc.)

- **find_iphone_alert** - Display the *Find My iPhone Alert* notification and play an alert sound on the specified phone.

- **lost_device_alert** - Send a message and phone number to a device when it has been lost

- **restart** - Restart iCloud3.

  > The *update* service call introduced in iCloud3 v2 was replaced by the *action* service call. The *update* service call is still available but will be removed in a future release of iCloud3. It is advisable to change any automations and scripts to *action*.


Actions can also be selected on the *HA Sidebar > Tools > Actions* screen.



------
## icloud3.action

This service allows you to change the way iCloud3 operates. The following parameters are used:

| Parameter   | Description                                                  |
| ----------- | ------------------------------------------------------------ |
| command     | The action to be performed (see below). *(Required)*         |
| device_name | Name of the device to be updated. All devices will be updated if this parameter is not specified.  All instances of the device_name are updated if it is in several groups.  *(Optional)* |




The following describe the commands that are available.

| Command_Parameter | Description                                                  |
| ----------------- | ------------------------------------------------------------ |
| pause             | Stop updating/locating a device (or all devices). Note: You may want to pause location updates for a device if you are a long way from home or out of the country and it doesn't make sense to continue locating your device. |
| resume            | Start updating/locating a device (or all devices) after it has been paused. |
| restart           | Restart the iCloud3 custom component.                        |
| locate interval   | Locate the device or all devices based on the following *locate interval* parameters:<br><br>`- no interval parameter` - Locate the device using the iCloud Location Services immediately<br>`- mobapp` - Send a location request to the Mobile App associated with the device.<br>`- interval time` - Set the *Next Location Time* to the *current time + the interval time*<br><br>Examples:<br>`- locate`<br>`- locate mobapp`<br>`- locate 30 secs`<br>`- locate 15 mins`<br>`- locate 2 hrs` |

#### Operational Automations (Restart, Pause, Resume)

  - ```
    alias: iCloud3 Restart
    triggers: []
    conditions: []
    actions:
      - action: icloud3.action
        data:
          command: restart
    mode: single
    ```
  - ```
    alias: iCloud3 Pause
    triggers: []
    conditions: []
    actions:
      - action: icloud3.action
        data:
          command: pause
    mode: single
    ```
  - ```
    alias: iCloud3 Pause (Gary)
    triggers: []
    conditions: []
    actions:
      - action: icloud3.action
        data:
          command: pause
          device_name: gary_iphone
    mode: single
    ```
  - ```
    alias: iCloud3 Resume (Gary)
    triggers: []
    conditions: []
    actions:
      - action: icloud3.action
        data:
          command: resume
          device_name: gary_iphone
    mode: single
    ```
------
#### Locate Devices Automations (locate, locate mobapp)

  - ```
    alias: iCloud3 Locate (Gary)
    triggers: []
    conditions: []
    actions:
      - action: icloud3.action
        data:
          command: locate
          device_name: gary_iphone
    mode: single
    ```
  - ```
    alias: iCloud3 Locate (Gary-Mobile APP)
    triggers: []
    conditions: []
    actions:
      - action: icloud3.action
        data:
          command: locate mobapp
          device_name: gary_iphone
    mode: single
    ```
  - ```
    alias: iCloud3 Locate (All Devices)
    triggers: []
    conditions: []
    actions:
      - action: icloud3.action
        data:
          command: locate
    mode: single
    ```
  - ```
    alias: iCloud3 Locate (All Devices 15-secs)
    triggers: []
    conditions: []
    actions:
      - action: icloud3.action
        data:
          command: locate 15 secs
    mode: single
    ```
  - ```
    alias: iCloud3 Locate (Gary 30-mins)
    triggers: []
    conditions: []
    actions:
      - action: icloud3.action
        data:
          command: locate 30 mins
          device_name: gary_iphone
    mode: single
    ```



------
##  icloud3.find_iphone_alert

This service will display a notification and play on the specified device based on the tracking method:

- Family Sharing - Display the alert using Apple's Find My iPhone Alert method.
- Mobile App - Send a notification with sound to the Mobile App.

| Parameter   | Description                     |
| ----------- | ------------------------------- |
| device_name | Name of the device *(Required)* |

```yaml
alias: Gary - Find Phone Alert
triggers: []
conditions: []
actions:
  - action: icloud3.find_iphone_alert
    data:
      device_name: gary_iphone
  - action: script.notify_gary_iphone
    data:
      title: 'Find iPhone Alert'
      message: 'Find iPhone Alert was triggered for Gary (gary_iphone)'
mode: single
```



------
## icloud3.lost_device_alert

This service will send a notification to the specified device that the device has been lost and to call the phone number in the message:

- Family Sharing - Display the alert using the Find My iPhone Alert process build into Mobile.
- Mobile App - Send a notification with sound to the Mobile App on the specified device .

| Parameter   | Description                                                  |
| ----------- | ------------------------------------------------------------ |
| device_name | Name of the device *(Required)*                              |
| number      | Phone number to call *(Required)*                            |
| message     | A message that will be displayed on the locked screen *(Required)* |

```yaml
alias: Gary - Lost Device Alert
triggers: []
conditions: []
actions:
  - action: icloud3.lost_device_alert
    data:
      device_name: gary_iphone
      number: '123-456-7890'
      message: 'This Phone has been lost. Please call this number to report it found.'
  - action: script.notify_gary_iphone
    data:
      title: 'Lost Device Alert'
      message: 'The Lost Device Alert message has been sent to Gary (gary_iphone)'
mode: single
```



------
## icloud3.restart

This service restarts iCloud3 and refreshes all of the devices that are tracked by iCloud3.

```yaml
alias: iCloud3 Restart
triggers: []
conditions: []
actions:
  - action: icloud3.restart
    data: {}
mode: single
```
