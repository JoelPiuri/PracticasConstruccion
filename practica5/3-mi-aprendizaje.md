# COMPLETAR  
Comparando sus conocimientos antes de hacer la práctica con sus conocimientos después de hacer la tarea, explicar los principales aprendizajes logrados para beneficio de su formación profesional.  
Si solucionó un problema presentado al realizar la práctica también se debe documentar.

## Introducción

En esta sección se documentan los aprendizajes logrados durante la realización de la práctica y se comparan con los conocimientos previos. También se describe cualquier problema que se haya solucionado durante el proceso.

## Comparación de Conocimientos

### Antes de la Práctica

Antes de realizar esta práctica, mis conocimientos sobre el uso de Docker Compose para configurar servicios complejos eran limitados. Sabía cómo:

- Crear y ejecutar contenedores simples.
- Configurar Docker Compose para aplicaciones básicas.
- Comprender la estructura general de un archivo `docker-compose.yml`.

### Después de la Práctica

Después de completar esta práctica, he adquirido conocimientos avanzados y habilidades específicas que han beneficiado mi formación profesional:

- **Configuración Avanzada de Docker Compose**: Aprendí a configurar servicios complejos como SonarQube y PostgreSQL utilizando Docker Compose. Esto incluyó la especificación de volúmenes, redes y variables de entorno adecuadas.
- **Implementación de Healthchecks**: Ahora entiendo cómo implementar y configurar healthchecks para asegurar que los servicios estén funcionando correctamente antes de que otros servicios dependan de ellos.
- **Manejo de Dependencias entre Servicios**: He aprendido a usar la directiva `depends_on` con condiciones de salud para gestionar adecuadamente las dependencias entre servicios.
- **Solución de Problemas y Depuración**: Desarrollé habilidades para identificar y solucionar problemas comunes al trabajar con Docker, como la configuración incorrecta de servicios y la gestión del estado del demonio de Docker.

## Problemas Solucionados

Durante la realización de la práctica, me enfrenté a varios problemas que pude resolver con éxito:

### Error de Configuración de Docker Daemon

**Problema**: El demonio de Docker no estaba corriendo, lo que impedía la ejecución de los contenedores.

**Solución**: Verifiqué el estado del demonio Docker usando `docker info` y `sc query docker`. Luego, reinicié Docker Desktop y aseguré que el servicio Docker estuviera en estado `RUNNING`.

### Configuración Incorrecta de Healthchecks

**Problema**: Inicialmente, la configuración del healthcheck para el servicio PostgreSQL no funcionaba correctamente.

**Solución**: Modifiqué el archivo `compose.yaml` para usar el comando correcto `pg_isready -U sonar` y ajusté los parámetros de `interval`, `timeout`, `retries` y `start_period` para asegurar que el healthcheck se ejecutara correctamente.

### Mapeo de Puertos y Volúmenes

**Problema**: La configuración inicial de mapeo de puertos y volúmenes no permitía un acceso adecuado a los servicios desde el host.

**Solución**: Revisé la documentación de Docker y ajusté los mapeos de puertos y volúmenes para asegurar que SonarQube y PostgreSQL fueran accesibles desde el host, mejorando la interoperabilidad y persistencia de datos.

## Conclusión

La práctica me permitió profundizar mis conocimientos en Docker Compose, aprendiendo a configurar servicios avanzados y solucionando problemas prácticos. Esto ha fortalecido mis habilidades técnicas y me ha proporcionado herramientas valiosas para mi desarrollo profesional en el campo de la ingeniería de software.

