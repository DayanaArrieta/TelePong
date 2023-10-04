# Juego Pong - Cliente/Servidor

Este proyecto se centra en la creación de una aplicación de red que simula el famoso juego Pong. El objetivo principal es adquirir experiencia en el desarrollo de aplicaciones y protocolos de red, lo que incluye la configuración de conexiones, el formato de datos y el uso de sockets. Tanto el cliente como el servidor se implementan en el lenguaje de programación C.

## Introducción

En este proyecto, hemos diseñado una aplicación cliente-servidor basada en la arquitectura de red TCP/IP. Esta arquitectura se adapta perfectamente a juegos en línea como el Pong, donde es crucial mantener una comunicación fluida entre múltiples clientes y un servidor central.

### Arquitectura Cliente/Servidor

La arquitectura se divide claramente en dos entidades: el cliente y el servidor. El cliente es responsable de recibir la entrada del usuario y transmitir comandos al servidor. Por otro lado, el servidor se encarga de mantener el estado del juego, ejecutar comandos, actualizar el estado y notificar a todos los clientes.

### Protocolo de Comunicación

Para garantizar una comunicación efectiva entre el cliente y el servidor, hemos diseñado un protocolo personalizado llamado "Ping Pong Protocol". Este protocolo se integra en la jerarquía de protocolos de la capa de aplicación sobre la red TCP/IP. A través de este protocolo, los clientes y el servidor pueden intercambiar información esencial para el juego, como comandos, datos de estado y notificaciones.

"Ping Pong Protocol"
Inicialización del Servidor: El servidor se crea mediante ppg_create_server(), que establece un socket TCP para la comunicación. Los clientes pueden conectarse a este servidor usando el puerto especificado.

Inicialización del Cliente: Los clientes se conectan al servidor utilizando la función ppg_connect_client(), especificando la dirección IP y el puerto del servidor. Tras una conexión exitosa, el servidor asigna a cada cliente un número de jugador (0 o 1) y comunica este número a los clientes.

Comunicación del Cliente: Una vez que los clientes están conectados, pueden comunicarse con el servidor mediante operaciones de lectura y escritura en sus descriptores de archivo de socket. El servidor y los clientes intercambian datos relacionados con el juego utilizando una estructura personalizada llamada struct gdata_redefined. Esta estructura parece contener información sobre las posiciones de los jugadores y el estado de terminación del juego.

Epoll y Sockets No Bloqueantes: El servidor utiliza epoll para gestionar eficientemente múltiples conexiones de clientes. Los sockets se establecen en modo no bloqueante para evitar llamadas bloqueantes al leer o escribir datos.

Multihilos: El servidor utiliza un grupo de hilos (tpool_t) para manejar varios clientes de manera concurrente. Los clientes se asignan a hilos para gestionar su comunicación.

Gestión del Estado del Juego: El servidor mantiene el estado del juego, incluyendo información sobre los clientes conectados, sus estados de juego (por ejemplo, jugando, terminado) y las sesiones de juego activas. Utiliza estructuras de datos personalizadas para gestionar esta información.

Terminación y Limpieza: Los clientes pueden enviar señales de terminación al servidor para indicar que están saliendo del juego. El servidor cierra el socket del cliente y los marca como terminados.

### Tecnologías Utilizadas

- Lenguaje de Programación: C
- Protocolo de Red: TCP/IP
- API de Sockets: Utilizamos la API de sockets de C para establecer y gestionar conexiones de red.

## Desarrollo

A lo largo de este proyecto, hemos implementado un servidor de juegos Pong y un cliente que se conecta a él a través de una conexión TCP. El cliente puede enviar comandos al servidor, como movimientos de paleta, y el servidor mantiene el estado del juego, asegurando que los clientes estén sincronizados y notificándoles sobre eventos importantes.

## Conclusiones

Este proyecto nos ha brindado una valiosa experiencia en el desarrollo de aplicaciones de red y protocolos personalizados. Hemos aprendido a configurar conexiones TCP, diseñar un protocolo de comunicación eficiente y trabajar en una arquitectura cliente-servidor. Estas habilidades son fundamentales en el mundo de las aplicaciones y juegos en línea.

A medida que continuamos desarrollando proyectos y explorando el mundo de las redes, estamos mejorando nuestras habilidades técnicas y nuestra comprensión de los desafíos asociados con las aplicaciones de red. Este proyecto nos ha proporcionado una base sólida para futuros desarrollos en el campo de las aplicaciones y juegos en línea.

## Contribución

Si deseas contribuir o mejorar este proyecto, te invitamos a enviar solicitudes de extracción (pull requests) o informes de errores (issues). Tu colaboración es bienvenida y puede ayudar a mejorar la calidad y funcionalidad de la aplicación.
