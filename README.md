# homebridge-mqtt-sonoffrf-receiver

Get Motion Sensor status via MQTT in Homebridge.
Sensor becomes active if received RF code matches for rfcode or RF key stored in Sonoff RF device.

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
          "rfcode": "code hex or 'any'",
          "rfkey": "1..16 or 'any'"
        }
      ],

      "platforms": []
    }

Contributions Welcome!
--------------------
