# COMPLETAR  
Comparando sus conocimientos antes de hacer la práctica con sus conocimientos después de hacer la tarea, explicar los principales aprendizajes logrados para beneficio de su formación profesional.  
Si solucionó un problema presentado al realizar la práctica también se debe documentar.

En esta practica aunque no este terminada en primera instancia aprendi como se pueden averiguar que tengo en una base de datos de postgresql desde un contenedor de docker,y crear adeas de agregar los datos desde la terminal mismo, es algo que no concocia antes.

Consultar: Cómo se gestionan datos confidenciales con los secretos de Docker (Docker Secrets).

Los docker secrets son un mecanismo de seguridad el cual permite almacenar y administrar datos confidenciales como contraseñas o certificados de forma cifrada pero dentro de docker.
esto se utiliza principalmente en docker Swarrm que oculta los datos en la ruta /run/secrets y solo los servicios autorizados pueden ingresar, esto no aparece ni si quiera en los logs, para esto se utiliza 

```
docker secret create
```

se asocia a un servicio con la opcion 

```
--secret 
```

y con ello se accede al contenido sin exponerlo, esta es una forma segura y controlada de manejar datos sensibles en docker.

