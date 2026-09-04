# Sample Automations & Scripts

The following automations and scripts are one example of how I am using iCloud3 for presence detection. Specifically, these show how I open my garage door when I arrive home.

I have an ESP32 running ESPHome that is connected to my garage door that creates several HA entities:

- *switch.garage_door* - Opens and closes it just like a wall mounted switch.
- *cover.garage_door* - Detects if the door is open or closed.
- *sensor.garage_door_distance* - Measures where the door is when it is opening or closing

I use several entities:

- *input_boolean.ha_started_flag* - Prevents the door from opening when HA has just been restarted.
- *input_boolean.gary_far_away_flag* - Set when Gary is more than 5 miles from Home.
- *sensor.someone_home* - Indicates if someone is home, no one is home or everyone is away

I use the following iCloud3 sensors and sensor attributes:

- *gary_iphone_zone_distance* - Distance to Home. I could also use *sensor.gary_iphone_home_distance* or *sensor.gary_iphone_zone_distance_warehouse* when tracking from several zones.
- *gary_iphone_zone_name* - Set to the zone name (Home) when in the zone.
- *sensor.gary_iphone_zone_distance/max_distance attribute* - Set to 0 when exiting the zone, then set to the furthest distance from the zone while traveling. This is used to see when I went more than 2 miles and probably driving rather than leaving the Home zone and just walking around the neighborhood. I could also use *sensor.gary_iphone_home_distance/max_distance attribute* or *sensor.gary_iphone_zone_distance_warehouse/max_distance attribute* when tracking from several zones.

My goal is to

- Open the garage door when I arrive home.
- Detect if the garage door is open when it should not be.
- Display badges showing the stage of the garage door and location of people.
- Be able to check the status of the garage door.
- Close it manually if it is open when it should not be.
- Close it if everyone is far away from Home.

The following automations and scripts do this reliably as long as I have a good cell signal and the GPS accuracy is within limits. These automations and scripts can be adapted for many other tasks (lights, security system, locks, camera operations, etc).


#### Example Automations, Scripts and Sensor Templates
The following Automations, Scripts and Sensor Templates are shown:
- Home Assistant has started (Automation)
- Gary - More/less than 5 miles from Home (Automation)
- Gary - Arrives Home (Automation)
- Gary - Arrives Home (Script)
- Gary - Leaves Home (Automation)
- Gary - Leaves Home (Script)
- Gary - Arrives Warehouse (Automation)
- Gary - Send Message (Script)
- Garage Door - Open (Script)
- Garage Door - Close (Script)
- Garage Door - Open or Close (Automation)
- Garage Door - Status (Script)
- Garage Door - Close at 8pm (Automation)
- Garage Door - Close when no one is Home (Automation)
- Garage Door Badge (Template Sensor)
- Set Someone Home Status (Template Sensor)



-----

#### Home Assistant has started (Automation)

```
alias: HA - Started Flag, Set
triggers:
  - trigger: homeassistant
    event: start
conditions: []
actions:
  - delay: "00:00:20"
  - action: input_boolean.turn_on
    target:
      entity_id: input_boolean.ha_started_flag
mode: single
```



-----
#### Gary Arrives Home (Automation) -  (HomeDistance sensor)

This automation uses the *HomeDistance* sensor. This sensor is always available and can be used when tracking from only one zone.

- Triggers:
  - *Gary's ZoneName* changes to *Home*, or
  - *Gary's HomeDistance* is less than .35 miles
- Conditions:
  - *Gary's HomeDistance/Max distance* attribute > 3 miles

- Action:
  - Run the *Gary - Arrives Home* script to open the garage door
  - Send a message that Gary is Home.

```
alias: Gary - Arrives Home
description: Gary Arrives Home
triggers:
  - trigger: state
    entity_id:
      - sensor.gary_iphone_zone_name
    to: Home
  - trigger: numeric_state
    entity_id: sensor.gary_iphone_home_distance
    below: 0.35
conditions:
  - condition: numeric_state
    entity_id: sensor.gary_iphone_home_distance
    attribute: max_distance
    above: 3
actions:
  - action: script.notify_gary_iphone
    data:
      title: Gary Arrives Home
      message: "Distance: {{ states('sensor.gary_iphone_home_distance') }}"
  - action: script.garage_door_open
    data: {}
mode: single
```



-----
#### Gary Leaves Home (Automation)

- Triggers:
  - *Gary's ZoneName* changes to 'Away' from 'Home'

- Conditions:
  - Home Assistant has been running for more than 2 minutes.
  - *Gary's HomeDistance* more than 0.1 miles

- Action:
  - Run the *Gary -  Leaves Home* script, and
  - Send a message that Gary has left Home



```yaml
alias: Gary - Leaves Home
triggers:
  - trigger: state
    entity_id: sensor.gary_iphone_zone_name
    to: Away
    from: Home
conditions:
  - condition: state
    entity_id: input_boolean.ha_started_flag
    state: "on"
    for:
      hours: 0
      minutes: 2
      seconds: 0
  - condition: numeric_state
    entity_id: sensor.gary_iphone_home_distance
    above: 0.1
actions:
  - action: script.gary_leaves_home
    data: {}
  - action: script.notify_gary_iphone
    data:
      title: Gary Leaves Home
      message: "Distance: {{ states('sensor.gary_iphone_home_distance') }}"
mode: single
```



-----
#### Gary Arrives Home (Script)

- Action:
  - Run the *Garage Door - Open* script

```
alias: Gary - Arrives Home
sequence:
  - action: script.garage_door_open
    data: {}
mode: single
icon: mdi:location-enter
```



-----
#### Gary - Leaves Home (Script)

- Action:
  - Run the *Garage Door - Close* script.

```
alias: Gary - Leaves Home
sequence:
  - condition: state
    entity_id: input_boolean.ha_started_flag
    state: "on"
    for:
      hours: 0
      minutes: 2
      seconds: 0
  - action: script.garage_door_close
    data: {}
mode: single
icon: mdi:location-exit
```



-----

#### Gary - Arrives Warehouse (Automation)

This is an example of an automation for a *Track from Zone* action. It is slightly different than the *Gary - Arrives Home* automation since it uses the *gary_iphone_zone_distance_warehouse* instead of the *gary_iphone_zone_distance* entity.

```
alias: Gary - Arrives Warehouse
description: ""
triggers:
  - trigger: state
    entity_id:
      - sensor.gary_iphone_zone_name
    to: Warehouse
  - trigger: numeric_state
    entity_id: sensor.gary_iphone_zone_distance_warehouse
    below: 0.35
conditions: []
actions:
  - action: script.notify_gary_iphone
    data:
      title: Gary Arrives - Warehouse Zone
      message: >-
        Zone: {{ states('sensor.gary_iphone_zone_name') }},
        Distance: {{ states('sensor.gary_iphone_zone_distance') }}
  - action: script.gary_arrives_warehouse
    data: {}
mode: single
```



-----

#### Gary - Send Message (Script)

- Action:
  - Send a message to Gary's iPhone

```
alias: Gary - Send Message
sequence:
  - action: notify.mobile_app_gary_iphone
    data:
      title: "{{ title }}"
      message: "{{ message }}"
mode: single
icon: mdi:message-alert-outline
```




-----

#### Garage Door - Open (Script)

- Conditions:
  - Home Assistant has been running for more than 2 minutes
  - The Garage Door has been closed for more than 2 minutes
  - No one is Far Away from Home (the *Someone Home* sensor is not *AllFarAway*)

- Actions:
  - Press the Garage Door switch to open it
  - Send a message that the door has been opened



```
alias: Garage Door - Open
sequence:
  - condition: state
    entity_id: input_boolean.ha_started_flag
    state: "on"
    for:
      hours: 0
      minutes: 2
      seconds: 0
  - condition: state
    entity_id: cover.garage_door
    state: closed
    for:
      hours: 0
      minutes: 2
      seconds: 0
  - condition: not
    conditions:
      - condition: state
        entity_id: sensor.someone_home
        state: AllFarAway
    alias: Confirm SomeoneHome Sensor is not AllFarAway
  - action: switch.turn_on
    target:
      entity_id: switch.garage_door
  - action: script.notify_gary_iphone
    data:
      title: Garage Door Action
      message: Garage Door Opened
mode: single
icon: mdi:garage-open
```




-----
#### Garage Door - Close (Script)

- Conditions:
  - Home Assistant has been running for more than 2 minutes
  - The Garage Door has been open for at least 15 seconds

- Actions:
  - Press the Garage Door switch to close it
  - Send a message to Gary



```
alias: Garage Door - Close
sequence:
  - condition: state
    entity_id: input_boolean.ha_started_flag
    state: "on"
    for:
      hours: 0
      minutes: 2
      seconds: 0
  - condition: state
    entity_id: cover.garage_door
    state: open
    for:
      hours: 0
      minutes: 0
      seconds: 15
  - action: switch.turn_on
    target:
      entity_id: switch.garage_door
  - action: script.notify_gary_iphone
    data:
      title: Garage Door Action
      message: Garage Door Closed
mode: single
icon: mdi:garage
```




-----
#### Garage Door - Status (Script)

- Action:
  - Send message about the status of the Garage Door

```
alias: Garage Door - Show Status
sequence:
  - action: script.notify_gary_iphone
    data:
      title: Garage Door Control Status
      message: >-
        DoorStatus={{states("cover.garage_door")}},
        Distance={{states("sensor.gary_iphone_zone_distance")}},
        Zone={{states("sensor.gary_iphone_zone_name") }}
mode: single
icon: mdi:message-alert-outline
```




-----
#### Garage Door - Close at 8pm (Automation)

Make sure the Garage Door is closed after 8pm

- Trigger:
  - Time is 8:00:00pm (20:00:00)
- Conditions:
  - Garage door is open
- Actions:
  - Run the *Garage Door - Close* script
  - Send a message to Gary

```
alias: Garage Door - Close After 8pm
description: ""
triggers:
  - trigger: time
    at: "20:00:00"
conditions:
  - condition: state
    entity_id: cover.garage_door
    state: open
actions:
  - action: script.garage_door_close
    data: {}
  - action: script.notify_gary_iphone
    data:
      title: Garage Door Closed
      message: After 8pm - Close Door Automation Triggered
mode: single
```




-----
#### Garage Door - Close when no one is Home (Automation)

Make sure the Garage Door is closed when no one is Home or everyone is far away from Home.

- Triggers:
  - The Someone Home sensor changes to 'AllAway', or
  - The Someone Home sensor changes to 'AllFarAway'
- Conditions:
  - The Garage door is open
- Actions:
  - Run the Garage Door - Close script
  - Send a message to Gary

```
alias: Garage Door - Close, No One Home
triggers:
  - trigger: state
    entity_id:
      - sensor.someone_home
    to: AllAway
  - trigger: state
    entity_id:
      - sensor.someone_home
    to: AllFarAway
conditions:
  - condition: state
    entity_id: cover.garage_door
    state: open
actions:
  - action: script.garage_door_close
    data: {}
  - action: script.notify_gary_iphone
    data:
      title: Garage Door Closed
      message: No One Home - Close Door Automation Triggered
mode: single
```




-----

#### Garage Door - Open or Close (Automation)

Open or Close the Garage Door by toggling the switch

```
alias: Garage Door - Press Switch
triggers:
  - trigger: state
    entity_id: switch.garage_door
    to: "on"
actions:
  - action: switch.turn_on
    target:
      entity_id: switch.garage_door
mode: single
```




-----
#### Garage Door Badge (Template Sensor)

This creates the *sensor.garage_door_badge* entity that displays a garage door open/close image,

*Note*: Sample images, *garage-door-open.png* and *garage-door-closed.png*, are in the *icloud3/event_log* directory. Copy them to the */www/images* directory for this script. HA converts the 'local' in the script to 'www'.

```yaml
#-------------------------------------------------------
# Garage Door Open/Closed Badge
#-------------------------------------------------------
- platform: template
  sensors:
    garage_door_badge:
      value_template: >-
        {{states("cover.garage_door") | title}}
      entity_picture_template: >-
        {% if is_state("cover.garage_door", "open") %}
          /local/images/garage-door-open.png
        {% else %}
          /local/images/garage-door-closed.png
        {% endif %}

```



-----

#### Set Someone Home Status (Template Sensor)

This creates the *sensor.someone_home* entity using the *sensor.[devicename]_zone_name* entity.

Value:

- AllHome - *sensor.gary_iphone_zone_name* and *sensor.lillian_iphone_zone_name* = "Home"
- AllFarAway - *input_boolean.gary_far_away_flag* and *input_boolean.lillian_far_away_flag* are "on"
- AllAway - *sensor.gary_iphone_zone_name* and *sensor.lillian_iphone_zone_name* are not "Home"
- SomeAway -  *sensor.gary_iphone_zone_name* or *sensor.lillian_iphone_zone_name* are not "Home"

```yaml
#-------------------------------------------------------
# Set Someone Home Status
#-------------------------------------------------------
- platform: template
  sensors:
    someone_home:
      friendly_name: Someone Home
      value_template: >
        {% if is_state("sensor.gary_iphone_zone_name", "Home")
              and is_state("sensor.lillian_iphone_zone_name","Home") %}
          AllHome
        {% elif is_state("input_boolean.gary_far_away_flag", "on")
              and is_state("input_boolean.lillian_far_away_flag","on") %}
          AllFarAway
        {% elif (is_state("sensor.gary_iphone_zone_name", "Home") == false)
              and (is_state("sensor.lillian_iphone_zone_name","Home") == false) %}
          AllAway
        {% elif (is_state("sensor.gary_iphone_zone_name", "Home") == false)
              or (is_state("sensor.lillian_iphone_zone_name","Home") == false) %}
          SomeAway
        {% else %}
          Unknown
        {% endif %}
      icon_template: >
        {% if is_state("sensor.gary_iphone_zone_name", "Home")
              and is_state("sensor.lillian_iphone_zone_name","Home") %}
          mdi:home-import-outline
        {% elif is_state("input_boolean.gary_far_away_flag", "on")
              and is_state("input_boolean.lillian_far_away_flag","on") %}
          mdi:home-circle-outline
        {% elif (is_state("sensor.gary_iphone_zone_name", "Home") == false)
              or (is_state("sensor.lillian_iphone_zone_name","Home") == false) %}
          mdi:home-minus-outline
        {% else %}
          mdi:home-minus-outline
        {% endif %}


```
