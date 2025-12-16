# Dashboard Builder

The Dashboard Builder is a tool that will create and update dashboards showing iCloud3 tracking results and other device information provided by iCloud3. It is added to the HA Sidebar panel when it is created and can be edited using the HA Dashboard Editor in the same manner as other dashboards. It's name starts with *iCloud3-#* and can be changed to meet your needs. There is no limit to the number of iCloud3 dashboards that can be created.

!> When the iCloud3 Integration is install the first time, the *iCloud3* is created and added to the HA Sidebar panel.

!> When new devices are added on the *Update iCloud3 Devices* screen, they are added to all iCloud3 dashboards *All Info, *Track Results and *Badge, Battery view tabs.*

Each dashboard has six view tabs. The *Main* and *Other Devices* view tabs are built for the selected devices when the dashboard is created. The other view tabs (their name starts with a '*') are recreated for all devices whenever a dashboard is updated. The type of elements that are created are:

- All tracking information (tracking results sensors + tracking status sensors  + device information sensors) as one item

- All tracking information (tracking results sensors, tracking status sensors, device information sensors) as separate items

- Device Badge sensors and Battery sensor as one item in several formats

- Device Battery sensors in several formats

   

------
## Dashboard View Tabs

The six views tabs that are set up when a dashboard is created.

- **Main** - The main view for iCloud3 that shows the Event log and devices in several formats.
- **Other Devices** - Tracking info for the devices not on the Main view tab (not shown).
- ***All Info** - Tracking info for all devices where the three sensor glance cards can be copied as a group or individually to other dashboards .
- ***Track Results** - The Tracking info consists of three sensor glance cards - Tracking Results, Tracking status, Device Info Msg. This screen shows the Tracking Results Summary for all devices.
- ***Badge, Battery** - Device Badge and Battery sensors that can be copied as a group or individually to other dashboards .
- **Event Log** - The iCloud3 Event Log (not shown).
- **Main (Backup)** - The Main view tab is not updated when devices are added or deleted. You can customize it to meet your needs and show the sensors that are important to you. You can, however, recreate an existing dashboard which will erase any changes you have made. This screen is the main view tab before it was recreated. Items you really wanted to keep can be copied back to the new Main view tab. (not shown).

![](..\images\dashboard-bldr-views-main.png)

![](..\images\dashboard-bldr-views-allinfo-badge-battery.png)



 

------
## Creating a Dashboard

A dashboard is created on the *iCloud3 Dashboard Builder* screen. This can be found on the *iCloud3 Devices & Sensors* menu on the *iCloud3 Configure Settings* screen accessed uging the *Event Log > Configure Shortcut* or the *HA Settings > Devices & services > iCloud3* screen.

1. Select **Dashboard Builder** on the *iCloud3 Devices & Sensors* menu.
2. Select **Create a new iCloud3 Dashboard**.
3. Select **Update a Dashboard**.
4. Select **SUBMIT**.

The dashboard that is created is named *iCloud3-0, iCloud3-1*, etc. This name can be changed on the *HA Settings > Dashboard* screen.

![](..\images\dashboard-builder.png)

  

------
## Update an Existing Dashboard

When a dashboard is updated, the current iCloud3 devices are used to recreate the *All Info , *Track Results and *Badge, Battery view tabs. The *Main* and *Other Device*s view tabs are not changed. This lets you customize the Main view tab to show sensors, device trackers, and other cards to meet your needs.

1. Select the **iCloud3 Dashboard** to be updated
2. Select **Update a Dashboard**
3. Select **SUBMIT**

> The *Main* and *Other Devices* will be recreated when you select *Recreate a Dashboard*. The current *Main* view tab is saved to the *Main (Backup)* view tab.

  

------
## Customizing the Main view tab

The *All Info, *Track Results and *Badge, Battery view tabs provide selectable elements that can be copied and pasted to another view tab or dashboard using the HA Dashboard Editor screens. That process is beyond the scope of this paragraph. HA provides instructions and tutorials [here⧉](https://www.home-assistant.io/dashboards/).

The screens below show the typical elements that can be copied and pasted.

![](..\images\dashboard-bldr-view-hl.png)

1. On the dashboard screen, select the **Edit Pencil** to open up the HA Dashboard Editor.
2. Go to the view tab with the item you want to copy to another dashboard or view tab.
3. Hover over the **3-dot More** image in the upper-left corner of the item to be copied and select **Copy**.
4. Go to the dashboard or view tab you want to copy the item to. Select the **'+' image** in the the destination area.
5. Select **Paste** copied item to paste it. Pasting it into a *Horizontal Stack* or *Vertical Stack* can help position the item in with other similar items.

![](..\images\dashboard-bldr-edit-copy-paste.png)

  

------
## Miscellaneous Notes

- The dashboard name and icon can be changed on HA Settings > Dashboards screen.
- The *url_path* starts with *ic3db* for dashboards created by the iCloud3 Dashboard Builder. You will not normally see this field.