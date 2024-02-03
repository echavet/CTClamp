This repository is a simple configuration file for ESPHome framework.
It allows to build a firmware for mottramlabs MLP 201077 4 channels current sensor and to integrate sensors into home assistant.


**requirements**
- [install esphome](https://esphome.io/guides/installing_esphome.html#)
- Create a secrets.yaml file with 
```yaml
wifi_ssid: "your SSID"
wifi_password: "your wifi psk"
wifi_ssid2: "RICO'S-NET-5G"

ota_pwd: your password
encryption_key: "an encryption key"
```

You can generate a project with
```
esphome wizard my_file.yaml
```

And the get the encryption key from the generated config file. Leave generated file. You don't need it anymore. Just use the current-sensor.yaml from this repository.

- Then launch
```
esphome compile current-sensor.yaml
```
to build the firmware, and 
- then launch
```
esphome upload current-sensor.yaml
```
to flash your ESP8266 Wemos D1 controler 
