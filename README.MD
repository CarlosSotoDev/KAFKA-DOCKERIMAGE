# Apache Kafka (KRaft-only) — Docker Compose

Este repositorio levanta **Apache Kafka (KRaft-only, sin ZooKeeper)** usando Docker Compose (Compose v2+), ideal para desarrollo local.


## Requerimientos

- **Docker Desktop** (Windows/Mac) o **Docker Engine** (Linux)
- **Docker Compose v2+** (se usa como `docker compose`, no `docker-compose`)
- Puertos libres en tu máquina:
  - `9092` (Kafka client)
  - `9093` (Controller interno KRaft)
- **docker-compose.yml** para poder construir la imagen dentro de nuestro docker desktop

> Nota: Este proyecto **no usa** `version:` en `docker-compose.yml` (obsoleto en Compose moderno).


## Pasos para crear la imagen de Kafka
### 1) Clonar / Preparar carpeta

Crea una carpeta en tu computadora donde quieras guardar el proyecto. Por ejemplo, puedes llamarla `kafka-kraft-dev`. Luego, dentro de esa carpeta, coloca el archivo `docker-compose.yml` que se encuentra en este repositorio. Esto te permitirá gestionar y levantar Apache Kafka usando Docker Compose desde ese directorio.

### 2) Descargar la imagen (Recomendado)
Aunque el comando `docker compose up` puede descargarla automaticamente, es buena práctica hacer el pull explícito:

```bash
docker pull apache/kafka:latest
```

### 3) Levantar Kafka
A continuación debemos de ejecutar el `docker-compose` para crear la imagen dentro de nuestro docker desktop y hacer uso de kafka

```bash
docker compose up -d
```
Verificar que el contenedor esté corriendo:
```bash
docker ps
```

