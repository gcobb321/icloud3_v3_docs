# Zone Log for Expense Reports or Zone Tracking

There may be times when you want to keep track of when a device enters and exits a zone. This is useful for:

- **Expense Reporting** - Keep track of the times you are at a specific location when the miles driven are reimbursable.
- **Tax deductions** - Keep track of the times you visit client locations when the miles driven are deductible on your taxes. 
- **Zone Logging** - Keep track of when a person(s) visit a location or multiple locations.

To do this:

1. Set an HA Zone for the location on the *HA Settings > Areas & Zones > Zones* screen. 

2. Add the zones to be tracked in the *Zone Log Activity* parameter on the *Update Other Devices Parameters* screen for every device you want to track. You can log more than one zone at the same time.

   ![](..\images\zone-log-sel-list.png)

   

### Zone Log csv File and Spreadsheet

The file name lets you select the way the data should be organized. The name contains the year, zone and devicename and is shown below. Select the one that best fits your situation:

1. **By Zone** -`[year]-[zone].csv` - This lets you log multiple devices for the same zone. A record for every device is added to the same Zone file so you can see all of the Devices that were at a specific Zone.
2. **By Device** -`[year]-[device].csv`  - This lets you log multiple zones for the same device. A record for every zone is added to the same Device file so you can see all of the Zones that were visited by a specific Device.
3. **By Device-Zone** -`[year]-[device]-[zone].csv`  - A Device's activity is logged to a separate Zone file.
4. **By Zone-Device** -`[year]-[zone]-[device].csv`  - Every Zone has a separate file for every Device.

A *.csv* spreadsheet file is created in the */config* directory on your Home Assistant server. It is updated when the device leaves the zone with the following information:

- Date
- Date and time the zone was entered
- Date and time the zone was exited from
- Time in the zone (minutes and hours)
- Distance from the Home zone
- Zone name
- Device entity name

![](..\images\zone-log-csv-file.png)

Importing this file into Excel provides various ways of sorting and summarizing this data.

![](..\images\zone-log-spreadsheet.png)

