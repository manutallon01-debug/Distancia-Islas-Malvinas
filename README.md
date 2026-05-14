## Calculadora de Distancia a las Islas Malvinas

Una herramienta web interactiva diseñada para calcular la distancia lineal en kilómetros desde cualquier punto del mapa hasta Puerto Argentino. Islas Malvinas (`-51.7963`, `-59.5236`), utilizando exclusivamente cartografía oficial de la República Argentina.

Este proyecto tiene como objetivo principal la **"malvinización"** y la reafirmación de la soberanía nacional a través del uso de tecnologías cívicas y datos públicos, reemplazando el uso de plataformas internacionales de mapas por servicios soberanos.

Características Principales

* **Cartografía Oficial:** Utiliza la capa base (WMS/TMS) provista por el **Instituto Geográfico Nacional (IGN)**, garantizar la correcta toponimia y representación del territorio nacional.
* **Cálculo Preciso:** Permite medir la distancia exacta mediante tres métodos:
  * 📍 Geolocalización del dispositivo (ubicación actual).
  * 🔍 Búsqueda por dirección postal (Geocoding vía Nominatim).
  * 🖱️ Selección interactiva haciendo clic en cualquier punto del mapa.
* **Trazado Dinámico:** Dibuja una polilínea geodésica entre el punto de origen y las islas, adaptando el zoom automáticamente para visualizar ambos puntos.
* **Diseño Responsivo:** Interfaz adaptada tanto para navegadores de escritorio como para dispositivos móviles, con una estética visual que remite a los colores patrios.

## 🛠️ Tecnologías Utilizadas

* **HTML5 / CSS3 / JavaScript (Vanilla):** Estructura, estilos y lógica del cliente.
* **Leaflet.js (v1.9.4):** Biblioteca de código abierto para mapas interactivos.
* **Servicios de Mapas del IGN:** Consumo de teselas (Tiles) desde `wms.ign.gob.ar`.
* **API Nominatim (OpenStreetMap):** Para la resolución de direcciones a coordenadas (Geocoding).
* **Google Fonts:** Tipografía *Montserrat* para una interfaz moderna y legible.

## 📐 Fundamentos Cartográficos y Metodología de Cálculo

Para garantizar la precisión y la coherencia con los estándares de la República Argentina, la herramienta se diseñó bajo los siguientes lineamientos geomáticos:

### 1. Sistema de Referencia y Capa Base (IGN)
A diferencia de los visores convencionales basados en *Web Mercator* (EPSG:3857) estandarizados por plataformas comerciales, esta herramienta consume las teselas de mapas web del **Instituto Geográfico Nacional (IGN)**.
* **Geoportal Oficial:** Los datos se obtienen de forma soberana mediante los servicios de mapas web oficiales, asegurando la toponimia oficial y la delimitación territorial aprobada por la Ley Nacional de Cartografía N° 22.963.

### 2. Cálculo de Distancia Geodésica (Fórmula del Haversine)
El cálculo de la distancia lineal entre el punto de origen seleccionado por el usuario y el baricentro de las Islas Malvinas (`-51.7963`, `-59.5236`) no se realiza mediante una simple línea recta plana (euclidiana), ya que esto induciría a severas distorsiones debido a la curvatura terrestre.
* **Metodología:** Se utiliza la **Fórmula del Haversine** (implementada a través del método `.distanceTo()` de la API de Leaflet). Este algoritmo matemático calcula la distancia de círculo máximo (ortodrómica) entre dos pares de coordenadas geográficas (latitud y longitud) sobre la superficie de una esfera.
* **Radio Terrestre:** El cálculo toma como referencia el radio medio de la Tierra definido por el elipsoide **WGS 84** ($R \approx 6378137$ metros), lo que permite obtener una precisión milimétrica en la distancia geodésica del arco.

### 3. Representación de la Traza (Línea de Distancia)
* **Visualización:** El trazado que une los puntos se genera mediante un objeto `L.polyline`. En proyectos de escala nacional y continental, esto modela visualmente la trayectoria del arco geodésico directo, permitiendo dimensionar el vector de proximidad real del territorio continental e insular.
* **Ajuste Dinámico de Escala (Bounding Box):** Se utiliza el método `map.fitBounds()`, que calcula dinámicamente la caja de envoltura espacial (*bounding box*) de la polilínea para adaptar el nivel de zoom y el centro del mapa de forma óptima, sin importar si el origen se encuentra en La Quiaca o en Ushuaia.

## ⚙️ Uso e Instalación (Desarrollo Local)

El proyecto no requiere de instalación de dependencias ni servidores complejos. Es completamente un desarrollo *Front-End* estático.

1. Cloná este repositorio en tu equipo:
   ```bash
   git clone [https://github.com/manutallon01-debug/Distancia-Islas-Malvinas.git](https://github.com/manutallon01-debug/Distancia-Islas-Malvinas.git)
   



##  Autor
Desarrollado por Manuel Tallone

Analista GIS y Programador Junior.

Licenciado en Sistemas de Información Geográfica (UNTREF).

Estudiante de la Licenciatura en Geografía (UNTREF).

##  Licencia
Este proyecto está bajo la Licencia GNU General Public License v3.0 (GPLv3).
Podés usar, estudiar y modificar el código fuente. Toda obra derivada o modificación distribuida debe mantener esta misma licencia de código abierto y otorgar el crédito correspondiente al autor original. Revisá el archivo LICENSE para más detalles
