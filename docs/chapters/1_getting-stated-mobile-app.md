# Using HA Companion Mobile App  for Location Data<!-- {docsify-ignore} -->

iCloud3 monitors the Mobile App device_tracker entity and several sensors for:

- zone enter/exit triggers
- location changes
- battery level updates. 

The sensors are monitored for changed data every 5-seconds. iCloud3 also sends messages to the Mobile App when an error occurs and when a location update from the Mobile App is needed.

## Results of not installing the Mobile App

iCloud3 does not require the Mobile App to be installed on an iPhone or iPad. However, if it is not installed, the following happens:

- iCloud3 will not react to a Zone Enter or Exit events until the phone's *Next Update Event* time. This will delay the device entering a zone or exiting from it.
- Significant location changes will not be available.
- The device's battery level is not available.
- Notifications can not be sent to the device.
- In this case, a short *inZone Interval* will help reduce the time between location updates.

The documentation for the Home Assistant Companion can be found [here](https://companion.home-assistant.io/). It is very extensive and explains how to set it up and use it.  ay particular attention to:
- Setting it up [here](https://companion.home-assistant.io/docs/getting_started/)
- Location [here](https://companion.home-assistant.io/docs/core/location)
- Sensors [here](https://companion.home-assistant.io/docs/core/sensors)
- Notifications [here](https://companion.home-assistant.io/docs/noticationsnotifications-basic)

## The Apple Watch cannot be tracked with the Mobile App

Only iPhones and iPads with the Mobile App installed are monitored. Although there is an HA Complication that can be installed on the Apple Watch, it does not provide location information so it is not monitored. iCloud3 attempts to trigger zone exits by requesting an Apple Account location update when a nearby iPhone or iPad receives a zone exit trigger.

## Add the Mobile App Integration

The Mobile App Integration is added to HA on the Integrations screen. It provides the link between the device itself and the device_tracker and sensor entities on the HA sever. There are a lot of sensor entities created by the Mobile App. iCloud3 monitors the only the _device_tracker_ entity, the _last_update_trigger_ sensor and the _battery_ sensor. The rest can be disabled, hidden or left alone.

## Configure the Mobile App for location updates

The screens below shows the configuration settings for the Mobile App:

![](../images/mobapp-config.png)

## Assign the Mobile App device_tracker to the iCloud3 tracked device

The Mobile App device is assigned to the the iCloud3 tracked device on the *Configure > Update iCloud3 Device* screen, *Mobile App device_tracker entity* field. It is selected from the list of available Mobile App devices.

## The Event Log shows devices that provide location data

When iCloud3 starts, Stage 4 handles setting up the Apple Account and Mobile App devices. The following is done:

- Read all of the devices in the Mobile App integration
- Match them up with the iCloud3 device using the Mobile App device_tracker parameter from the *Update iCloud3 Device* screen
- Errors are identified. This includes missing device_tracker entities, duplicate devices, etc.

The results are shown in the *Event Log > Stage 4* screens. 

![](../images/evlog-stage-4-notes.png)



## Clearing the Mobile App Cache

The cache needs to be cleared when a new version of the Event Log is installed. This does not happen very often, usually when major iCloud3 version is released. A message, with instructions, is displayed when this is needed. It will need to be cleared on every device (iPhones, iPads) that is using the Mobile App. 

1. In the *Home Assistant Companion App*, tap **☰ > HA Settings > Companion App.**
2. Tap **Debugging > Reset front end cache**
3. Tap **Settings > Done**
4. Refresh the screen by pulling down on it until the refresh symbol displays. This will reload the screen and iCloud3 Event Log from the HA server.

