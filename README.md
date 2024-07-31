# Consumo Agua v1.0
Codigos necesarios para reproducir le realizado

## ESPHome
Pasos necesario para cargar el codigo en el ESP32 mediante ESPHome:
* Instalar ESPHome en su computadora, se puede ver desde https://esphome.io/index.html .
* Se debe decargar la carpeta esp_home, luego dentro del archivo esp_consumo_agua.yaml se debe modifcar los parametros tanto del Wifi al cual se desea conectar, como del broker MQTT a utilizar.
* Conectar el ESP32 a la computadora.
* Abrir una terminal y situarse en la carpeta esp_home.
* Ejecutar el comando 'esphome run esp_consumo_agua.yaml', el cual va a compilar el programa y al finalizar le va solicitar en que puerto esta conectado el ESP32.
