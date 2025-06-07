# DASHBOARD PARA EL MONITOREO DE TANQUES DE GAS

Este proyecto es un dashboard interactivo creado con Node-RED que permite gestionar y monitorear tanques de gas distribuidos en distintas zonas de una ciudad.

## 🚀 Funcionalidades

- Visualización en tiempo real de:
  - **Presión** (PSI)
  - **Nivel** (%)
  - **Concentración de gas** (ppm)
  - **Ubicación del tanque**
- Control de válvulas (abrir/cerrar)
- Activación del sistema de ventilación
- Alertas automáticas en caso de fuga
- Historial de consumo a lo largo del tiempo mediante gráficos
- Información climática de la ciudad actual

## 🧪 Tecnologías utilizadas

- [Node-RED](https://nodered.org/)
- Node.js
- MQTT (con [Mosquitto](https://mosquitto.org/))

## ⚙️ Instalación y ejecución

1. **Clonar el repositorio**

   ```bash
   git clone <url-del-repo>
   cd <carpeta-del-proyecto>
   ```

2. **Instalar dependencias**

   ```bash
   npm install
   ```

3. **Iniciar el dashboard**

   ```bash
   npm run fuego
   ```

   > Esto ejecuta `node-red -p 1880 -u .`

4. Accede a Node-RED desde:  
   [http://localhost:1880](http://localhost:1880)

## 🛠️ Configuraciones necesarias

### MQTT con Mosquitto

Asegúrate de tener instalado Mosquitto MQTT Broker en tu máquina local.

```bash
sudo apt install mosquitto mosquitto-clients
```

Debe estar corriendo en `localhost` (puerto 1883 por defecto).

### Clima - OpenWeather API

1. Abre el flujo de Node-RED.
2. Busca el nodo llamado `Solicitud clima`.
3. Reemplaza el valor de la API Key por una obtenida en [https://openweathermap.org/api](https://openweathermap.org/api).

### Archivos estáticos (imágenes)

El proyecto utiliza imágenes locales (válvula, ventilador, etc.) ubicadas en la carpeta `static`.

Para habilitar el acceso a esa carpeta:

1. Abre el archivo `settings.js` (usualmente ubicado en `~/.node-red/settings.js` o dentro del proyecto).
2. Busca la línea que contiene `httpStatic: '/ruta/...`, y cámbiala por la ruta absoluta de la carpeta `static` del proyecto. Ejemplo:

```js
httpStatic: "/home/usuario/tu-proyecto/static",
```

3. Reinicia Node-RED para aplicar los cambios.

## 🖼️ Diseño
### Vista general del dashboard

![Dashboard](./archivos/Dashboard%20inicial.png)

### Historial de consumo de gas

![Historial de consumo](./archivos/Historial%20de%20consumo.png))

## 📄 Licencia

MIT – Libre para uso personal y académico.

## 🤝 Autor

Proyecto desarrollado por Kenneth Romero y Jordan Quijie.