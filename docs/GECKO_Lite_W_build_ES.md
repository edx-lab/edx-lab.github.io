# GECKO Lite W | EDX_LAB
## Archivos de impresión 3D y guía de fabricación (ES)

**Proyecto:** GECKO Lite W — Compact Wireless Security Tool  
**Creador:** EduSicilia | EDX_LAB  
**Web oficial y documentación central:** **https://edx-lab.github.io/**  
**Código fuente y documentación del firmware:** https://github.com/edx-lab/GECKO-Lite-W  
**Firmware oficial v1.0.0:** https://github.com/edx-lab/GECKO-Lite-W/releases/tag/v1.0.0

> **IMPORTANTE:** Este ZIP contiene los modelos 3D para fabricar la carcasa de GECKO Lite W. **No incluye componentes electrónicos físicos.** La web de EDX_LAB es el punto de referencia para documentación, lista de materiales, descargas y novedades.

## 1. ¿Qué es GECKO Lite W?

GECKO Lite W es un dispositivo portátil basado en ESP32-S3, con pantalla en color y controles físicos, pensado para la experimentación y el análisis de seguridad de redes inalámbricas **en entornos propios o expresamente autorizados**. Utiliza una adaptación del firmware Bruce para este hardware concreto. El diseño de la carcasa está preparado para impresión 3D FDM y puede modificarse a partir de los archivos STEP.

### Especificaciones del dispositivo

| Elemento | Especificación |
| --- | --- |
| Microcontrolador | ESP32-S3 N16R8 |
| Memoria | 16 MB Flash + 8 MB PSRAM |
| Conectividad | Wi-Fi y Bluetooth Low Energy integrados |
| Pantalla | TFT SPI ST7789V de 2,0", resolución física 240 × 320 píxeles; interfaz horizontal 320 × 240 |
| Controles | Joystick de 5 direcciones, pulsador central, 2 botones adicionales |
| Almacenamiento | Lector microSD SPI (bus independiente de la pantalla) |
| Batería | LiPo 3,7 V, 800 mAh, formato 802540 |
| Carga | Módulo de carga USB-C independiente |
| Alimentación | Módulo elevador DC-DC y circuito de filtrado |
| Avisos | Buzzer pasivo |
| Firmware | GECKO Lite W v1.0.0, basado en Bruce |
| Fabricación de la carcasa | Impresión 3D FDM/FFF |

Estas especificaciones corresponden al diseño GECKO Lite W documentado; no garantizan compatibilidad con otros ESP32-S3, pantallas ni módulos aparentemente similares.

## 2. Contenido de la descarga

- **Archivos STL:** piezas de la carcasa para preparar la impresión en un laminador.
- **Archivos STEP/STP:** geometría CAD editable para adaptar el diseño.
- **Este README:** guía de fabricación, montaje, seguridad y enlaces oficiales.

Consulta las carpetas y nombres reales de los archivos del paquete. El firmware y su código fuente se distribuyen **por separado en GitHub**. La lista de materiales con fotografías y enlaces de compra (BOM en español e inglés) se consulta en la web oficial; puede distribuirse también como documentación adicional.

## 3. Componentes electrónicos necesarios

El montaje utiliza los siguientes componentes principales (una unidad de cada uno):

1. ESP32-S3 N16R8 (16 MB Flash, 8 MB PSRAM).
2. Pantalla TFT SPI de 2 pulgadas con controlador ST7789V.
3. Batería LiPo 802540 de 3,7 V y 800 mAh.
4. Módulo de joystick de 5 vías y 2 botones SET/RST.
5. Módulo cargador de batería LiPo USB-C.
6. Interruptor deslizante miniatura de encendido/apagado.
7. Convertidor DC-DC elevador (*step-up*).
8. Lector microSD SPI y tarjeta microSD compatible.
9. Buzzer pasivo de dos terminales.

**Componentes adicionales:** cables, conexiones y material de fijación; condensadores de **100 nF + 10 µF** en paralelo a la salida del step-up; divisor de medida de batería con **dos resistencias de 100 kΩ y un condensador de 100 nF** desde el punto medio a GND. Comprueba los valores, la disposición y las conexiones en la documentación técnica antes de soldar.

**BOM ilustrada y enlaces a los módulos exactos:** https://edx-lab.github.io/

## 4. Ajustes recomendados de impresión

| Ajuste | Recomendación inicial |
| --- | --- |
| Tecnología | FDM / FFF |
| Material | PLA o PETG |
| Diámetro de boquilla | 0,4 mm |
| Altura de capa | 0,20 mm |
| Perímetros | 4 líneas como punto de partida |
| Capas superiores e inferiores | 5 |
| Relleno | 30 % giroide |
| Soportes | Solo si el análisis de la pieza y su orientación los requieren |
| Orientación | Elegir la superficie de apoyo más estable, cuidando los acabados visibles y los huecos funcionales |
| Tiempo y consumo | Dependen del laminador, el material y la impresora; calcular antes de imprimir |

Estos parámetros son **recomendaciones**, no un perfil de impresión validado para todas las impresoras. El espesor real de las paredes procede del modelo CAD y **no equivale necesariamente** al número de perímetros del laminador. No escales las piezas: altera sus tolerancias y los alojamientos de los módulos.

## 5. Montaje y comprobaciones

1. **Antes de imprimir:** abre todos los STL en tu laminador, comprueba que el conjunto esté completo, revisa orientación y posibles soportes. No cambies la escala.
2. **Imprime las piezas:** utiliza el mismo perfil/material cuando necesites mantener encajes consistentes. Deja enfriar las piezas antes de retirarlas de la cama.
3. **Acabado:** retira soportes si los hubiera y limpia con cuidado orificios, pestañas, ranuras y superficies de contacto. No fuerces las piezas.
4. **Presentación en seco:** coloca temporalmente pantalla, ESP32-S3, joystick, microSD, interruptor, batería y módulos auxiliares; verifica espacio libre para cables, conectores y cierre antes de fijar o soldar.
5. **Cableado:** realiza las conexiones conforme al esquema/pinout de GECKO Lite W; presta especial atención a masa común, alimentación, polaridad y a los cables de la batería. No alimentes el equipo hasta revisarlo.
6. **Comprobación eléctrica:** con la batería desconectada, inspecciona soldaduras, continuidad, ausencia de cortocircuitos y tensión de salida configurada del convertidor DC-DC. Emplea un multímetro; no presupongas que el módulo viene ajustado a la tensión correcta.
7. **Primera puesta en marcha:** prueba pantalla, joystick, botones, microSD, buzzer y lectura de batería antes de cerrar la carcasa definitivamente.
8. **Cierre:** organiza el cableado sin atraparlo entre piezas; asegura la batería sin perforarla, comprimirla ni apoyar bordes agresivos sobre ella. Cierra con los elementos de fijación previstos por tu versión impresa.
9. **Firmware:** descarga la versión oficial y sigue las instrucciones de instalación incluidas en la publicación de GitHub.

### Referencia rápida del pinout del firmware v1.0.0

| Señal | GPIO |
| --- | --- |
| TFT: CLK / MOSI / CS / DC / RST | 12 / 11 / 10 / 9 / 8 |
| microSD: CLK / MOSI / MISO / CS | 14 / 13 / 16 / 15 |
| Joystick: arriba / abajo / izquierda / derecha | 4 / 5 / 6 / 7 |
| Pulsador central joystick | 21 |
| B1 / SET | 17 |
| B2 / RST | 18 |
| Lectura batería ADC | 1 (punto medio del divisor 100 kΩ / 100 kΩ) |
| Buzzer | 38 |

Los controles se activan contra GND con resistencias *pull-up* internas. El pin **BL de la pantalla está conectado a 3,3 V** en este diseño. Este cuadro **no sustituye al esquema de cableado completo**. Consulta la documentación actualizada del repositorio antes de conectar la electrónica.

## 6. Firmware y primera instalación

El firmware no forma parte necesariamente de este ZIP de piezas impresas. Descárgalo aquí:

**https://github.com/edx-lab/GECKO-Lite-W/releases/tag/v1.0.0**

Para una primera instalación se utiliza el binario combinado **`Gecko-esp32-s3-n16r8.bin`**, grabado en la dirección **`0x0`**, según la guía oficial de instalación. **`firmware.bin` es solo la aplicación y no se graba en `0x0`.** Sigue íntegramente `INSTALACION.md` de la publicación para conocer comandos, puertos, actualización y advertencias sobre los ajustes guardados en memoria.

## 7. Seguridad y uso responsable

**Batería y carga**
- Utiliza una batería LiPo y un módulo cargador apropiados. Respeta polaridad, límites de tensión y corriente y las recomendaciones del fabricante.
- No cortocircuites, perfores, aplastes, deformes ni calientes la batería. Si se hincha, desprende olor o presenta daños, deja de utilizarla y gestiona su reciclaje de forma segura.
- No cargues el dispositivo sobre superficies inflamables ni lo dejes desatendido durante las pruebas iniciales. Comprueba el funcionamiento del circuito de carga antes del uso habitual.
- No confundas el módulo cargador con una protección universal: verifica las protecciones reales de la batería y del circuito que has adquirido.

**Electrónica e impresión**
- Desconecta alimentación y batería antes de manipular cables, soldaduras o módulos. Evita cortocircuitos, polaridad inversa y contacto de componentes energizados con herramientas metálicas.
- Una carcasa impresa en PLA/PETG no constituye por sí misma aislamiento eléctrico certificado ni protección térmica, contra agua o golpes.
- Mantén el dispositivo fuera del alcance de niños pequeños. Contiene piezas pequeñas y una batería de litio.
- No es un producto certificado ni apto para aplicaciones médicas, industriales críticas o de protección personal.

**Seguridad inalámbrica y normativa**
- Las capacidades de análisis y prueba del firmware se deben utilizar **solo con equipos y redes propios o con autorización expresa**.
- Algunas funciones pueden afectar a la disponibilidad de redes o dispositivos. Respeta la legislación aplicable y no realices interferencias, capturas ni pruebas invasivas en sistemas ajenos.
- El usuario es responsable del montaje, de la seguridad eléctrica y del uso legal del dispositivo.

## 8. Soporte, comunidad y redes oficiales

**Toda la información, documentación y novedades de EDX_LAB:**  
https://edx-lab.github.io/

**Código fuente, incidencias técnicas y versiones de firmware (GitHub):**  
https://github.com/edx-lab/GECKO-Lite-W

**Perfil del creador en Cults3D:** busca **EduSicilia**.  
**Redes sociales y otros canales:** utiliza los enlaces publicados en la **web oficial de EDX_LAB** para acceder a los perfiles auténticos y actualizados. No atribuyas al proyecto cuentas no enlazadas oficialmente.

Para consultas sobre montaje, indica el modelo de placa y pantalla, versión del firmware, síntoma y fotografías claras de las conexiones cuando resulte necesario. Antes de publicar una incidencia, revisa la documentación y las preguntas existentes en el repositorio.

## 9. Modificaciones y distribución

Los archivos STEP permiten adaptar la carcasa para uso personal o proyectos derivados. No se garantiza que las modificaciones mantengan tolerancias, compatibilidad, resistencia o seguridad. Conserva los créditos **EduSicilia | EDX_LAB** cuando compartas el origen del diseño.

**Licencias:** consulta las condiciones indicadas en la ficha de Cults3D y en cada repositorio o archivo de origen. **La licencia del firmware no debe darse por idéntica a la licencia de los modelos 3D.** El firmware Bruce y los componentes de terceros conservan sus avisos y licencias correspondientes.

---

**GECKO Lite W | EDX_LAB**  
**WEB OFICIAL: https://edx-lab.github.io/**  
Gracias por construir, estudiar y mejorar proyectos abiertos al aprendizaje.
