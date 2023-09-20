## Recommended Weather-Appropriate Song Playlists by using W5x00-EVB-Pico with DHT22 & MQTT protocol
This project recommends playlists with songs that match the weather, humidity, and current conditions through an app using MQTT communication.

![ui pentachord](https://github.com/wiznetmaker/W5100S-MQTT-DHT11/assets/143767394/04776918-c4cd-4ac5-92f4-fbf47555317d)

### Get Started
Connect the DHT11 temperature and humidity sensor to the pins configured on the W5100S Pico.
<br>
![282451885_1695204110](https://github.com/wiznetmaker/W5100S-MQTT-DHT11/assets/143767394/c82c8c9f-8593-4d11-9c24-8259b7f4439f)
<br>

Set the values of MQTT_CLIENT_ID, MQTT_USERNAME, MQTT_PASSWORD, MQTT_PUBLISH_TOPIC, and the MQTT broker IP in the variable g_mqtt_broker_ip.

```c
/* Port */
#define PORT_MQTT 1883

/* MQTT */

#define MQTT_CLIENT_ID "rpi-pico"
#define MQTT_USERNAME "wiznet"
#define MQTT_PASSWORD "0123456789"
#define MQTT_PUBLISH_TOPIC "publish_topic"

static uint8_t g_mqtt_broker_ip[4] = {192, 168, 11, 229};
```

<br>  
Create broker using Mosquitto by executing the following command. If the broker is created normally, the broker's IP is the current IP of your desktop or laptop, and the port is 1883 by default.
<br>
<br>

 `mosquitto -c mosquitto.conf -v`   

![282451885_1695217915](https://github.com/wiznetmaker/W5100S-MQTT-DHT11/assets/143767394/ed1c9a58-865f-434b-a76d-549409cdf02f)

Install a mobile application that supports MQTT communication on your smartphone.

Enter the configured IP, client ID, username, and other settings, and then press 'Connect.'

 Subscribe to the specified topic to receive MQTT data for temperature and humidity as well as playlist recommendations.

![282451885_1695207536](https://github.com/wiznetmaker/W5100S-MQTT-DHT11/assets/143767394/5d72707f-aeee-44f1-8280-7723082a1d9d)


## DHT22 (temperature and humidity sensor) & MQTT (temperature, humidity, and playlist output communication protocol)
For more details, please refer to the link below.
* [WIZnet/RP2040-HAT-C/examples/mqtt](https://github.com/Wiznet/RP2040-HAT-C/tree/main/examples/mqtt)
* [vmilea/pico_dht](https://github.com/vmilea/pico_dht)
* [Youtube Data Api](https://developers.google.com/youtube/v3/docs/search/list?hl=ko)

