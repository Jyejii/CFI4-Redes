# CFI4-Redes
https://github.com/Jyejii/CFI4-Redes.git
------------------------------------------
# 1.Diseño y Modelado.
## Modelo OSI y TCP/IP 
-	Modelo OSI
1.	Capa Física	Encargado de la transmisión real de bits a través de medios físicos, por ejemplo: cables, wifi. En esta capa se hacen los cálculos de capacidad de canal (fórmula de Shannon).
2.	Capa de Enlace de datos	Colabora la transmisión libre de errores entre nodos, gestiona el direccionamiento a nivel de hardware como las direcciones MAC y se encarga del control de acceso al medio 
3.	Capa de Red	Distribuye el direccionamiento lógico y la toma de decisiones de enrutamiento, por ejemplo, el subneteo y esquema de rutas.
4.	Capa de Transporte	Se encarga de ejecutar una entrega confiable o en tiempo real, UDC y TCP.
5.	Capa de Sesión	Establece, administra y finaliza conexiones entre aplicaciones, para la gestión de diálogos entre diferentes sistemas.
6.	Capa de Presentación	Representa y codifica los datos, haciendo el cifrado, compresión y transformación de diferentes formatos.
7.	Capa de Aplicación	Se comunica directamente con los programas que utiliza el usuario, por ejemplo, protocolos FTP/SFTP para transferir archivos, HTTP/HTTPS para los de multimedia, etc...

-	Modelo TCP/IP
1.	Capa de Acceso a Red	Sería igual que la capa física y enlace de datos en el modelo OSI. Se encarga de la transmisión de datos a nivel de hardware y de la comunican por medio físicos como el ethernet. 
2.	Capa de Internet	Se asemeja a la capa de red del modelo OSI. En este se gestiona las direcciones IP y el enrutamiento, por ejemplo, el algoritmo de DIjkstra.
3.	Capa de Transporte	Parecida a la capa de transporte del modelo OSI. Gestiona los servicios de transporte ya sea confiable o sin conexión, TCP y UDP.
4.	Capa de Aplicación	Equivalen a las capas 5, 6 y 7 del modelo OSI. Protocolos de trasnferencia, FTP y SFTP, manejo de contenidos HTTP y HTTPS, etc...

## Diagrama
![](https://github.com/Jyejii/CFI4-Redes/blob/main/Captura%20de%20pantalla%202025-05-13%20020159.png)
![](https://github.com/Jyejii/CFI4-Redes/blob/main/Captura%20de%20pantalla%202025-05-13%20014846.png)
<p>como se puede observar, se separa la red en dos partes,la de seguridad,medioambiente y trafico que contiene un firewall y un anillo de switches sencillo cada uno con sus respectivos dispositivos, como camaras,semaforos y alarmas. Por el otro lado se puede ver los edificios gubernamentales como oficinas, ayuda al ciudadano y sala multimedia, para acceder a este parte se pasa por una zona desmilitarizada que contiene servidores como el FTP,Web y email,despues conecta un anillo de switches que conectan las salas de oficina,ayuda al cliente que contienen pcs, un acces point y un telefono,sala audiovisual que contiene una pcs,acces point,telefono,camara y micrófono.<p>
  
-------------------------------------------------------
# 1.Capa Física
## Capacidad de los enlaces
Capa Fisica 
Usamos la formula de Shannon:<br>
Un buen nivel de de SNR para tanto cableado como inalámbrico seria de 35Db<br>
SNR lineal= 10^(SNR/10)		Shannon= C=B*log₂* (1+SNR)<br>
SNR lineal =10^((35/10) )=3162.2<br>

Para el sistema inalámbrico B=100*10^6<br>
C = 100 * 10^6 * log₂(1 + 3162.2) = 1162.7 Mbps
<br>
Para el sistema cableado B=80*10^6<br>
C=80*10^6*log₂ (1+3162.2)=930.1 Mbps<br>
## Selección de modulación
Para la modernización de la infraestructura de comunicaciones de una ciudad inteligente, se comparan las siguientes técnicas de modulación:

BPSK: Baja eficiencia espectral (1 bit/símbolo) pero alta robustez ante interferencias. Ideal para enlaces inalámbricos en entornos ruidosos y de emergencia.

QPSK: Mejora la eficiencia (2 bits/símbolo) con moderada robustez. Adecuada para enlaces inalámbricos que requieren mayor velocidad pero sin alta interferencia.

16-QAM: Alta eficiencia espectral (4 bits/símbolo) y adecuada para enlaces de alta capacidad. Menos robusta ante interferencias, ideal para enlaces cableados controlados.

64-QAM: Muy alta eficiencia (6 bits/símbolo), adecuada para enlaces de alta velocidad, pero requiere condiciones ideales de señal. Utilizable en enlaces cableados de alta capacidad.

Uso:

Enlaces Cableados: 16-QAM o 64-QAM para alta capacidad.

Enlaces Inalámbricos: BPSK o QPSK para mayor robustez en entornos ruidosos.
## Selección de Modulación y Evaluación de Encapsulamiento

Se hará uso del método OFDM, usando WiFi 5/6 y 5G, que permite transmisión eficiente con múltiples usuarios y baja interferencia.

**Encapsulamiento:**  
Se envían 1000 bytes incluyendo:  
- Cabecera TCP = 20 bytes  
- Cabecera IP = 20 bytes  
- Cabecera MAC (802.11) = 34 bytes  
- Tráiler (FCS y otros) = 4 bytes  
**Sobrecarga:** 78 bytes  
**Eficiencia:**  
\[ Eficiencia = 1000/(1000 + 78) = 92.8%]  
Sobrecarga: 7.2%
----------------------------------------------
# Capa de Red 
## Diseño de esquema y direccionamiento IP
Se asignarán bloques de direcciones IPv4 en base a la necesidad de cada segmento, generalmente comenzando con una red más grande para áreas con más dispositivos.<br>
`Zona Gubernamental (10.0.0.0/24):`

Dirección de red: 10.0.0.0

Dirección de Broadcast: 10.0.0.255

Rango de hosts: 10.0.0.1 – 10.0.0.254`

`Servicio Transporte, Ambiental y Seguridad (10.0.1.0/24):`

Dirección de red: 10.0.1.0

Dirección de Broadcast: 10.0.1.255

Rango de hosts: 10.0.1.1 – 10.0.1.254

`Atención Ciudadana (10.0.2.0/24):`

Dirección de red: 10.0.2.0

Dirección de Broadcast: 10.0.2.255

Rango de hosts: 10.0.2.1 – 10.0.2.254

`Oficinas (10.0.3.0/24):`

Dirección de red: 10.0.3.0

Dirección de Broadcast: 10.0.3.255

Rango de hosts: 10.0.3.1 – 10.0.3.254

`Sala Multimedia (10.0.4.0/24):`

Dirección de red: 10.0.4.0

Dirección de Broadcast: 10.0.4.255

Rango de hosts: 10.0.4.1 – 10.0.4.254

`Servidores Internos (10.0.5.0/24):`

Dirección de red: 10.0.5.0

Dirección de Broadcast: 10.0.5.255

Rango de hosts: 10.0.5.1 – 10.0.5.254

## Enrutamiento y rutas dinámicas.
El algoritmo de dijkstra busca la ruta mas corta entre los diferentes nodos de la red, en el caso del camino de zona de seguridad y zona de emergencias, la mejor opción seria el acceso directo ya que se encuentran en un anillo de 3 switches.
El enrutamiento por inundación o flooding, el protocolo inunda toda la red de paquetes y encuentra la ruta mas óptima,es útil como respaldo pero a largo plazo no es viable debido a la sobrecarga generada.Por lo que se puede usar como ruta de reespaldo si el protocolo principal falla.

# Capa de transporte
## Selección de protocolo de transporte
El uso de TCP (Protocolo de Control de Transmisión) para servicios que requieren alta fiabilidad, como la transferencia de archivos o actualizaciones de bases de datos, y el uso de UDP (Protocolo de Datagramas de Usuario) para servicios en tiempo real, como el streaming de cámaras o alertas de tráfico, se justifica en función de las características y necesidades de cada tipo de servicio.<br>
TCP:
| Característica                       | Explicación                                                                                                                                     |
|---------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| **Fiabilidad y Control de Errores**   | Garantiza la entrega ordenada y sin errores de los datos, fundamental para la transferencia de archivos y actualizaciones de bases de datos.   |
| **Confirmación de Recepción**         | Asegura que los datos han llegado correctamente al destino antes de continuar con la transmisión.                                               |
| **Control de Congestión y Flujo**     | Ajusta la cantidad de datos enviados para evitar la sobrecarga de la red, garantizando la eficiencia en servicios críticos.                    |
| **Reensamblaje y Recuperación**       | Permite la retransmisión de paquetes perdidos, asegurando que no se pierdan datos en aplicaciones críticas como la transferencia de archivos.  |

UDP:
| Característica                        | Explicación                                                                                                                         |
|----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| **Bajo Retardo**                       | UDP reduce significativamente la latencia, lo cual es esencial en servicios en tiempo real como el streaming de cámaras y alertas.  |
| **Mayor Eficiencia en el Ancho de Banda** | UDP es más ligero y eficiente al no tener mecanismos de control, lo que permite un uso óptimo del ancho de banda para datos en tiempo real. |
| **Tolerancia a la Pérdida de Paquetes** | La pérdida de algunos paquetes no afecta mucho a la calidad del servicio en tiempo real, como en el caso de alertas de tráfico o video en vivo. |
| **Simplicidad en la Implementación**   | UDP es más sencillo de implementar, lo que mejora el rendimiento de aplicaciones en tiempo real sin sobrecargar los recursos de procesamiento. |

## Calculo tamaño de ventana TCP

### Cálculo del Tamaño de Ventana en TCP

**Fórmula:**
Ventana óptima = Ancho de banda X RTT

#### Parámetros:
- **RTT** = 50 ms = 0.05 segundos
- **MSS** = 1,500 bytes
- **Ancho de banda** = 1 Mbps = 1,000,000 bps

#### Paso 1: Convertir RTT a segundos
50ms = 0.05segundos
#### Paso 2: Calcular la ventana óptima en bits
Ventana óptima = 1,000,000bps X 0.05 segundos = 50,000 bits
#### Paso 3: Convertir la ventana óptima a bytes
50,000 bits / 8 = 6,250 bytes
#### Paso 4: Calcular el número de segmentos MSS
6,250bytes / 1,500 bytes = 4.17 = 4 segmentos MSS
Con un RTT de 50 ms y un ancho de banda de 1 Mbps, **4 segmentos MSS** pueden estar en tránsito simultáneamente.

# Capa de aplicación
## Implementación de Servicios y Resolución de Nombres

### Servicios Configurados

### DNS
- Ubicación: Zona de servidores internos.
- Función: Resolución de nombres internos (`*.ciudadinteligente.local`) y externos mediante reenviadores.
- Puerto: UDP/TCP 53

### SFTP
- Ubicación: Servicios gubernamentales.
- Función: Transferencia segura de archivos.
- Puerto: TCP 22

### 🧾 HTTP/HTTPS
- Ubicación: Servicios gubernamentales y sala multimedia.
- Función: Portal ciudadano, monitoreo y servicios multimedia.
- Puertos: TCP 80 / 443

### Proceso de Resolución de Nombres

1. El cliente consulta el DNS local.
2. El DNS responde con la IP correspondiente.
3. Si no existe en la zona local, reenvía a servidores externos.
4. El cliente se conecta al servicio deseado (web, FTP, etc.).

### Multiplexación de Solicitudes

- **HTTP/2:** Manejo de múltiples flujos sobre una sola conexión.
- **SFTP:** Sesiones paralelas por usuario.
- **NAT/PAT:** Traducción de puertos para gestionar múltiples accesos desde Internet.

### Conectividad

- Segmentación por zonas: transporte, multimedia, oficinas, atención ciudadana.
- Interconexión mediante switches y routers.
- Seguridad y control de tráfico vía firewall y VLANs.

##  Servicios Multimedia

### Métodos de Transmisión

Para la transmisión de video en tiempo real desde cámaras de seguridad y eventos públicos se emplearán:

- **UDP Streaming (RTP sobre UDP):**
  - Ideal para CCTV y vigilancia en tiempo real.
  - Menor latencia.
  - Tolerancia a pequeñas pérdidas de paquetes.

- **Adaptive HTTP Streaming (DASH):**
  - Utilizado para eventos públicos y contenidos accesibles desde el portal web.
  - Segmenta el video en fragmentos y ajusta la calidad según el ancho de banda.
  - Compatible con HTTP/HTTPS, sin necesidad de protocolos especiales.

### Adaptación Dinámica de Calidad

- **Medición Continua del Ancho de Banda:**
  - El cliente mide la velocidad de descarga de fragmentos (en DASH).
  - En UDP, el servidor puede disminuir la tasa de bits si detecta pérdida de paquetes.

- **Escalado de Resolución y Bitrate:**
  - Perfiles de calidad: 1080p, 720p, 480p.
  - Cambio automático entre perfiles dependiendo del rendimiento de red del cliente.

- **Buffer Dinámico:**
  - DASH utiliza buffers para prevenir interrupciones durante cambios de calidad.
  - Se prioriza fluidez sobre resolución en redes inestables.

### Ejemplos de Uso

- **Cámaras de tráfico/seguridad:** UDP para menor latencia en centros de control.
- **Eventos públicos / transmisiones web:** DASH para escalabilidad y soporte multiplataforma.

# Capa de seguridad
##  Políticas y Medidas de Seguridad

###  Conectividad Segura mediante VPN

- **Segmentos Protegidos:**
  - Enlace cifrado entre el centro de control de emergencias (transporte y seguridad) y oficinas gubernamentales.
- **Tecnología:** VPN IPSec Site-to-Site.
- **Propósito:** Evitar exposición de datos sensibles en tránsito (ej. monitoreo ambiental, videovigilancia, datos ciudadanos).
- **Autenticación y Cifrado:**
  - IKEv2 con certificados.
  - AES-256 para cifrado de túneles.

---

###  Firewalls y Listas de Control de Acceso (ACLs)

#### 1. **Firewall Perimetral (en cada zona con Internet)**
- **Reglas:**
  - Permitir tráfico saliente HTTP/HTTPS, DNS y VPN.
  - Bloquear accesos entrantes no autorizados desde Internet.
  - Permitir solo puertos específicos hacia servidores (TCP 443, 22, etc.).

#### 2. **ACLs en Switches/Routers Internos**
- **Ejemplo de reglas:**
  - `deny ip any 192.168.10.0 0.0.0.255` → Evita que zonas públicas accedan a servidores internos.
  - `permit ip 192.168.20.0 0.0.0.255 any` → Permite acceso desde oficinas a recursos compartidos.
  - `deny ip any any log` → Última regla para registrar intentos bloqueados.

---

###  Monitoreo y Auditoría

- **Sistemas de registro (syslog):** Captura de eventos de red y alertas de seguridad.
- **IDS/IPS:** Detección de intrusos y patrones de ataque (Snort, Suricata).
- **Actualizaciones regulares:** Aplicación de parches de seguridad en todos los dispositivos.

---

###  Aislamiento de Zonas

- **Segmentación mediante VLANs:** Transporte, servidores, oficinas, multimedia.
- **Acceso entre zonas controlado con ACLs y firewall.**
- **Dispositivos IoT aislados y sin acceso a zonas críticas.**

## Cifrado y autentificacion

---

##  Implementación de Servicios y Resolución de Nombres

### Servicios Configurados

- **DNS:** Servidor interno para `*.ciudadinteligente.local`, con reenvío a DNS externos.  
  - 🔌 Puerto: UDP/TCP 53
- **SFTP:** Transferencia segura de archivos.  
  - 🔌 Puerto: TCP 22
- **HTTP/HTTPS:** Portal web y multimedia para ciudadanos y administradores.  
  - 🔌 Puertos: TCP 80 / 443

### Resolución de Nombres

1. El cliente consulta al DNS interno.
2. Si el nombre está en la zona local, responde directamente.
3. Si no, reenvía a un servidor externo.
4. El cliente accede al servicio usando la IP obtenida.

### Multiplexación

- **HTTP/2:** Múltiples solicitudes en una sola conexión.
- **SFTP:** Soporte de sesiones concurrentes.
- **NAT/PAT:** Traducción de puertos para múltiples clientes y servicios.

---

## Servicios Multimedia

### Métodos de Transmisión

- **UDP Streaming (RTP):** Para videovigilancia en tiempo real (baja latencia).
- **DASH (Adaptive HTTP Streaming):** Para eventos públicos y contenido multimedia en la web.

### Adaptación de Calidad

- Evaluación del ancho de banda por parte del cliente.
- Cambio dinámico de resolución y tasa de bits (1080p, 720p, 480p).
- Uso de buffers para evitar interrupciones (en DASH).

---

## Políticas y Medidas de Seguridad

### VPN entre Zonas Críticas

- VPN IPSec Site-to-Site entre oficinas gubernamentales y centros de control.
- Autenticación con IKEv2 y cifrado AES-256.

### Firewalls y ACLs

#### Firewall Perimetral

- Permitir solo tráfico esencial (HTTPS, DNS, VPN).
- Bloqueo de accesos entrantes no autorizados.
- Reglas específicas para servicios internos expuestos.

#### ACLs Internas

```plaintext
deny ip any 192.168.10.0 0.0.0.255     ! Bloquea acceso desde zonas públicas
permit ip 192.168.20.0 0.0.0.255 any   ! Oficinas acceden a recursos internos
deny ip any any log                    ! Registra y bloquea todo lo demás
```
------------
# CISCO
![](https://github.com/Jyejii/CFI4-Redes/blob/main/Captura%20de%20pantalla%202025-05-13%20165038.png)
![](https://github.com/Jyejii/CFI4-Redes/blob/main/Captura%20de%20pantalla%202025-05-13%20165058.png)
![](https://github.com/Jyejii/CFI4-Redes/blob/main/Captura%20de%20pantalla%202025-05-13%20165121.png)
