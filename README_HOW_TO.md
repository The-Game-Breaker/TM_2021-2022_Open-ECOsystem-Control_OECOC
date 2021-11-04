# OECOC Build Guide
In this article I will explain how to build an OECOC system. 

# Prerequisites
- Home assistant OS installed on raspberry pi
- Basic knowlege of Home Assistant
- Basic knowlege of Node-RED
- Basic knowlege of ESPHome

# 1 Installing home assistant OS and preparing the software

For this, you will need an instalation of home assistant. This can be installed easily on the raspberry pi following [this](https://www.home-assistant.io/installation/raspberrypi) tutorial. Once you have installed home assistant, start the rasberry pi and go through the onboarding process. Once completed, you will have to install the following integrations:
- Node-RED
- ESPHome
- Influxdb

Once installed, move on to the next step.

# 2 Node-RED configuration

Once Node-RED is installed, go to it in home assistant and configure it if necessary, then start it. Once Node-RED is started, open it and import the flow provided [here](https://github.com/The-Game-Breaker/TM_2021-2022_Open-ECOsystem-Control_OECOC/blob/ee62c0f1d5eed604a494e42f3039b4c4e979fb77/Software-Firmware/Node-RED/flows.json). Check and change the configuration so it fits your needs and setup.

# 3 Configuring Home assistant

Configure your home assistant dashboard to your liking or open the raw configuration editor and paste the code found in this [file](https://github.com/The-Game-Breaker/TM_2021-2022_Open-ECOsystem-Control_OECOC/blob/4365aa8a5759891aa45c2a583b3c3437a4dd4da0/Software-Firmware/Home_Assistant/Dashboard_config.yaml).

