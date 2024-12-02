# Docker Compose: Nginx y SSH

Este proyecto utiliza Docker Compose para implementar un servidor Nginx con SSL y un servidor SSH seguro. 

## Estructura de Servicios

- **Nginx**: Servidor web con dos sitios virtuales (blog.midominio.local y app.midominio.local) y certificados SSL autofirmados.
- **SSH**: Servidor SSH con autenticación basada en llaves públicas.

## comando utilizados

docker compose down - para detener contenedores y eliminarlos
docker compose up -d --build - comando para inicializar los contendores del docker compose y a su vez crear las imaginas y ejecutarlo en segundo plano
docker rmi - para eliminar imagenes creadas

shh -i -p 2222 developer@localhost - comando para conectarme por medio del ssh al servidor
eval "$(ssh-agent -s)" - comando para crear el agente ssh
shh-add (nombre de la clave) - este comando se utiliza para agregar claves a el agente ssh
