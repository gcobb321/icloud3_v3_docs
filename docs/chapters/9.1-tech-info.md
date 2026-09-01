# Technical Information

### How the Interval is Determined

The iCloud3 device tracked uses data from several sources to determine the time interval between the iCloud Find my Friends location update requests.  The purpose is to provide accurate location data without exceeding Apple's limit on the number of requests in a time period and to limit the drain on the device's battery.

The algorithm uses a sequence of tests to determine the interval. If the test is true, it's interval value is used and no further tests are done. The following is for the nerd who wants to know how this is done. 


| Test | Interval | Method Name|
|------|----------|------------|
| ***The Zone (State) changed:*** |  | |
| Zone changed to Stationary Zone | stationary_inzone_interval | 1sz-Stationary |
| Zone Changed to other zone | inzone_interval | 1ez-Zone |
| In near_zone close to home (or another zone) | 15 seconds | 1nz-InHomeNearZone |
| In near_zone far from Home (or another zone) | 15 seconds | 1nhz-InOtherNearZone |
| Left Home zone (or another zone) | 4 minutes | 1ehz-ExitHomeZone |
| Left other zone (or another zone) | 2 minutes | 1ez-ExitOtherZone |
| Entered Another Zone | 4 minutes | 1cz-ZoneChanged |
| ***The Zone (State) did not change:*** |  |  |
| Poor GPS Accuracy | 1 minute | 2-PoorGPS |
| Override interval specified | inzone_interval | 3-Override |
| In Stationary zone | stationary_inzone_interval | 4sz-Stationary |
| In Home zone or near Home zone and direction is Towards | inzone_interval | 4iz-InZone |
| In near_zone | 15 seconds | 4nz-NearZone |
| In other zone & inzone_interval > waze time | inzone_interval | 4iz-InZone |
| Just left a zone | 2.5 minutes | 5-LeftZone |
| Distance from zone < 2.5km/1.5mi | 15 seconds | 10a-Dist < 2.5km |
| Distance from zone < 3.5km/2mi | 30 seconds | 10b-Dist < 3.5km |
| Waze used and Waze time < 5 min. | time `travel_time_factor` | 10c-WazeTime |
| Distance from zone < 5km/3mi | 1 minute | 10d-Dist < 5km |
| Distance from zone < 8km/5mi | 3 minutes | 10e-Dist < 8km |
| Distance from zone < 12km/7.5mi | 15 minutes | 10f-Dist < 12km |
| Distance from zone < 20km/12mi | 10 minutes | 10g-Dist < 20km |
| Distance from zone < 40km/25mi | 15 minutes | 10h-Dist < 40km |
| Distance from zone < 150km/90mi | 1 hour | 10i-Dist < 150km |
| Distance from zone > 150km/90mi | distance/1.5 | 20-Calculated |



The interval is then multiplied by a value based on other conditions. The conditions are:

1. If Stationary, keep track of the number of polls when you are stationary (the stationary count reported in the `info` attribute). Multiply the interval time by 2 when the stationary count is an even number and by 3 when it is divisible by 3.
2. If the direction of travel is Away, multiply the interval time by 2.
3. Is the battery is low, the GPS accuracy is poor or the location data is old, don't make any of the above adjustments to the interval.

   

