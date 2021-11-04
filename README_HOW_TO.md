# OECOC Build Guide
Int his article I will explain how to build an OECOC system. 
# Prerequisits
- Home assistant OS installed on raspberry pi
- Basic knollege of Home Assistant
- Basic knollege of Node-RED
- Basic knollege of ESPHome

# 1 Installing home assistant OS and prepairing the software

For this you will need an istalation of home assistand. This can be installed easly on the raspberry pi following [this](https://www.home-assistant.io/installation/raspberrypi) tutorial. Once you have installed home assistant start the pi and go through the ondboarding proces. Once completed you will have to install the following integrations:
- Node-RED
- ESPHome
- Influxdb

Once installed move ont he the next step.

# 2 Node-RED configuration
Once Node-RED is installed go to it in home assistant and configure it if necessary then start it. Once Node-RED is started open it and import the flow provided [here](https://github.com/The-Game-Breaker/TM_2021-2022_Open-ECOsystem-Control_OECOC/blob/ee62c0f1d5eed604a494e42f3039b4c4e979fb77/Software-Firmware/Node-RED/flows.json). Check and change the configuration so it fits your needs and setup.

# 2 Configuring Home assistant
In youre home assistant dashboard configure it to your liking
