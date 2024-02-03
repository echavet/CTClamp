This repository is a simple configuration file for ESPHome framework.
It allows to build a firmware for mottramlabs MLP 201077 4 channels current sensor and to integrate sensors into home assistant.

**requirements**

- purchase a [Current Sensor board board](https://www.ebay.co.uk/sch/i.html?_nkw=&_armrs=1&_ipg=&_from=&_ssn=mlabs2018)
  You can look [here]((https://www.mottramlabs.com/esp_products.html) for more info on available boards.
  The configuration file provided in this repository is meant to configure 2 of the 4 channels of the MLP201077 board.
  Of course you can adapt the configuration for your board and used channels.
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

- Then you will have to calibrate your connected sensors
  With process should be done by reading the raw values from sensors having flashed the raw-current-sensor.yaml file.
- Then you will have to flash the final firmware with your calibration data.

**Flashing the final firmware with calibrated sensors**

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
