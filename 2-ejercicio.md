### Crear contenedor de Postgres sin que exponga los puertos. Usar la imagen: postgres:15-alpine3.21

```
docker run -d --name postgres -e POSTGRES_PASSWORD=secretpassword postgres:15-alpine3.21
```

### Crear un cliente de postgres. Usar la imagen: dpage/pgadmin4

```
docker run -d --name pgadmin_cliente -e PGADMIN_DEFAULT_EMAIL=admin@admin.com -e PGADMIN_DEFAULT_PASSWORD=admin -p 8080:80 dpage/pgadmin4
```

La figura presenta el esquema creado en donde los puertos son:
- a: (no expuesto) 5432
- b: 80
- c: 8080

![Imagen](esquema-2-ejercicio.PNG)

## Desde el cliente

### Acceder desde el cliente al servidor postgres creado.

<img width="1919" height="1031" alt="image" src="https://github.com/user-attachments/assets/bd83f37f-0e38-433d-b19d-8d3a6f298d94" />

### Crear la base de datos info, y dentro de esa base la tabla personas, con id (serial) y nombre (varchar), agregar un par de registros en la tabla, obligatorio incluir su nombre.

```
CREATE DATABASE info;
CREATE TABLE personas (id serial PRIMARY KEY, nombre varchar(50));
INSERT INTO personas (nombre) VALUES ('Dilan'),('Melany'),('Josue');

```

## Desde el servidor postgresl
### Acceder al servidor
### Conectarse a la base de datos info

```
docker exec -it postgres bash
psql -U postgres -d info
```

### Realizar un select *from personas

```
select * from personas;
```

# AGREGAR UNA CAPTURA DE PANTALLA DEL RESULTADO

<img width="447" height="258" alt="image" src="https://github.com/user-attachments/assets/e183f143-255a-44e8-8fd2-b900e4d861b0" />

