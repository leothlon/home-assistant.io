---
layout: page
title: "TellStick"
description: "Instructions on how to integrate your TellStick into Home Assistant."
date: 2015-03-28 13:06
sidebar: true
comments: false
sharing: true
footer: true
logo: telldus_tellstick.png
ha_category: Hub
---

The `tellstick` component integrates [TellStick](https://telldus.com/produkt/z-wave-gateway-tellstick-znet-lite-ver-2/) devices into Home Assistant. This integration allows users to add switches, lights, and sensors which are communicating with 433 MHz. There are a number of vendors (Capidi Elro, Intertechno, Nexa, Proove, Sartano, and Viking) who are selling products that work with TellStick. For more details, please check the TellStick [protocol list](http://developer.telldus.com/wiki/TellStick_conf).

## {% linkable_title Configuration %}

To get started, add the devices to your `configuration.yaml` file.

```yaml
# Example configuration.yaml entry
tellstick:
```

For Hass.io users there is a [TellStick add-on](/addons/tellstick/) available.

```yaml
# Example configuration.yaml entry for Hass.io with the TellStick add-on
tellstick:
  host: core-tellstick
  port: [50800, 50801]
```

{% configuration %}
signal_repetitions:
  description: Because the TellStick sends its actions via radio and from most receivers it's impossible to know if the signal was received or not. Therefore you can configure the switch and light to try to send each signal repeatedly.
  required: false
  type: integer
  default: 1
host:
  description: If you run TellStick on another server or with the Hass.io add-on.
  required: inclusive
  type: string
port:
  description: Needed with the `host` configuration variable. Must be port pair, for example `[50800, 50801]`.
  required: inclusive
  type: list
{% endconfiguration %}
