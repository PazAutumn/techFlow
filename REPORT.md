# Reporte de Implementación de CI

## Pasos realizados
1. Inicialización del repositorio Git local y configuración del repositorio remoto en GitHub.
    - Se creó un repositorio local y se realizó un commit inicial con los archivos proporcionados.
    - Se configuró el enlace remoto en GitHub y se realizó el push inicial.

2. Configuración y verificación de la API utilizando json-server.
    - Se instaló `json-server` globalmente y se verificó que la API respondiera correctamente en el puerto configurado.

3. Creación y configuración del pipeline en Jenkins.
    - Se configuró un nuevo trabajo en Jenkins y se creó un `Jenkinsfile` para definir las etapas del pipeline.
    - Se configuraron las credenciales necesarias para acceder al repositorio remoto.

4. Ejecución de pruebas automatizadas y generación de reporte de resultados.
    - Se modificó el pipeline para ejecutar las pruebas preescritas automáticamente.
    - Se configuró un paso en el pipeline para generar un reporte con los resultados de las pruebas.

## Problemas encontrados
1. **Error de instalación de `json-server`**:
    - **Problema**: `json-server` no estaba disponible en el entorno de Jenkins.
    - **Solución**: Se instaló `json-server` globalmente usando npm y se verificó su instalación.

2. **Error de credenciales en Jenkins**:
    - **Problema**: Jenkins no podía encontrar las credenciales especificadas.
    - **Solución**: Se crearon nuevas credenciales en GitHub y se configuraron correctamente en Jenkins.

3. **Error de sintaxis en el `Jenkinsfile`**:
    - **Problema**: `MultipleCompilationErrorsException` debido a un problema de sintaxis.
    - **Solución**: Se revisó y corrigió la estructura del `Jenkinsfile`.

4. **Error al iniciar `json-server`**:
    - **Problema**: `json-server: command not found`.
    - **Solución**: Se instaló `json-server` como dependencia del proyecto y se actualizó el `Jenkinsfile` para usar `json-server` desde las dependencias locales.

5. **Error al verificar el servidor**:
    - **Problema**: El servidor no se iniciaba correctamente.
    - **Solución**: Se agregó un script para matar cualquier proceso existente en el puerto 3000, iniciar `json-server` en segundo plano, esperar 3 segundos y verificar que el servidor estuviera funcionando.
