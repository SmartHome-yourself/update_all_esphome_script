# Alle ESPHome Projekte mit einem Klick im Hintergrund aktualisieren
Bei diesem Projekt handelt es sich um ein Script für Home Assistant, mit dem sich alle ESPHome Projekte automatisch nacheinander aktualisieren lassen. 
Der Vorteil gegenüber dem "Update All" Button in der ESPHome Oberfläche ist, dass die Updates hier im Hintergrund erfolgen.  
  

## Video zum Script
[<img src="https://github.com/SmartHome-yourself/update_all_esphome_script/assets/705724/15e4fb74-1c68-4744-8d16-2633c870a18c" width="500px">](https://www.youtube.com/watch?v=Ob49k5rt9gQ)
  
## Fehler beim Update   
Sollte beim Update eines ESPHome Projektes ein Fehler auftreten, wird dieser in den Home Assistant-Benachrichtigungen hinterlegt.   
[<img src="https://github.com/SmartHome-yourself/update_all_esphome_script/assets/705724/615769f2-4852-423d-834c-199b1d80c86c" width="600px">](https://github.com/SmartHome-yourself/update_all_esphome_script/assets/705724/615769f2-4852-423d-834c-199b1d80c86c)   
   
   
# Einrichtung   
Der Inhalt der Datei `update_all_esphome_script.yaml` kann als [Package-Datei in die Home Assistant Config](https://www.youtube.com/watch?v=wZ1Qd0wDY8Y) übernommen werden. (empfohlen)   
Wer keine Packages nutzt, muss die Inhalte entsprechend [in seiner configuration.yaml integrieren](https://www.youtube.com/watch?v=9LEoRc30LMU).   
   
   
### Aufruf des Scripts (als Dienstaufruf für z.B. Automatisierungen oder Tap-Actions)   
```
service: script.update_all_esphome_devices
data:
  notifier: notify.mobile_app_pixel_7_pro_daniel
```   
   
   
### Button Beispiel   
Das Update-Script lässt sich bequem über einen Button starten.   
So kann man darüber mit einem Klick all seine ESPHome Geräte im Hintergrund nacheinander aktualisieren lassen.   
      
**Update vorhanden**    
<img src="https://github.com/SmartHome-yourself/update_all_esphome_script/assets/705724/50ed7a62-fb30-4d9f-9f2f-63cfaa6c8fb8" width="400px">
   
**Kein Update vorhanden:**   
<img src="https://github.com/SmartHome-yourself/update_all_esphome_script/assets/705724/f2cb8aa5-7911-4ff2-909b-f06be408f676" width="400px">
   
   
```
type: button
show_name: true
show_icon: true
name: Update All ESPHome
tap_action:
  action: call-service
  service: script.update_all_esphome_devices
  target: {}
  data: 'notifier: notify.mobile_app_pixel_7_pro_daniel'
entity: binary_sensor.update_info
```

