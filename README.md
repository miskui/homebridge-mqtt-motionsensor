# homebridge-mqtt-sonoffrf-receiver

Get Motion Sensor status via MQTT in Homebridge using [Sonoff RF Bridge 433](https://www.itead.cc/sonoff-rf-bridge-433.html) with [TasmOTA firmware](https://github.com/arendst/Sonoff-Tasmota/wiki).
Motion sensor is activated when received RF code matches for rfcode or RF key stored in Sonoff RF Bridge. Open Sonoff RF Bridge console to read out received RF codes as hexadecimal values in DATA field. Use these values in rfcode parameter or use rfkey if you have already defined RF codes in Sonoff RF Bridge. Value 'any' will activate the sensor if any RF code received.
Sensor can be [motion sensor](https://www.itead.cc/sonoff-rf-bridge-433.html) or [RF button](https://www.aliexpress.com/item/86-Wall-Panel-Wireless-Remote-Transmitter-1-2-3-Channel-Sticky-RF-TX-Smart-For-Home/32793117889.html?spm=a2g0s.9042311.0.0.nUq3pZ) or any other RF sensor.

Installation
--------------------
    sudo npm install -g homebridge-mqtt-sonoffrf-receiver


Sample HomeBridge Configuration
--------------------
    {
      "bridge": {
        "name": "HomeBridge",
        "username": "CC:33:3B:D3:CE:32",
        "port": 51826,
        "pin": "321-45-123"
      },

      "description": "",

      "accessories": [
        {
          "accessory": "mqtt-sonoffrf-receiver",
          "name": "Living Room",
          "url": "mqtt://localhost",
          "topic": "tele/sonoff_rf/RESULT",
          "username": "username",
          "password": "password",
          "rfcode": "1..7FFFFF or 'any'",
          "rfkey": "1..16 or 'any'",
          "ondelay": "time in ms while the sensor is active, the default is 10000",
          "accessoryservicetype": "'MotionSensor' (default) or 'StatelessProgrammableSwitch'"
        }
      ],

      "platforms": []
    }

# References
Use [homebridge-mqtt-sonoffrf-transmitter](https://github.com/miskui/homebridge-mqtt-sonoffrf-transmitter) to control RF devices in Homebridge.
