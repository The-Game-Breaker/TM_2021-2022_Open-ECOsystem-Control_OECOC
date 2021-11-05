# OECOC Build Guide
In this article I will explain how to build an OECOC system. 
- [OECOC Build Guide](#oecoc-build-guide)
- [Prerequisites](#prerequisites)
- [1 Hardware Node](#1-hardware-node)
- [2 Installing home assistant OS and preparing the software](#2-installing-home-assistant-os-and-preparing-the-software)
- [3 ESPHome configuration](#3-esphome-configuration)
- [4 Node-RED configuration](#4-node-red-configuration)
- [5 Configuring Home assistant](#5-configuring-home-assistant)
- [6 Connecting it all together](#6-connecting-it-all-together)
- [7 Mains connections](#7-mains-connections)
- [8 Enjoy your new automated terrarium](#8-enjoy-your-new-automated-terrarium)

# Prerequisites
- Home assistant OS installed on raspberry pi
- Basic knowlege of Home Assistant
- Basic knowlege of Node-RED
- Basic knowlege of ESPHome
- Working with mains wiring

# 1 Hardware Node
To create this project, you need the required sensors and components found [here](https://github.com/.The-Game-Breaker/TM_2021-2022_Open-ECOsystem-Control_OECOC/blob/43764f40454ba14c2747e6c835ad0126cb0fd91b/Doc/BOM.md)
| Item                    | Qty           | Description |
|-------------------------|---------------|-------------|
|                         | 1 Node        |             |
| ESP32                   | 1             |             |
| AHT10                   | 2             |             |
| DS18B20                 | 2             |             |
| 8 Relay module          | 1             |             |
| Reed switch             | 2             |             |
| Buzzer                  | 1             |             |
| 5v regulator or adapter | 1             |             |
|                         | Project Total |             |
| Raspberry pi            | 2             |             |
| Touchscreen             | 1             |             |

Solder wires to the sensors. Solder the needed components to the pcb.  
![Soldered components on pcb](https://github.com/The-Game-Breaker/TM_2021-2022_Open-ECOsystem-Control_OECOC/blob/77adc2747cf4b1649ac5a258545d397c07d0ecc4/Doc/Resources/Pictures/Hardware/Node/_MG_0957.JPG)

Print and install the needed mounting components and install them.
1. Mount PCB bracket and DIN mounts
2. Mount relay in the case and mount the case on the DIN mounts.
3. Glue the AHT10 in its case and glue the case closed (be carefull not to glue the sensorcomponent shut. It might be handy to add glue were the cables enter the main cable to avoid water in the cables)

![AHT10 sensor in enclosure](https://github.com/The-Game-Breaker/TM_2021-2022_Open-ECOsystem-Control_OECOC/blob/4ab3e855020c70989ca0b5f24d8b7ef4a6861072/Doc/Resources/Pictures/Hardware/AHT10_sensor/_MG_0965.JPG)

Once you gathererd all the components, you need to connect them all together as shown in the schematic using the cables and connectors.

![Schematic](https://github.com/The-Game-Breaker/TM_2021-2022_Open-ECOsystem-Control_OECOC/blob/77adc2747cf4b1649ac5a258545d397c07d0ecc4/Doc/Resources/Pictures/Hardware/Node/Schematic_node.png)
![Picture of connected node](url)



# 2 Installing home assistant OS and preparing the software

For this, you will need an installation of home assistant. This can be installed easily on the raspberry pi following [this](https://www.home-assistant.io/installation/raspberrypi) tutorial. Once you have installed home assistant, start the rasberry pi and go through the onboarding process. Once completed, you will have to install the following integrations:
- Node-RED
- ESPHome
- Influxdb

Once installed, move on to the next step.
# 3 ESPHome configuration
Once ESPHome is installed, go to it in home assistant and start it. Make a new device and select esp32, then import the configuration file  found [here](https://github.com/The-Game-Breaker/TM_2021-2022_Open-ECOsystem-Control_OECOC/blob/ee62c0f1d5eed604a494e42f3039b4c4e979fb77/Software-Firmware/Node/terra-1.yaml). 

Edit the configuration file so it fits your setup. Plug in your ESP32 then click install and select  `Plug into the computer running ESPhome Dashboard`. Select the correct port and ESPHome should start flashing the ESP32. This only has to be done once for the first time, afterwards you can use the `OTA` option to install configuration.

# 4 Node-RED configuration

Once Node-RED is installed, go to it in home assistant and configure it if necessary, then start it. Once Node-RED is started, open it and import the flow provided [here](https://github.com/The-Game-Breaker/TM_2021-2022_Open-ECOsystem-Control_OECOC/blob/ee62c0f1d5eed604a494e42f3039b4c4e979fb77/Software-Firmware/Node-RED/flows.json). Check and change the configuration so it fits your needs and setup.

# 5 Configuring Home assistant

Configure your home assistant dashboard to your liking. Add extra buttons, gauges, graphs or sliders to monitor and control the thermostat. You can also open the raw configuration editor and paste the code found in this [file](https://github.com/The-Game-Breaker/TM_2021-2022_Open-ECOsystem-Control_OECOC/blob/4365aa8a5759891aa45c2a583b3c3437a4dd4da0/Software-Firmware/Home_Assistant/Dashboard_config.yaml).

# 6 Connecting it all together

Now install your ESP32 on its carrier board and install the sensors in your terrarium. When installing be sure to install the sensors in places that will provide you with the correct data you need. In terrariums it might be usefull to install one sensor on the hot side and the other on the cold side. Also keep the location of the sensors in mind when setting the parameters.

# 7 Mains connections

**WARNING** Working with mains voltage is dangerous, only proceed if you know what you are doing and take the necessary safety precautions.

Connect all your terrarium devices to their respective relays on the board.

# 8 Enjoy your new automated terrarium
Choose your parameters such as the minimum and maximum humidiy and temperature in realtion to environment you want to create.
Enjoy your very own automated terrarium. 