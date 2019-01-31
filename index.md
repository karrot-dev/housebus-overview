class: center
<h1 style="border-bottom: none; padding-top: 100px">HouseBus overview</h1>

.big[Nick Sellen, Matthias Larisch]

--

<div class="center" style="font-size: 50px; padding-top: 40px">
  <span style="font-size: 180px; font-family: 'Cabin Sketch'; vertical-align: middle">?</span>
</div>

---
# Hardware

<img src="./images/pcb-picture.jpg" style="float: right; width: 50%" />

* STM32 Microcontroller
  * 64 kByte program memory
  * 16 kByte RAM
  * 48 MHz
* CAN Transceiver
* 8 kByte EEPROM
* Connectors
  * Bus
  * Debug/Programming
  * Sensors
* Soldering area

---
<img src="./images/pcb-schematics.svg" style="float: right; width: 80%" />
---
<img src="./images/pcb-layout.svg" style="float: right; width: 90%" />
---
<img src="./images/allpcb.png" style="float: right; width: 100%" />
---

# CAN-Bus

<img src="./images/telephone_cable_wikimedia_erkaha.jpg" style="width: 25%; float:right;" />
<small class="attribution">CC BY-SA Erkaha from wikimedia commons<br>CC BY-SA 3.0, https://commons.wikimedia.org/w/index.php?curid=31571749</small>

* Electrical transfer protocol: symmetrical, bidirectional transfer
* Arbitration, addressing, CRC

<img src="./images/CAN-Bus-frame_in_base_format_without_stuffbits.svg" style="width: 100%;" />

---

# UAVCAN

<img src="./images/uavcan_architecture.png" style="width: 40%; float:right;" />

* builds on top of CAN:
  * addresses (127 nodes per network)
  * data types
  * broadcast messages
  * request / response messages


---

```
#
# Get or set a parameter by name or by index.
# Note that access by index should only be used to retreive the list of parameters; it is higly
# discouraged to use it for anything else, because persistent ordering is not guaranteed.
#

uint13 index

# If set - parameter will be assigned this value, then the new value will be returned.
# If not set - current parameter value will be returned.
# Refer to the definition of Value for details.
Value value
uint8[<=92] name

---

void5
# Actual parameter value.
Value value

void5
Value default_value    # Optional

void6
NumericValue max_value # Optional, not applicable for bool/string

void6
NumericValue min_value # Optional, not applicable for bool/string

uint8[<=92] name
```

---

# home automation / smart home

* gathering data about the house
  * temperature, humidity
  * utilities data (water, gas, electricity)
  * door bell usage...
* controlling things around the house
  * lights, fans, door opening
* data awareness
  * showing people inside and outside the house how we live
* cool, fun learning project

---

# don't they already exist?

<img src="/images/01dc71bae4d5468c9cc9bf62391ced08.jpg">

---
class: middle, center

<img src="/images/ED-AY270_bkrvsu_JV_20190114131426.jpg">

---

<img src="/images/kanthaus-housebus-overview.png" style="width: 80%; margin-left: 100px;">

---

<img src="/images/housebus-layers.png" style="width: 80%; margin-left: 100px;">

---

layout: false
class: big
# Join us!

* contribute! &rarr; [github.com/NerdyProjects/HouseBusNode](https://github.com/NerdyProjects/HouseBusNode) <small>(C, STM32)</small>
* contribute! &rarr; [github.com/yunity/uavcan-web](https://github.com/yunity/uavcan-web)
* contribute! &rarr; [github.com/yunity/uavcan-influxdb-writer](https://github.com/yunity/uavcan-influxdb-writer)
* uavcan &rarr; [uavcan.org](https://uavcan.org/)
* contribute! &rarr; [github.com/yunity/openwrt-stats-collector](https://github.com/yunity/openwrt-stats-collector)
* contribute! &rarr; [github.com/yunity/fritzinfluxdb](https://github.com/yunity/fritzinfluxdb)

