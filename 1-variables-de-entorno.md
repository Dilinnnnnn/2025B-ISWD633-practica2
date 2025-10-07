# Variables de Entorno
### ¿Qué son las variables de entorno?

Las variables de entorno son variables dinamicas que almacenan la informacion en el sistema operativo que afectan los procesos de ejecucion. Dan datos especificos al sistema operativo pero no modifican el codigo.

### Para crear un contenedor con variables de entorno

```
docker run -d --name <nombre contenedor> -e <nombre variable1>=<valor1> -e <nombre variable2>=<valor2>
```

### Crear un contenedor a partir de la imagen de nginx:alpine con las siguientes variables de entorno: username y role. Para la variable de entorno rol asignar el valor admin.

docker run -d --name nginx2 nginx:alpine -e username=dilin -e role=admin

<img width="1070" height="379" alt="image" src="https://github.com/user-attachments/assets/cd37d6cd-28b3-46b5-9e04-845d997c2ce6" />

### Crear un contenedor con la imagen de mysql, mapear todos los puertos
docker run -P -d --name mysql mysql:latest

### ¿El contenedor se está ejecutando?
directamente no si se comprueba con docker ps -a 

### Identificar el problema
Las variables de entorno  

    - MYSQL_ROOT_PASSWORD
    
    - MYSQL_ALLOW_EMPTY_PASSWORD
    
    - MYSQL_RANDOM_ROOT_PASSWORD

no se encuentran identificadas dado que no se iniciaron o especificaron en ningun momento.

### Para crear un contenedor con variables de entorno especificadas
- Portabilidad: Las aplicaciones se vuelven más portátiles y pueden ser desplegadas en diferentes entornos (desarrollo, pruebas, producción) simplemente cambiando el archivo de variables de entorno.
- Centralización: Todas las configuraciones importantes se centralizan en un solo lugar, lo que facilita la gestión y auditoría de las configuraciones.
- Consistencia: Asegura que todos los miembros del equipo de desarrollo o los entornos de despliegue utilicen las mismas configuraciones.
- Evitar Exposición en el Código: Mantener variables sensibles como contraseñas, claves API, y tokens fuera del código fuente reduce el riesgo de exposición accidental a través del control de versiones.
- Control de Acceso: Los archivos de variables de entorno pueden ser gestionados con permisos específicos, limitando quién puede ver o modificar la configuración sensible.

### Crear un contenedor con mysql, mapear todos los puertos y configurar las variables de entorno mediante un archivo
# COMPLETAR

# CAPTURA CON LA COMPROBACIÓN DE LA CREACIÓN DE LAS VARIABLES DE ENTORNO DEL CONTENEDOR ANTERIOR 

### ¿Qué bases de datos existen en el contenedor creado?
salen 4 bases de datos 

mysql> show databases;

+--------------------+

| Database           |

+--------------------+

| information_schema |

| mysql              |

| performance_schema |

| sys                |

+--------------------+

4 rows in set (0.02 sec)
