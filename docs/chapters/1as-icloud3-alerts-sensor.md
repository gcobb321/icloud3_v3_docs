# iCloud3 Alerts Sensor

*Added in iCloud3 v3.2.3*

Errors and Alerts are displayed in the Event log as they are found and summarized in a green bar at the top of the Event Log. They are prioritized in order of importance:

- Internet Connection Errors
- Apple account authentication is needed
- Apple account configuration and login errors
- Device configuration errors
- Other warnings

![](..\images\icloud3-alerts-evlog.png)

## *icloud3_alerts* Sensor

Alert updates are also added to the *sensor.icloud3_alerts* entity. This sensor entity can be used to notify a device that an error or alert has occurred. 

   - **State Value**: 
        - *none* - No alerts are available
        - The highest priority alert

   - **Attributes**:
        - *alert_count* - Number of alerts (0 if no alerts are available)
        - *updated* - When the alert sensor was updated
        - *message_text* - A text summary of all errors that can be sent to a device using the notify.[devicename] Action.
        - *yourappleacct@* - The Apple account that caused the alert
        - *devicename* - The Device that caused the alert

![](..\images\icloud3-alerts-sensor.png)

## Alert Notifications

Alert notifications can be sent to one of your devices when Home Assistant starts or when a the alerts have been updated. The following examples show:

- Notifications for the state value (highest priority alert)

![](..\images\icloud3-alerts-notify-msg-state.png)

-  Notifications for all alerts (alert *message_text* attribute). Due to space limitations, the HA notify will only list the first 2 alerts.

![](..\images\icloud3-alerts-notify-msg-attrs.png)



##### *iCloud3_Alerts* Notification for the state value (first alert message above)
```
alias: iCloud3 Alerts
description: Send an Alert Msg (All Alerts)
triggers:
  - entity_id:
      - sensor.icloud3_alerts
    for:
      hours: 0
      minutes: 0
      seconds: 0
    trigger: state
    attribute: message_text
  - trigger: homeassistant
    event: start
conditions:
  - condition: numeric_state
    entity_id: sensor.icloud3_alerts
    above: 0
    attribute: alert_count
actions:
  - data_template:
      title: >-
        iCloud3 Alerts ({{ state_attr('sensor.icloud3_alerts', 'alert_count') }}
        Alerts)
      message: "{{ states('sensor.icloud3_alerts') }}"
    action: script.notify_gary_iphone
mode: single

```



##### *iCloud3_Alerts_Attributes* Notification for all alerts (second alert message above)
```
alias: iCloud3 Alerts Attributes
description: Send an Alert Msg (All Alerts)
triggers:
  - entity_id:
      - sensor.icloud3_alerts
    for:
      hours: 0
      minutes: 0
      seconds: 0
    trigger: state
    attribute: message_text
  - trigger: homeassistant
    event: start
conditions:
  - condition: numeric_state
    entity_id: sensor.icloud3_alerts
    above: 0
    attribute: alert_count
actions:
  - data_template:
      title: >-
        iCloud3 Alerts ({{ state_attr('sensor.icloud3_alerts', 'alert_count') }}
        Alerts)
      message: "{{ state_attr('sensor.icloud3_alerts', 'message_text') }}"
    action: script.notify_gary_iphone
mode: single
```



##### Send Message Script
```
alias: Gary - Send Message
sequence:
  - data_template:
      title: "{{ title }}"
      message: "{{ message }}"
    action: notify.mobile_app_gary_iphone_app
mode: single
icon: mdi:message-alert-outline
```

