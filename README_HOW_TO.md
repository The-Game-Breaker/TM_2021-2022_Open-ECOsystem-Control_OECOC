# OECOC Build Guide
In this article I will explain how to build an OECOC system. 

# Prerequisites
- Home assistant OS installed on raspberry pi
- Basic knowlege of Home Assistant
- Basic knowlege of Node-RED
- Basic knowlege of ESPHome
- Working with mains wiring

# 1 Hardware Node
To create this project you need to the required sensors and components found [here](https://github.com/The-Game-Breaker/TM_2021-2022_Open-ECOsystem-Control_OECOC/blob/43764f40454ba14c2747e6c835ad0126cb0fd91b/Doc/BOM.md)

Solder wires tires to the sensors. Solder the needed components to the pcb.  
![Soldered components on pcb](https://github.com/The-Game-Breaker/TM_2021-2022_Open-ECOsystem-Control_OECOC/blob/77adc2747cf4b1649ac5a258545d397c07d0ecc4/Doc/Resources/Pictures/Hardware/Node/_MG_0957.JPG)

Print and install the needed mounting components and install them.
1. Mount PCB bracket and DIN mounts
2. Mount relay in case and mount the case on the DIN mounts.
3. Glue the AHT10 in its case and glue the case closed (be carefull not to glue the sensorcomponent shut)(it might be handy to add glue were the cables enter the main cable to avoid water in the cables)

![AHT10 senor in enclosure](https://github.com/The-Game-Breaker/TM_2021-2022_Open-ECOsystem-Control_OECOC/blob/4ab3e855020c70989ca0b5f24d8b7ef4a6861072/Doc/Resources/Pictures/Hardware/AHT10_sensor/_MG_0965.JPG)

Once you gathererd all the components you need to connect them all together as shown in the schematic using the cables and connectors.

![Schematic](https://github.com/The-Game-Breaker/TM_2021-2022_Open-ECOsystem-Control_OECOC/blob/77adc2747cf4b1649ac5a258545d397c07d0ecc4/Doc/Resources/Pictures/Hardware/Node/Schematic_node.png)
![Picture of connected node](url)



# 2 Installing home assistant OS and preparing the software

For this, you will need an instalation of home assistant. This can be installed easily on the raspberry pi following [this](https://www.home-assistant.io/installation/raspberrypi) tutorial. Once you have installed home assistant, start the rasberry pi and go through the onboarding process. Once completed, you will have to install the following integrations:
- Node-RED
- ESPHome
- Influxdb

Once installed, move on to the next step.
# ESPHome configuration
Once ESPHome is installed, go to it in home assistant and start it. 

# 4 Node-RED configuration

Once Node-RED is installed, go to it in home assistant and configure it if necessary, then start it. Once Node-RED is started, open it and import the flow provided [here](https://github.com/The-Game-Breaker/TM_2021-2022_Open-ECOsystem-Control_OECOC/blob/ee62c0f1d5eed604a494e42f3039b4c4e979fb77/Software-Firmware/Node-RED/flows.json). Check and change the configuration so it fits your needs and setup.

# 3 Configuring Home assistant

Configure your home assistant dashboard to your liking or open the raw configuration editor and paste the code found in this [file](https://github.com/The-Game-Breaker/TM_2021-2022_Open-ECOsystem-Control_OECOC/blob/4365aa8a5759891aa45c2a583b3c3437a4dd4da0/Software-Firmware/Home_Assistant/Dashboard_config.yaml).

