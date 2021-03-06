## Mosquitto MQTT broker

Made for [netPI](https://www.netiot.com/netpi/), the Open Edge Connectivity Ecosystem

### Debian Stretch with Mosquitto MQTT message server(broker)

The image provided hereunder deploys a container with installed Debian Stretch and a Mosquitto MQTT server. This makes it suitable for handling the "Internet of Things" message protocol MQTT as a broker. MQTT clients on localhost or local area networks can use this broker for message distribution in the publish/subscribe model based manner.

Base of this image builds a tagged version of [debian:stretch](https://hub.docker.com/r/resin/armv7hf-debian/tags/) and the [Mosquitto](https://mosquitto.org/) MQTT server in the version V1.4.14 supporting the MQTT protocol versions 3.1 and 3.1.1.

#### Container prerequisites

##### Port mapping

If the containerized MQTT server is used for message transactions of localhost MQTT clients hosted on netPI only then there is no need to map ports. Otherwise the ports 1883 and 8883 need to be mapped to free netPI host ports to get accessible over netPI's local area networks.

#### Getting started

STEP 1. Open netPI's landing page under `https://<netpi's ip address>`.

STEP 2. Click the Docker tile to open the [Portainer.io](http://portainer.io/) Docker management user interface.

STEP 3. Enter the following parameters under **Containers > Add Container**

* **Image**: `hilschernetpi/netpi-mosquitto-mqtt-broker`

* **Port mapping**: `Host "1883" (any unused one) -> Container "1883"` `Host "8883" (any unused one) -> Container "8883"` 

* **Restart policy"** : `always`

STEP 4. Press the button **Actions > Start container**

Pulling the image from Docker Hub may take up to 5 minutes.

#### Accessing

The container starts Mosquitto daemon automatically.

Start your clients and publish/subscribe your topics and messages as usual.

#### Tags

* **hilscher/netPI-mosquitto-mqtt-broker:latest** - non-versioned latest development output of the master branch. Can run on any netPI system software version.

#### GitHub sources
The image is built from the GitHub project [netPI-mosquitto-mqtt-broker](https://github.com/Hilscher/netPI-mosquitto-mqtt-broker). It complies with the [Dockerfile](https://docs.docker.com/engine/reference/builder/) method to build a Docker image [automated](https://docs.docker.com/docker-hub/builds/).

To build the container for an ARM CPU on [Docker Hub](https://hub.docker.com/)(x86 based) the Dockerfile uses the method described here [resin.io](https://resin.io/blog/building-arm-containers-on-any-x86-machine-even-dockerhub/).

[![N|Solid](http://www.hilscher.com/fileadmin/templates/doctima_2013/resources/Images/logo_hilscher.png)](http://www.hilscher.com)  Hilscher Gesellschaft fuer Systemautomation mbH  www.hilscher.com
