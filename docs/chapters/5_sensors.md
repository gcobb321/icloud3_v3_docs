# Sensors <!-- {docsify-ignore} -->

##### Selected From: *Configure Devices & Sensors Menu*

Many sensors are used to display tracking results and other information for a device. This screen is used to select the sensors that should be created.

The sensors are grouped into the following categories:

- **Monitored devices sensors**:

  - **_badge** - Badge sensor - A badge showing the Zone Name or distance from the Home zone. Attributes include location related information
  - **_battery , _battery_status** - Create Battery (65%) and Battery Status (Charging, Low, etc) sensors (Always Created)
  - **_location_sensors** - Location related sensors > Name, zone, distance, travel_time, etc. (_name, _zone, _zone_fname, _zone_name, _zone_datetime, _home_distance, _travel_time, _travel_time_min, _last_located, _last_update)

- **Tracking update sensors**:

  - **_interval** - Time between location request
  - **_last_update** - Last time the location was updated
  - **_next_update**  - Next time the location will be updated (Always Created)
  - **_last_located** - Last time the was located using iCloud or Mobile App location

- **Tracking time sensors:**

  - **_travel_time** - Waze Travel time to Home or closest Track-from-Zone zone (Always Created)
  - **_travel_time_min** - Waze Travel time to Home or closest Track-from-Zone zone in minutes
  - **_travel_time_hhmm** - Waze Travel time to a Zone in hours:minutes
  - **_arrival_time** - Home Zone arrival time based on Waze Travel time (Always Created)

- **Tracking distance sensors**:

  - **_home_distance** - Distance to the Home zone (Always Created)
  - **_zone_distance** - Distance to the Home or closest Track-from-Zone zone
  - **_dir_of_travel** - Direction of Travel for the Home zone or closest Track-from-Zone zone (Towards, AwayFrom, inZone, etc)
  - **_moved_distance** - Distance moved from the last location

- **Track from Zone sensors**:

  - **_zone_fname** - HA Zone entity Friendly Name (HA Config > Areas & Zones > Zones > Name)
  - **_zone** - HA Zone entity_id (`the_shores`)
  - **_zone_name** - Reformat the Zone entity_id, capitalize and remove `_`s (`the_shores` → `TheShores`)
  - **_zone_datetime** - The time the Device entered the Zone
  - **_zone_fname** > HA Zone entity Friendly Name (HA Config > Areas & Zones > Zones > Name)
  - **_last_zone[...]** - Create the same sensors for the device`s last HA Zone

- **Other tracking sensors:**

  - **_gps_accuracy** - GPS acuracy of the last location coordinates
  - **_vertical_accuracy** - Vertical (Elevation) Accuracy
  - **_altitude** - Altitude/Elevation

- **Excluded sensors** -  Sensors that will not be created when iCloud3 starts






![](../images/sensors.png)