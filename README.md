# update_all_esphome_script
A script to update all ESPHome Projects in Background with a single service-call in Home Assistant


# Aufruf des Scripts (als Dienstaufruf für z.B. Automatisierungen oder Tap-Actions)
```
service: script.update_all_esphome_devices
data:
  notifier: notify.mobile_app_pixel_7_pro_daniel
```

# Button Beispiel
```
show_name: true
show_icon: true
type: button
name: Update All ESPHome
tap_action:
  action: call-service
  service: script.update_all_esphome_devices
  target: {}
  data: 'notifier: notify.mobile_app_pixel_7_pro_daniel'
entity: binary_sensor.update_info
```


![image](https://github.com/SmartHome-yourself/update_all_esphome_script/assets/705724/615769f2-4852-423d-834c-199b1d80c86c)
