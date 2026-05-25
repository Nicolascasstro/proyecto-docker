# proyecto-docker

Trabajo colaborativo politecnico

# Solución Taller - Integración Continua con Docker

Se han construido y comunicado con éxito dos contenedores independientes basados en Ubuntu.

## Comandos utilizados:

1. Creación de la red: `docker network create red-taller`
2. Enlace del contenedor 1: `docker network connect red-taller ubuntu1`
3. Enlace del contenedor 2: `docker network connect red-taller ubuntu2`

## Prueba de conectividad:

Desde la terminal de `ubuntu1` se ejecutó un ping hacia `ubuntu2` respondiendo con éxito mediante resolución de nombres interna de Docker.

Para crear estos mismos contenedores en local, se debe
tener el archivo actualizado con el docker compose que se encuentra en la carpeta evidencias y escribir en la terminal `docker-compose up -d` (esto creará los dos contedores y la red para conectarlos)
