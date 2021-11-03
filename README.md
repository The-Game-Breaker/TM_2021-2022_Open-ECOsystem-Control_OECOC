- [TM_2021-2022_Open-ECOsystem-Control_OECOC](#tm_2021-2022_open-ecosystem-control_oecoc)
  - [Nodes](#nodes)
  - [Central Server](#central-server)
- [Hardware](#hardware)
  - [Nodes](#nodes-1)
  - [Central Server](#central-server-1)
  - [End user terminal](#end-user-terminal)
  - [Sensors](#sensors)
  - [Environmental](#environmental)
    - [AHT10](#aht10)
    - [DS18B20](#ds18b20)
  - [Power](#power)
    - [CT Clamp](#ct-clamp)
  - [Actuators](#actuators)
    - [Relay modules](#relay-modules)
- [Software](#software)
- [Protocols](#protocols)
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

It are be divided in the following:
- Nodes
- Central server

## Nodes
Nodes are be used to read the environmental sensors and communicate the information to the central server. They are also used to control several actuators to influence the environment.

## Central Server
The central server is used to receive data from the the nodes and communicate the information to the the users and other nodes. The central server decides which actions are required to keep the environmental parameters within the required numbers.

The server also provides a local and remote platform to view and control the environmental parameters.

# Hardware
## Nodes
ESP32/ESP8266 

## Central Server
Raspberry pi with homeassistend, esphome, node red.

## End user terminal
Raspberry pi with touchscreen and homeassistend interface.

## Sensors
## Environmental
### AHT10
The AHT10 will be used to monitor the temperature and humidity.
### DS18B20
The DS18B20 will be used to monitor the temperature of water or very humid environments.

## Power
### CT Clamp

## Actuators
### Relay modules

![alt text][logo]

[logo]: Doc\Resources\Pictures\Hardware\8ralay_relaymodule.jpg "8 Relay relay module"

# Software

Visual studio code (platformIO)
ESPhome
Node-red
Home assistant



# Protocols
Wifi
MQTT

# Schematics
TBD
# Flowchart

![alt text](Doc\Flowcharts\Mainflow.png "Main Flowchart")

![alt text](https://github.com/The-Game-Breaker/TM_2021-2022_Open-ECOsystem-Control_OECOC/blob/7ecdbfd31a25872af0eda6d846d4bfb034369db6/Doc/Flowcharts/Mainflow.png "Main Flowchart")