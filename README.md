# Laboratorio-Tarea
1. ¿Por qué el frontend no necesita conectarse a PostgreSQL?
  Porque el frontend se comunica con el backend mediante la API. Es el backend quien se encarga de consultar y modificar los datos de PostgreSQL
2. ¿Por qué el backend pertenece a dos redes?
  Porque necesita comunicarse con el frontend y también con PostgreSQL. Por eso pertenece a las redes frontend y datos
3. ¿Qué servicio necesita publicar un puerto en el anfitrión?
  El frontend, porque es el servicio al que accedemos desde el navegador mediante localhost:8080
4. ¿Por qué publicar PostgreSQL hacia fuera no es la solución adecuada para un fallo de comunicación interno?
  Porque los contenedores pueden comunicarse entre ellos mediante las redes internas de Docker. Publicar PostgreSQL hacia fuera podría suponer un riesgo de seguridad al exponer la base de datos innecesariamente
5. ¿Qué ventaja ofrece Docker Compose respecto a ejecutar los tres contenedores manualmente?
  Permite configurar y administrar todos los contenedores desde un único archivo. Así podemos iniciar, detener y configurar toda la aplicación con pocos comandos
6. ¿Por qué hemos dividido la arquitectura en dos redes?
  Para separar las comunicaciones de la aplicación. El frontend se comunica con el backend y PostgreSQL solamente se comunica con el backend. Esto mejora la organización y la seguridad
7. ¿Por qué el backend utiliza `db` como dirección de PostgreSQL?
  Porque db es el nombre del servicio de PostgreSQL en el archivo compose.yaml. Docker permite que los contenedores se encuentren utilizando sus nombres de servicio dentro de una misma red
8. ¿Qué diferencia existe entre detener un proyecto y eliminar sus volúmenes?
  Detener un proyecto para los contenedores, pero conserva sus datos. Eliminar los volúmenes también borra los datos almacenados en ellos
9. ¿Qué consecuencias tendría para la empresa perder el volumen de PostgreSQL?
  La empresa perdería los datos almacenados en la base de datos, como las incidencias registradas. Esto podría provocar una pérdida importante de información y afectar al funcionamiento de la aplicación
