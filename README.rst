Ventulo ESPHome
---------------

Intro
+++++
This repo contains `ESPHome <https://esphome.io/>`_ configuration files
for `ESP32` or `ESP8266` boards which are able to provide smart home control
of `Ventulo heat-recovery units <https://www.ventulo.cz>`_.

Version
+++++++

These config files are not fully finilized yet. They will be modified
in a near future. This `README` is planned to be extended as well.

Instructions
++++++++++++

#) Choose a correct YAML config file variant -- `ESP32` or `ESP8266`.

   If you own a different board than `wemos_d1_uno32` (`ESP32`),
   or `nodemcuv2` (`ESP8266`), make sure you change the `board`
   value in the config.

#) Change a `node_area` value and also name of the YAML file according
   to an area change.

   .. note::

      If u happen to have several Ventulo heat-recovery units in a same area,
      but use ESP device for each one of them, you should append a number to
      an area, so it's named e.g. `kitchen1` as you'll need several YAML
      config files.

#) Create a `secret.yaml` file by copying a `secret.yaml.example`
   file and fill credentials of your Home Assistant WiFi network.


#) If you prefere localized names of entities, check the `substitutions`
   section of the config file.

#) Compile the firmware and flash your ESP device.

   On Linux-based operating systems, this can be done like this:

   .. code::

   # 
   # CONF=kitchen-ventulo-esp32.yaml;
   #
   # Validate the YAML, compile, upload binary and start logs
   # (board is expected to be available under serial interface `ttyUSB0`).
   #
   # $ esphome run --device /dev/ttyUSB0 ${CONF};
   #