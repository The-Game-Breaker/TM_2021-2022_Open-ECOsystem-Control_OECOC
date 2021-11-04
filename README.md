- [TM_2021-2022_Open-ECOsystem-Control_OECOC](#tm_2021-2022_open-ecosystem-control_oecoc)
  - [Nodes](#nodes)
  - [Central Server](#central-server)
- [Hardware](#hardware)
  - [Nodes](#nodes-1)
      - [Reason of choice](#reason-of-choice)
  - [Central Server](#central-server-1)
      - [Reason of choice](#reason-of-choice-1)
  - [End user terminal](#end-user-terminal)
      - [Reason of choice](#reason-of-choice-2)
  - [Sensors](#sensors)
    - [AHT10](#aht10)
      - [Reason of choice](#reason-of-choice-3)
    - [DS18B20](#ds18b20)
      - [Reason of choice](#reason-of-choice-4)
    - [Reed switches](#reed-switches)
      - [Reason of choice](#reason-of-choice-5)
  - [Power](#power)
    - [Current sensor](#current-sensor)
      - [Reason of choice](#reason-of-choice-6)
  - [Actuators](#actuators)
    - [Relay modules](#relay-modules)
- [Software](#software)
  - [Visual studio code](#visual-studio-code)
  - [Openscad](#openscad)
  - [Fusion360](#fusion360)
  - [Home assistant](#home-assistant)
  - [ESPhome](#esphome)
  - [Node-RED](#node-red)
  - [InfluxDB](#influxdb)
- [Protocols](#protocols)
  - [Wifi](#wifi)
  - [Home Assistant api](#home-assistant-api)
  - [MQTT](#mqtt)
- [Schematics](#schematics)
- [Flowchart](#flowchart)
# TM_2021-2022_Open-ECOsystem-Control_OECOC
Open source ecosystem controller for controlling:
- Terrariums 
- Aquariums 
- Ponds
- Aquaponics
- Greenhouses 
- Etc

It is divided in the following:
- Nodes
- Central server

## Nodes
Nodes are used to read the environmental sensors and communicate the information to the central server. They are also used to control several actuators to influence the environment.

## Central Server
The central server is used to receive data from the the nodes and communicate the information to the the users and other nodes. The central server decides which actions are required to keep the environmental parameters within the required limits.

The server also provides a local and remote platform to view and control the environmental parameters.

# Hardware
## Nodes
The ESP32 formes the bases for the nodes. It is programmed using ESPHome. It provides a platform for the sensors and relays to connect with the central server. The connection between the nodes and sensors is enabled by a carrier board. Pictured below.

![Node Carrier board ESP32 not mounted](https://github.com/The-Game-Breaker/TM_2021-2022_Open-ECOsystem-Control_OECOC/blob/77adc2747cf4b1649ac5a258545d397c07d0ecc4/Doc/Resources/Pictures/Hardware/Node/_MG_0962.JPG)

On this board the sensors are mounted with modular connectors.

#### Reason of choice
I chose the ESP32 because it is a compact and afordable controller with the needed features and pinout. It also allows for future expansion. 

## Central Server
Raspberry pi with homeassistent, ESPHome, node red.
The raspberry pi acts as a central server and provides a grapical web interface to view and control the connected devices. It also provides a system to program and update the nodes. Finally it provides a Node-RED interface to program and fine-tune the control and automation features.


#### Reason of choice
I chose this platform because I was already partly familiar with it. It is also very flexible and versitile.


## End user terminal
Raspberry pi with touchscreen and homeassistent interface.

#### Reason of choice
I wanted to be able to see the interface when standing near the terrariums so this way I am able to view and control the terrariums easily.

## Sensors
An overvieuw of the various sensors and their uses.

---

### AHT10
The AHT10 will be used to monitor the temperature and humidity.

![AHT10 senor in enclosure](https://github.com/The-Game-Breaker/TM_2021-2022_Open-ECOsystem-Control_OECOC/blob/4ab3e855020c70989ca0b5f24d8b7ef4a6861072/Doc/Resources/Pictures/Hardware/AHT10_sensor/_MG_0965.JPG)

#### Reason of choice
I chose this sensor because it was a most suitable for this application. It measures essential features like temperature and humidity but it doesn't have unused features like air pressure which doesn't matter in terrarium environments (this would be overkill). Therefore, it is also a lot cheaper than a Bosch BME280 which was my first idea. The sensor is also natively supported in ESPHome.

### DS18B20
The DS18B20 will be used to monitor the temperature of water or very humid environments.

![Picture of DS18B20 inclosed in waterproof sleeve with cable](url)

#### Reason of choice
I chose this sensor because it is a well-known sensor that provides reasonable temperature data for its price.


### Reed switches
These are used to monitor if the terrarium doors are opened. If it's opened too long, it sends a notification via home assistant and sounds an alarm.

#### Reason of choice
I chose these because I had them available and they matched for use in my project. It also adds an extra feature to the system that is not typically found in thermostats.


## Power
### Current sensor
The current sensor is used to monitor the power consumption. It also provides the ability to calculate the running costs.

#### Reason of choice
I chose this sensor because it was fairly cheap. However, if I were to do this again, I would integrate a similar sensor on the carrier board pcb. This would make wiring and deploying much easier.

![Used current sensor](https://github.com/The-Game-Breaker/TM_2021-2022_Open-ECOsystem-Control_OECOC/blob/ad19109421f6b388fefdfc3097e506008aab1973/Doc/Resources/Pictures/Hardware/SEEED-Electricity-Sensor.jpg)

## Actuators
### Relay modules
The relay module is responsible for controlling the various actuators.

![8 Relay relay module](https://github.com/The-Game-Breaker/TM_2021-2022_Open-ECOsystem-Control_OECOC/blob/411a693bcd60b609918b9289cb70e5a48a72820e/Doc/Resources/Pictures/Hardware/8ralay_relaymodule.jpg)]


# Software

## Visual studio code
Visual studio code is used to document and manage the files of the project. Initially it was planned to be used to program the project as well but this turned out to be unnecessary.

I chose it because I'm familiar with it.

## Openscad
Openscad was used to create some of the 3D models such as the DIN mounts. I used a script made by remoteqth.com. Because openscad is code based, it makes it easy to create different models based on the same "source model" simply by using different parameters.

## Fusion360
Fusion360 was used to create some of the more custom models such as the node mainboard mounting plate.

## Home assistant
Home assistant is used as the central server for the OECOC system. It also provides a user interface (UI) for interacting with the OECOC system. Finally it hosts some of the needed software. This way, we have an all-in-one package for controlling and programming the system.

## ESPhome
ESPHome is used as the main programmer for the nodes. Not only does it make it easy to create a new and custom node, it also provides a simple way to update OTA. 
It runs directly on the home assistant server. 

## Node-RED
Node-RED is used as the backbone for dealing with the incoming data and automating actions. I chose it because it is easy to work with and very adaptable. It also runs directly on the home assistant server.

## InfluxDB
I decided to use InfluxDB to log the incoming data to get a better understanding of the temperature flow. At the moment I don't use the captured data for anything besides being able to look at it. This data could become very usefull in newer iterations of the project. InfluxDB was chosen because it is easy to use and is designed to work with timed data.

It also runs on the home assistant server.




# Protocols
## Wifi
Used to communicate between the main server node and web interface clients.

## Home Assistant api
THe home Assistant API is used to communicate with everything on the main server and web interface.

## MQTT
MQTT is not really used but is considered for later intergration.



# Schematics
![Schematic](https://github.com/The-Game-Breaker/TM_2021-2022_Open-ECOsystem-Control_OECOC/blob/77adc2747cf4b1649ac5a258545d397c07d0ecc4/Doc/Resources/Pictures/Hardware/Node/Schematic_node.png)

# Flowchart

![Main Flowchart](https://github.com/The-Game-Breaker/TM_2021-2022_Open-ECOsystem-Control_OECOC/blob/7ecdbfd31a25872af0eda6d846d4bfb034369db6/Doc/Flowcharts/Mainflow.png)