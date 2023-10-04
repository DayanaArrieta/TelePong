# Juego Pong - Cliente/Servidor

Este proyecto se centra en la creación de una aplicación de red que simula el famoso juego Pong. El objetivo principal es adquirir experiencia en el desarrollo de aplicaciones y protocolos de red, lo que incluye la configuración de conexiones, el formato de datos y el uso de sockets. Tanto el cliente como el servidor se implementan en el lenguaje de programación C.

## Introducción

En este proyecto, hemos diseñado una aplicación cliente-servidor basada en la arquitectura de red TCP/IP. Esta arquitectura se adapta perfectamente a juegos en línea como el Pong, donde es crucial mantener una comunicación fluida entre múltiples clientes y un servidor central.

### Arquitectura Cliente/Servidor

La arquitectura se divide claramente en dos entidades: el cliente y el servidor. El cliente es responsable de recibir la entrada del usuario y transmitir comandos al servidor. Por otro lado, el servidor se encarga de mantener el estado del juego, ejecutar comandos, actualizar el estado y notificar a todos los clientes.

### Protocolo de Comunicación

Para garantizar una comunicación efectiva entre el cliente y el servidor, hemos diseñado un protocolo personalizado llamado "MyAppGameProtocol". Este protocolo se integra en la jerarquía de protocolos de la capa de aplicación sobre la red TCP/IP. A través de este protocolo, los clientes y el servidor pueden intercambiar información esencial para el juego, como comandos, datos de estado y notificaciones.

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
