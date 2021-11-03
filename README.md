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
      - [Reason of choice](#reason-of-choice)
    - [DS18B20](#ds18b20)
      - [Reason of choice](#reason-of-choice-1)
  - [Power](#power)
    - [Current sensor](#current-sensor)
  - [Actuators](#actuators)
    - [Relay modules](#relay-modules)
- [Software](#software)
  - [Visual studio code](#visual-studio-code)
  - [ESPhome](#esphome)
  - [Node-red](#node-red)
  - [Home assistant](#home-assistant)
  - [Openscad](#openscad)
  - [Fusion360](#fusion360)
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

It is divided in the following:
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
![AHT10 senor in enclosure](https://github.com/The-Game-Breaker/TM_2021-2022_Open-ECOsystem-Control_OECOC/blob/77adc2747cf4b1649ac5a258545d397c07d0ecc4/Doc/Resources/Pictures/Hardware/AHT10_sensor/_MG_0965.JPG)
#### Reason of choice
I chose this sensor because it was a more suitable for this aplication. Its also a lot cheaper than a Bosch BME280 wich was my first choice. The sensor is alsonatively suported in esphome.

### DS18B20
The DS18B20 will be used to monitor the temperature of water or very humid environments.
![Alt Text](url)

#### Reason of choice
I chose this sensor its a well known sensor that provides reasonable temperature data for the price.

## Power
### Current sensor
The current sensor is used to monitor the power consumption. I also provides the abillity to calculate the running costs.
![Alt Text]()

## Actuators
### Relay modules
![8 Relay relay module](https://github.com/The-Game-Breaker/TM_2021-2022_Open-ECOsystem-Control_OECOC/blob/411a693bcd60b609918b9289cb70e5a48a72820e/Doc/Resources/Pictures/Hardware/8ralay_relaymodule.jpg)]


# Software

## Visual studio code
## ESPhome
## Node-red
## Home assistant
## Openscad
## Fusion360




# Protocols
Wifi
MQTT
Home Assistant api

# Schematics
![Schematic](https://github.com/The-Game-Breaker/TM_2021-2022_Open-ECOsystem-Control_OECOC/blob/77adc2747cf4b1649ac5a258545d397c07d0ecc4/Doc/Resources/Pictures/Hardware/Node/Schematic_node.png)
# Flowchart

![Main Flowchart](https://github.com/The-Game-Breaker/TM_2021-2022_Open-ECOsystem-Control_OECOC/blob/7ecdbfd31a25872af0eda6d846d4bfb034369db6/Doc/Flowcharts/Mainflow.png)