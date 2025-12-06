# Tracking From More Than One Zone

Normally, you track a device from the Home Zone. The sensor entities for travel time, distance, intervals, next update time, etc. are calculated for the Home Zone. iCloud3 also lets you track a device from another zone. It will calculate the same type of sensor entities for that zone. 

To track from another zone, select that zone in the *Track from Zones* parameter on the *Update Tracked iCloud3 Device* screen. 

1. Select the *iCloud3 Devices* screen.
2. Select the device to be tracked from the other zone.
3. Select the *Track-from-Zones* field, then select the zones to be tracked from.

![](..\images\cf-device-update-tfz.png)

New sensors are created for all of the track-from-zones.

- **Sensor Entities** - The zone name is added to the end of the entity name. For example:
  - Home Zone -*sensor.gary_iphone_travel_time_**home**, sensor.gary_iphone_zone_distance_**home***, etc.
  - Warehouse Zone - *sensor.gary_iphone_travel_time_**warehouse***, *sensor.gary_iphone_zone_distance_**warehouse***, etc.

- **Sensor's Friendly Name** - The zone's display-as friendly is added to the end of the sensor friendly name:
  - Home Zone - Gary TravelTime (**Home**), Gary ZoneDistance (**Home**), etc.
  - Warehouse Zone - Gary TravelTime (**Warehouse**), Gary ZoneDistance (**Warehouse**), etc.


The sensors created when only tracking from the Home zone (*sensor.gary_iphone_travel_time, sensor.gary_iphone_zone_distance, etc.*) have changed:

- Closer to the Home zone - Show the Home zone information
- Within 8km of the Other zone and going towards it - Show the Other zone's information
- Within 8km of the Other zone and going away from it - Show the Home zone's information
- Going towards both zones - Show the Home zone's information if more than 8km away from the Other zone
- Other zone's information is displayed - It's first initial is displayed in the *distance* sensor (🅦 is shown for the Warehouse zone).

