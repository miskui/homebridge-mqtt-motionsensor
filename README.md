# homebridge-mqtt-sonoffrf-motionsensor

Get Motion Sensor status via MQTT in Homebridge.
Sensor becomes active if received RF code matches for rfcode or RF key stored in Sonoff RF.

Installation
--------------------
    sudo npm install -g homebridge-mqtt-sonoffrf-motionsensor


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
          "accessory": "mqtt-sonoffrf-motionsensor",
          "name": "Living Room",
          "url": "mqtt://localhost",
          "topic": "tele/sonoff_rf/RESULT",
          "username": "username",
          "password": "password",
          "rfcode": "code hex",
          "rfkey": "1..16"
        }
      ],

      "platforms": []
    }

Contributions Welcome!
--------------------
