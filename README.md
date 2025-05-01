# CFI4-Redes
https://github.com/Jyejii/CFI4-Redes.git

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
