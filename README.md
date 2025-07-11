# Superset con soporte para Oracle

Este proyecto levanta Apache Superset con soporte para base de datos Oracle.

## Contenido del proyecto

- `Dockerfile.superset`: Imagen personalizada de Superset con Oracle Instant Client y el driver `oracledb`.
- `docker-compose.yml`: Orquesta Superset y Postgres como base de datos interna.

## Uso

1. Construí la imagen:

```bash
docker-compose build
```

2. Levantá los servicios:

```bash
docker-compose up -d
```

3. Accedé a Superset desde:

```
http://localhost:8088
```

## Conectar base Oracle

1. Ingresá a Superset y andá a `Sources > Databases > + Database`.
2. Usá esta URI (ajustando los datos reales):

```
oracle+oracledb://usuario:contraseña@host:1521/servicio
```

Ejemplo:

```
oracle+oracledb://scott:tiger@192.168.1.5:1521/XEPDB1
```

## Reverso con Nginx

Este Superset queda disponible en el puerto `8088`, listo para ser montado detrás de un Nginx como proxy.
