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
````````
````````
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
