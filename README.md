# ☀️ Monitoreo de Paneles Solares

Sistema de monitoreo de energía solar. El proyecto recolecta datos en tiempo real de un inversor mediante una Raspberry Pi. La Raspberry utiliza **Telegraf** para la recolección, procesamiento e inserción de los datos en la base de datos. Los datos recopilados son almacenados en una base de datos de series temporales **InfluxDB** y mediante ellos se generan visualizaciones en **Grafana**.

## Recolección de datos

Los paneles solares se encuentran conectados a un elevador-inversor para convertir la energía CC a CA y adecuarla para el uso de las cargas conectadas al sistema.


| Paneles | Elevador-Inversor |
| :---: | :---: |
| <img src="assets/paneles.jpg" width="400" alt="paneles">| <img src="assets/inversor-elevador.jpg" width="400" alt="inversor"> |

Mediante el protocolo Modbus sobre RS-485, la Raspberry Pi solicita periódicamente al microcontrolador del inversor para su posterior envío a la VPS e insersión en la base de datos.

| RPI | RPI-Tablero |
| :---: | :---: |
| <img src="assets/rpi-bateria-placa.jpg" width="400" alt="paneles">| <img src="assets/rpi-tablero.jpg" width="400" alt="inversor"> |

## 📊 Visualización

En esta sección se muestran las métricas del sistema y el estado de la Raspberry Pi.

### Paneles de Monitoreo

El dashboard se encuentra disponible: [Monitoreo-Solar](assets/dashboard-monitoreo.json)

#### Estado del Sistema

![Estado](assets/estado-grafana.png)

#### Resumen de Generación y Ahorro
![Resumen](assets/reumen-grafana.png)

#### Gráficas Temporales de las Variables Eléctricas
![Graficas](assets/graficas-grafana.png) 

### Monitoreo de la Raspberry Pi

El dashboard se encuentra disponible: [Monitoreo-RPI](assets/dashboard-rpi.json)

![RPi](assets/rpi-grafana-completa.png)


## 🛠️ Tecnologías Utilizadas

*   **Infraestructura:** Docker.
*   **Base de Datos:** InfluxDB 2.x (Consultas en Flux).
*   **Visualización:** Grafana.
*   **Proxy:** SWAG.
