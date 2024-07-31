# Consumo Agua v1.0
Codigos necesarios para reproducir lo realizado

## ESPHome
Pasos necesario para cargar el código en el ESP32 mediante ESPHome:
* Instalar ESPHome en su computadora. Pasos a seguir en: https://esphome.io/index.html .
* Se debe descargar la carpeta esp_home, luego dentro del archivo esp_consumo_agua.yaml se debe modificar los parámetros tanto del Wifi al cual se desea conectar, como del broker MQTT a utilizar.
* Conectar el ESP32 a la computadora.
* Abrir una terminal y situarse en la carpeta esp_home.
* Ejecutar el comando ```esphome run esp_consumo_agua.yaml```, el cual va a compilar el programa y al finalizar le va a solicitar en qué puerto está conectado el ESP32.


## Docker
Pasos necesarios para instalar los software necesarios en contenedores de Docker:
* Instalar Docker en su computadora. Pasos a seguir en: https://www.docker.com/
* Descargar carpeta docker en la computadora, desde una terminal se debe colocar en dicha carpeta y ejecutar el comando ```docker-compose up``` y esperar a que instale todas las instancias.

## Mosquitto
Para poder acceder al broker se debe modificar el archivo mosquitto.conf. El mismo se accede desde docker, donde debemos entrar a Volumes y luego en el volumen que contenga el nombre mosquitto_conf, nos encontraremos con el archivo deseado que se le debe agregar las siguientes líneas de codigo:
```
listener 1883  
allow_anonymous true
```

## Node-RED
Para importar el programa realizado en Node-RED se debe:
* En un navegador insertar ```http://localhost:1880/```, el cual te abrirá la interfaz web de node-RED. 
* Inicialmente es necesario instalar los nodos ```node-red-contrib-influxdb``` y ```node-red-dashboard```, los mismos se instalan desde el menú en Administrar Paleta.
* Luego en el menú seleccionar Importar, y seleccionar el archivo ```flows.json``` que está en la carpeta docker descargada.

  Nota: En caso de querer cambiar el huso horario en Node-RED, el mismo se puede hacer abriendo el contenedor nodered instalado en docker, en la pestaña Files buscar el archivo settings.js que se encuentra dentro de la carpeta data y agregar las siguientes líneas:
   ```process.env.TZ = 'Europe/Madrid';  // Si se quiere el horario de Madrid```
