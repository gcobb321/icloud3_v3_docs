## iCloud3 User Guide Index  {docsify-ignore-all}

------
### Getting Started

#### [Introducing iCloud3](chapters/0.1-introduction.md)

- [iCloud3 v3 Highlights](chapters/0.1-introduction?id=icloud3-v3-highlights)
- [Information screens showing tracking information](chapters/0.1-introduction?id=information-screens-showing-tracking-information)
- [iCloud3 Documentation](chapters/0.1-introduction?id=icloud3-documentation)
- [Installing iCloud3](chapters/0.1-introduction?id=installing-icloud3)

#### [v3 Changes and New Features](chapters/0.2-change-log-v3.md)

- [iCloud3 is now a Home Assistant Integration](chapters/0.2-change-log-v3?id=icloud3-is-now-a-home-assistant-integration)
- [Event Log card](chapters/0.2-change-log-v3?id=event-log-card)
- [Track from more than one zone](chapters/0.2-change-log-v3?id=track-from-more-than-one-zone)
- [Starting iCloud3](chapters/0.2-change-log-v3?id=starting-icloud3)
- [Waze History Database](chapters/0.2-change-log-v3?id=waze-history-database)
- [Other New or Enhanced Features](chapters/0.2-change-log-v3?id=other-new-or-enhanced-features)
- [Breaking Changes - The following items have been changed or removed](chapters/0.2-change-log-v3?id=breaking-changes-the-following-items-have-been-changed-or-removed)




------
### iCloud3 Components

#### [Tracking Results screen](chapters/1.1-tracking-results-screen.md)

- [Overview of the Tracking Results screen](chapters/1.1-tracking-results-screen?id=overview-of-the-tracking-results-screen)
- [Creating the Tracking Results screen (Lovelace yaml Code)](chapters/1.1-tracking-results-screen?id=creating-the-tracking-results-screen-lovelace-yaml-code)

#### [Event Log](chapters/1.2-event-log.md)
- [About the Event Log](chapters/1.2-event-log.md)
- [Quick Link Icons](chapters/1.2-event-log?id=quick-link-icons)
- [Actions](chapters/1.2-event-log?id=actions)
- [Creating the Event Log screen](chapters/1.2-event-log?id=creating-the-event-log-screen)
- [Lovelace Resource for the Event Log](chapters/2.3-mobile-app?id=assigning-the-mobile-app-device)
  - [Using another custom card directory](chapters/1.2-event-log?id=using-another-custom-card-directory)
- [Event Log During Startup](chapters/1.2-event-log?id=event-log-during-startup)
  - [Stage 1 - Initial Preparation](chapters/1.2-event-log?id=stage-1-initial-preparation)
  - [Stage 2 - Prepare Support Services](chapters/1.2-event-log?id=stage-2-prepare-support-services)
  - [Stage 3 - Prepare Configured Devices](chapters/1.2-event-log?id=stage-3-prepare-configured-devices)
  - [Stage 4 - Setup iCloud & Mobile App Tracking Methods](chapters/1.2-event-log?id=stage-4-setup-icloud-amp-mobile-app-tracking-methods)
  - [Stage 5 - Configure Tracked Devices](chapters/1.2-event-log?id=stage-5-configure-tracked-devices)

#### [Configure iCloud3 Settings](chapters/1.3-configure-settings.md)

- [Opening the Configure Settings screens](chapters/1.3-configure-settings?id=opening-the-configure-settings-screens)
- [Main Menu screens](chapters/1.3-configure-settings?id=main-menu-screens)
- [Typical Configure Settings screens](chapters/1.3-configure-settings?id=typical-configure-settings-screens)
  - [Update Tracked Device screen](chapters/1.3-configure-settings?id=update-tracked-device-screen)
  - [Format Settings screen](chapters/1.3-configure-settings?id=format-settings-screen)


------
### Location Data Sources

#### [iCloud Account Family Sharing Devices](chapters/2.1-icloud-account.md)

- [iCloud Account Family Sharing Devices (FamShr)](chapters/2.1-icloud-account?id=icloud-account-family-sharing-devices-famshr)
  - [Configuring the iCloud Account as a Data Source](chapters/2.1-icloud-account?id=configuring-the-icloud-account-as-a-data-source)
    - [Changing the iCloud Account](chapters/2.1-icloud-account?id=changing-the-icloud-account)
  - [Assigning the Family Sharing Device](chapters/2.1-icloud-account?id=assigning-the-family-sharing-device)
  - [Tracking an Apple Watch](chapters/2.1-icloud-account?id=tracking-an-apple-watch)
  - [Tracking AirTags](chapters/2.1-icloud-account?id=tracking-airtags)
  - [Event Log Family Share Information When iCloud3 Starts](chapters/2.1-icloud-account?id=event-log-family-share-information-when-icloud3-starts)
  - [Upgrading to a new Device (Ex.: iPhone 13 to iPhone 14)](chapters/2.1-icloud-account?id=upgrading-to-a-new-device-ex-iphone-13-to-iphone-14)

#### [Authenticating Apple iCloud Account Access]((chapters/2.2-apple-id-verification.md))

- [Apple Notification windows](chapters/2.2-apple-id-verification?id=apple-notification-windows)
- [Displaying the Apple ID Verification Code screen](chapters/2.2-apple-id-verification?id=displaying-the-apple-id-verification-code-screen)
- [Entering the Apple ID Verification Code](chapters/2.2-apple-id-verification?id=entering-the-apple-id-verification-code)
- [Requesting a New Verification Code](chapters/2.2-apple-id-verification?id=requesting-a-new-verification-code)
- [Access tokens, password and security](chapters/2.2-apple-id-verification?id=access-tokens-password-and-security)
- [Login email Notification from Apple](chapters/2.3-mobile-app?id=configuring-the-mobile-app-as-a-data-source)
  - [What can you do to minimize these emails from clogging up your inbox](chapters/2.2-apple-id-verification?id=what-can-you-do-to-minimize-these-emails-from-clogging-up-your-inbox)

#### [Mobile App Integration, Mobile App Entities)](chapters/2.3-mobile-app.md)

- [Configuring the Mobile App as a Data Source](chapters/2.3-mobile-app?id=configuring-the-mobile-app-as-a-data-source)
    - [Enable HA Mobile Companion App data usage](chapters/2.3-mobile-app?id=enable-ha-mobile-companion-app-data-usage)

- [Assigning the Mobile App Device](chapters/2.3-mobile-app?id=assigning-the-mobile-app-device)
    - [If the Mobile App is not Installed](chapters/2.3-mobile-app?id=if-the-mobile-app-is-not-installed)
- [Using the Mobile App with the Apple Watch](chapters/2.3-mobile-app?id=using-the-mobile-app-with-the-apple-watch)
- [Event Log Family Share Information When iCloud3 Starts](chapters/2.3-mobile-app?id=event-log-family-share-information-when-icloud3-starts)
- [Install and Configure the Mobile App](chapters/2.3-mobile-app?id=install-and-configure-the-mobile-app)
- [Clearing the Mobile App Cache](chapters/2.3-mobile-app?id=clearing-the-mobile-app-cache)



------
### Installing iCloud3
#### [Migrating from v2 to v3](chapters/3.1-migrating-v2-to-v3.md)

- [Upgrading to iCloud3 v3](chapters/3.1-migrating-v2-to-v3?id=upgrading-to-icloud3-v3)
  - [Generally, you will do the following:](chapters/3.1-migrating-v2-to-v3?id=generally-you-will-do-the-following)
- [Step #1 - Install iCloud3 v3](chapters/3.2-installing-and-configuring?id=clearing-the-browser39s-cache)
  - [Easy Way - Use HACS](chapters/3.1-migrating-v2-to-v3?id=easy-way-use-hacs)
  - [Hard Way (but not too hard) - Manual Installation](chapters/3.1-migrating-v2-to-v3?id=hard-way-but-not-too-hard-manual-installation)
- [Step #2 - Add the iCloud3 Integration and Verify the Configuration](chapters/3.1-migrating-v2-to-v3?id=step-2-add-the-icloud3-integration-and-verify-the-configuration)
- [Step 3 - Review the Parameter Migration Results](chapters/3.2-installing-and-configuring?id=clearing-the-browser39s-cache)
  - [Step #3.1 - The *iCloud Account & Mobile App* screen](chapters/3.2-installing-and-configuring?id=step-3-add-the-icloud3-integration-and-open-configure-settings)
    - [Enable Family Sharing data usage](chapters/3.1-migrating-v2-to-v3?id=enable-family-sharing-data-usage)
    - [Enable HA Mobile Companion App data usage](chapters/3.1-migrating-v2-to-v3?id=enable-ha-mobile-companion-app-data-usage)
    - [iCloud Account Authentication](chapters/3.1-migrating-v2-to-v3?id=icloud-account-authentication)
  - [Step #3.2 - The *iCloud3 Devices* screen](chapters/3.1-migrating-v2-to-v3?id=step-32-the-icloud3-devices-screen)
  - [Step #3.3 - The *Update Tracked iCloud3 Device* screen](chapters/3.1-migrating-v2-to-v3?id=step-33-the-update-tracked-icloud3-device-screen)
  - [Step #3.4 - The *Sensors* selection screen](chapters/3.1-migrating-v2-to-v3?id=step-34-the-sensors-selection-screen)
- [Step #4 - Exit *The Configuration Wizard* and Restart iCloud3](chapters/3.1-migrating-v2-to-v3?id=step-4-exit-the-configuration-wizard-and-restart-icloud3)
- [Step #5 - Clear the Browsers Cache](chapters/3.2-installing-and-configuring?id=step-5-set-up-a-lovelace-card-tracking-card)
  - - [Clear the Browser's Cache (Chrome, Edge, Safari, MacOS)](chapters/3.1-migrating-v2-to-v3?id=clear-the-browser39s-cache-chrome-edge-safari-macos)
    - [Clear the Home Assistant Companion (Mobile App) Cache](chapters/3.1-migrating-v2-to-v3?id=clear-the-home-assistant-companion-mobile-app-cache)
- [Step #6 - Restart Home Assistant (if necessary)](chapters/3.1-migrating-v2-to-v3?id=step-6-restart-home-assistant-if-necessary)
- [Step #7 - Review the *Configuration Screens & Parameters* chapter](chapters/3.1-migrating-v2-to-v3?id=step-7-review-the-configuration-screens-amp-parameters-chapter)
- [iCloud3 Debug Log](chapters/3.1-migrating-v2-to-v3?id=icloud3-debug-log)

#### [As a New Installation](chapters/3.2-installing-and-configuring.md)

- [Step #1 - Install iCloud3](chapters/3.2-installing-and-configuring?id=step-1-install-icloud3)
- [Step #2 - Install the Mobile App on your iPhone or iPad](chapters/3.2-installing-and-configuring?id=step-2-install-the-mobile-app-on-your-iphone-or-ipad)
- [Step #3 - Add the iCloud3 Integration and open *Configure Settings*](chapters/3.2-installing-and-configuring?id=step-3-add-the-icloud3-integration-and-open-configure-settings)
  - [Step #3.1 - iCloud Account & Mobile App screen](chapters/3.2-installing-and-configuring?id=step-31-icloud-account-amp-mobile-app-screen)
  - [Step #3.2 - iCloud3 Devices screen](chapters/3.2-installing-and-configuring?id=step-32-icloud3-devices-screen)
  - [Step #3.3 - Add Tracked iCloud3 Device screen](chapters/3.2-installing-and-configuring?id=step-33-add-tracked-icloud3-device-screen)
  - [Step #3.4 - Update Tracked iCloud3 Device screen](chapters/3.2-installing-and-configuring?id=step-34-update-tracked-icloud3-device-screen)
- [Step #4 - Exit the *Configure Settings* screens and Restart iCloud3](chapters/3.2-installing-and-configuring?id=step-3-add-the-icloud3-integration-and-open-configure-settings)
  - [The Other Configuration Screens](chapters/3.2-installing-and-configuring?id=the-other-configuration-screens)
- [Step #5 - Set up a Lovelace card tracking card](chapters/3.2-installing-and-configuring?id=step-5-set-up-a-lovelace-card-tracking-card)
  - [Step 5.1 - Create the Lovelace iCloud3 Dashboard](chapters/3.2-installing-and-configuring?id=step-51-create-the-lovelace-icloud3-dashboard)
  - [Step 5.2 - Create the device tracking portion of the lovelace screen](chapters/3.2-installing-and-configuring?id=step-52-create-the-device-tracking-portion-of-the-lovelace-screen)
  - [Step 5.3 - Create the Event Log portion of the Lovelace screen](chapters/3.2-installing-and-configuring?id=step-53-create-the-event-log-portion-of-the-lovelace-screen)
  - [Step 5.4 - Set up the *icloud3-event-log-card* Lovelace Resource (if needed)](chapters/3.2-installing-and-configuring?id=step-54-set-up-the-icloud3-event-log-card-lovelace-resource-if-needed)
- [Congratulations, iCloud3 is set up](chapters/3.2-installing-and-configuring?id=congratulations-icloud3-is-set-up)
- [Installation Notes](chapters/3.2-installing-and-configuring?id=installation-notes)
- [Restart Home Assistant (if necessary)](chapters/3.2-installing-and-configuring?id=restart-home-assistant-if-necessary)
- [Clearing the Browser's Cache](chapters/3.2-installing-and-configuring?id=clearing-the-browser39s-cache)
  - [Clear the Browser's Cache (Chrome, Edge, Safari, MacOS)](chapters/3.2-installing-and-configuring?id=clear-the-browser39s-cache-chrome-edge-safari-macos)
  - [Clear the Home Assistant Companion (Mobile App) Cache](chapters/3.2-installing-and-configuring?id=clear-the-home-assistant-companion-mobile-app-cache)
- [iCloud3 Log File](chapters/3.2-installing-and-configuring?id=icloud3-log-file)

------
#### Reference

#### [Configuration Screens & Parameters](chapters/7.1-config-parms.md)

- [Data Sources - iCloud Account & Mobile App](chapters/7.1-config-parms?id=data-sources-icloud-account-amp-mobile-app)
- [Enter/Request an Apple ID Verification Code](chapters/7.1-config-parms?id=enterrequest-an-apple-id-verification-code)
	- [Apple Account Reauthentication Process](chapters/7.1-config-parms?id=apple-account-reauthentication-process)
- [Update iCloud3 Devices](chapters/7.1-config-parms?id=update-icloud3-devices)
	- [Add Device](chapters/7.1-config-parms?id=add-device)
	- [Delete Device](chapters/7.1-config-parms?id=delete-device)
	- [Change Device Order screen](chapters/7.1-config-parms?id=change-device-order-screen)
- [Update Tracked iCloud3 Device](chapters/7.1-config-parms?id=update-tracked-icloud3-device)
- [Sensors](chapters/7.1-config-parms?id=sensors)
	- [Exclude Sensors screen](chapters/7.1-config-parms?id=exclude-sensors-screen)
- [Format Settings screen](chapters/7.1-config-parms?id=format-settings-screen)
- [Action Commands](chapters/7.1-config-parms?id=action-commands)
- [Display Text-as](chapters/7.1-config-parms?id=display-text-as)
- [Waze Route Distance & Time, Waze History Database](chapters/7.1-config-parms?id=waze-route-distance-amp-time-waze-history-database)
	- [Waze Location Map Display](chapters/7.1-config-parms?id=waze-location-map-display)
- [inZone Intervals](chapters/7.1-config-parms?id=inzone-intervals)
- [Special Zones](chapters/7.1-config-parms?id=special-zones)
  - [Enter Zone Delay](chapters/7.1-config-parms?id=enter-zone-delay)
  - [Stationary Zone](chapters/7.1-config-parms?id=stationary-zone)
  - [Primary Base Zone](chapters/7.1-config-parms?id=primary-base-zone)
- [Tracking & Other Parameters](chapters/7.1-config-parms?id=tracking-amp-other-parameters)



------

#### [Other iCloud3 Features](chapters/7.2-other-topics.md)

- [Startup & Device Alerts](chapters/7.6-alerts.md)
- [Tracking From More Than One Zone](chapters/7.2-other-topics?id=tracking-from-more-than-one-zone)
- [Log Zone Activity for Expense Reports or Zone Tracking](chapters/7.2-other-topics?id=log-zone-activity-for-expense-reports-or-zone-tracking)
- [Display the Waze History Locations on a Map Card](chapters/7.2-other-topics?id=display-the-waze-history-locations-on-a-map-card)
  - [How to Remove the Lines Between the Locations](chapters/7.2-other-topics?id=how-to-remove-the-lines-between-the-locations)
  - [Loading the saved locations](chapters/7.2-other-topics?id=loading-the-saved-locations)



------

#### [Sensor Attributes](chapters/7.3-attributes.md)

- [Device Tracking Attributes](chapters/7.3-attributes?id=device-tracker-attributes)
- [Attributes for Different Sensor Types](chapters/7.3-attributes?id=sensor-attributes)



------

#### [Service Calls](chapters/7.4-service-calls.md)

- [Device Tracker Services](chapters/7.4-service-calls?id=device-tracker-services)
- [icloud3.action](chapters/7.4-service-calls?id=icloud3action)
    - [Operational Automations (Restart, Pause, Resume)](chapters/7.4-service-calls?id=operational-automations-restart-pause-resume)
    - [Locate Devices Automations (locate, locate mobileapp)](chapters/7.4-service-calls?id=locate-devices-automations-locate-locate-mobileapp)
- [icloud3.find_iphone_alert](chapters/7.4-service-calls?id=icloud3find_iphone_alert)
- [icloud3.lost_device_alert](chapters/7.4-service-calls?id=icloud3lost_device_alert)
- [icloud3.restart](chapters/7.4-service-calls?id=icloud3restart)



------

#### [Sample Automation & Scripts](chapters/7.5-sample-automation-scripts.md)

- [Example Automations, Scripts and Sensor Templates](chapters/7.5-sample-automation-scripts?id=example-automations-scripts-and-sensor-templates)
- [Home Assistance has started (Automation)](chapters/7.5-sample-automation-scripts?id=home-assistance-has-started-automation)
- [Gary - Turn on/off Gary FarAwayFlag (Automation)](chapters/7.5-sample-automation-scripts?id=gary-turn-onoff-gary-farawayflag-automation)
- [Gary Arrives Home (Automation) - (HomeDistance sensor)](chapters/7.5-sample-automation-scripts?id=gary-arrives-home-automation-homedistance-sensor)
- [Gary Arrives Home (Automation) - (ZoneDistance sensor)](chapters/7.5-sample-automation-scripts?id=gary-arrives-home-automation-zonedistance-sensor)
- [Gary Leaves Home (Automation)](chapters/7.5-sample-automation-scripts?id=gary-leaves-home-automation)
- [Gary Arrives Home (Script)](chapters/7.5-sample-automation-scripts?id=gary-arrives-home-script)
- [Gary - Leaves Home (Script)](chapters/7.5-sample-automation-scripts?id=gary-leaves-home-script)
- [Gary - Arrives Warehouse (Automation)](chapters/7.5-sample-automation-scripts?id=gary-arrives-warehouse-automation)
- [Gary - Send Message (Script)](chapters/7.5-sample-automation-scripts?id=gary-send-message-script)
- [Garage Door - Open (Script)](chapters/7.5-sample-automation-scripts?id=garage-door-open-script)
- [Garage Door - Close (Script)](chapters/7.5-sample-automation-scripts?id=garage-door-close-script)
- [Garage Door - Status (Script)](chapters/7.5-sample-automation-scripts?id=garage-door-status-script)
- [Garage Door - Close at 8pm (Automation)](chapters/7.5-sample-automation-scripts?id=garage-door-close-at-8pm-automation)
- [Garage Door - Close when no one is Home (Automation)](chapters/7.5-sample-automation-scripts?id=garage-door-close-when-no-one-is-home-automation)
- [Garage Door Badge (Template Sensor)](chapters/7.5-sample-automation-scripts?id=garage-door-badge-template-sensor)
- [Set Someone Home Status (Template Sensor)](chapters/7.5-sample-automation-scripts?id=set-someone-home-status-template-sensor)




------
### Questions and Problems

- [ Frequently Asked Questions](chapters/8.1-freq-asked-questions.md)
- [ Configuration Screen Issues](chapters/8.2-configuration_setup-issues.md)
- [ Tracking Issues](chapters/8.3-tracking-issues.md)
- [ Troubleshooting Tools](chapters/8.4-troubleshooting-tools.md)

------
### Other Topics

#### [Technical Information](chapters/9.1-tech-info.md)

- [How the Interval is Determined](chapters/9.1-tech-info?id=how-the-interval-is-determined)
- [Displaying Interval Calculation Information in the `Info` Field](chapters/9.1-tech-info?id=displaying-interval-calculation-information-in-the-info-field)
- [Writing Debug Information to the HA Log File](chapters/9.1-tech-info?id=writing-debug-information-to-the-ha-log-file)
